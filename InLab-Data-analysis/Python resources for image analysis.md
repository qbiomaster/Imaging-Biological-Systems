- **Opening a JPG image in Python**

There are multiple libraries you can use depending on what you want to do with the image. The most common are:

***Using Pillow (PIL fork)***

```python
from PIL import Image

# Open the image
img = Image.open("example.jpg")

# Show info
print(img.format)   # e.g. 'JPEG'
print(img.mode)     # e.g. 'RGB'
print(img.size)     # (width, height)

# Display the image
img.show()
```

***Using OpenCV***

```python
import cv2

# Open the image
img = cv2.imread("example.jpg")

# Show structure
print(type(img))        # <class 'numpy.ndarray'>
print(img.shape)        # (height, width, channels), e.g. (720, 1280, 3)
print(img.dtype)        # e.g. uint8

# Display the image
cv2.imshow("Image", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

**Structure of the Output**

***Pillow (`Image.open`)***

- The output is a `PIL.Image.Image` object.
- Attributes:
  - `.format` → format of the file (e.g. "JPEG")
  - `.mode` → color mode (e.g. "RGB", "L" for grayscale, "RGBA")
  - `.size` → (width, height)
  - `.info` → metadata (EXIF, DPI, etc.)

***OpenCV (`cv2.imread`)***

- The output is a **NumPy array** of shape:

  ```
  (height, width, channels)
  ```

  - Each pixel is an array of values, usually 3 channels (B, G, R) in **BGR order**.
  - Example: `img[100, 200]` → `[blue, green, red]` at pixel (200,100).

------

👉 If you want to **process images like arrays (e.g., machine learning, pixel operations)** → OpenCV (NumPy arrays) is better.

👉 If you want to **manipulate images at a higher level (e.g., resize, crop, format conversion)** → Pillow is more convenient.

------

### **Opening a TIFF image in Python**

***Using Pillow (PIL)***

```python
from PIL import Image

# Open TIFF image
img = Image.open("example.tif")

print(img.format)   # 'TIFF'
print(img.mode)     # e.g. 'RGB', 'L', 'I;16' (16-bit grayscale), etc.
print(img.size)     # (width, height)

img.show()
```

👉 **Notes**:

- Pillow supports many TIFF variants, including multi-page TIFF (common in medical/scientific imaging).

- If the TIFF has multiple frames (pages):

  ```python
  from PIL import ImageSequence
  
  for i, page in enumerate(ImageSequence.Iterator(img)):
      print(f"Page {i}: size={page.size}, mode={page.mode}")
  ```

------

***Using OpenCV***

```python
import cv2

# Open TIFF image
img = cv2.imread("example.tif", cv2.IMREAD_UNCHANGED)

print(type(img))    # <class 'numpy.ndarray'>
print(img.shape)    # (height, width, channels) or (height, width) for grayscale
print(img.dtype)    # often uint8, but can be uint16 for scientific data

cv2.imshow("TIFF", img)
cv2.waitKey(0)
cv2.destroyAllWindows()
```

👉 OpenCV handles **single-page TIFFs** easily, but **multi-page TIFFs** are trickier (you’d need `tifffile` or Pillow for that).

------

***Using tifffile (specialized library)***

```python
import tifffile

# Open TIFF
img = tifffile.imread("example.tif")

print(type(img))    # numpy.ndarray
print(img.shape)    # supports multi-page and multi-dimensional
print(img.dtype)    # often uint8, uint16, or float32
```

👉 `tifffile` is the go-to library for **scientific TIFFs** (microscopy, geospatial, medical imaging).



**📌 Structure of `tifffile.imread()` Output**

When you use:

```python
import tifffile

img = tifffile.imread("example.tif")
```

The return is a **NumPy array**, but the shape depends on the kind of TIFF:

------

**1. Single-page grayscale TIFF**

- Shape: `(height, width)`

- Example:

  ```python
  img.shape   # (1024, 1024)
  img.dtype   # usually uint8, uint16, or float32
  ```

------

**2. Single-page RGB TIFF**

- Shape: `(height, width, 3)`

- Example:

  ```python
  img.shape   # (1024, 1024, 3)
  img.dtype   # often uint8 or uint16
  ```

------

**3. Multi-page TIFF (like a stack of images)**

- Shape: `(n_pages, height, width)` for grayscale

- Shape: `(n_pages, height, width, channels)` for RGB

- Example:

  ```python
  img.shape   # (50, 1024, 1024) → 50 grayscale slices
  img.shape   # (50, 1024, 1024, 3) → 50 RGB slices
  ```

This is very common in **microscopy or medical imaging (CT/MRI scans)** where a TIFF contains a whole stack.

------

**4. Higher-dimensional TIFF (OME-TIFF, microscopy)**

Some TIFFs encode data with dimensions like:

- `(time, channels, z, height, width)`

- Example:

  ```python
  img.shape   # (10, 3, 20, 512, 512)
  ```

Here you could have:

- `time` → number of timepoints
- `channels` → spectral channels (e.g. GFP, DAPI in microscopy)
- `z` → depth slices (z-stack)
- `height, width` → image size

------

✅ **So, the structure is always a NumPy array** with shape depending on whether the TIFF is single-page, multi-page, or multi-dimensional.

### Procedure to open stacks of tif images:

**1. Load all pages into a single NumPy array**

If the TIFF is a stack (multi-page):

```python
import tifffile

# Read the TIFF stack
img_stack = tifffile.imread("example_stack.tif")

print(img_stack.shape)
print(img_stack.dtype)
```

Example outputs:

- Grayscale stack → `(50, 512, 512)`
- RGB stack → `(50, 512, 512, 3)`

So `img_stack[0]` is the first frame, `img_stack[1]` is the second, etc.

------

**2. Iterating through frames**

```python
for i, frame in enumerate(img_stack):
    print(f"Frame {i}: shape={frame.shape}, dtype={frame.dtype}")
```

This way you can access each page as a separate **NumPy array**.

------

**3. Saving frames individually**

```python
import imageio.v2 as imageio

for i, frame in enumerate(img_stack):
    filename = f"frame_{i}.png"
    imageio.imwrite(filename, frame)
    print(f"Saved {filename}")
```

------

**4. Using `TiffFile` for advanced access**

If you want more control (metadata, selective reading):

```python
from tifffile import TiffFile

with TiffFile("example_stack.tif") as tif:
    print(len(tif.pages))   # number of pages
    for i, page in enumerate(tif.pages):
        img = page.asarray()
        print(f"Page {i}: shape={img.shape}, dtype={img.dtype}")
```

This is useful if the file is huge and you don’t want to load everything into memory at once.

------

✅ **Summary**:

- `tifffile.imread` → loads everything into one NumPy array (convenient for small/medium stacks).
- `tifffile.TiffFile` → lets you iterate lazily through pages, good for very large TIFFs.

------

### **Visualizing a multi-page TIFF stack interactively** with `matplotlib`.

**1. Simple interactive viewer with keyboard**

```python
import tifffile
import matplotlib.pyplot as plt

# Load TIFF stack
stack = tifffile.imread("example_stack.tif")
print("Stack shape:", stack.shape)  # e.g. (50, 512, 512)

# Start with first frame
idx = 0
fig, ax = plt.subplots()
im = ax.imshow(stack[idx], cmap="gray")
ax.set_title(f"Frame {idx+1}/{stack.shape[0]}")

def on_key(event):
    global idx
    if event.key == "right":
        idx = (idx + 1) % stack.shape[0]
    elif event.key == "left":
        idx = (idx - 1) % stack.shape[0]
    im.set_data(stack[idx])
    ax.set_title(f"Frame {idx+1}/{stack.shape[0]}")
    fig.canvas.draw()

fig.canvas.mpl_connect("key_press_event", on_key)
plt.show()
```

👉 Use **← and → arrows** to move through the frames.

------

**2. Using a slider widget**

This is nice if you want a GUI scroll bar:

```python
import tifffile
import matplotlib.pyplot as plt
from matplotlib.widgets import Slider

# Load TIFF stack
stack = tifffile.imread("example_stack.tif")

fig, ax = plt.subplots()
plt.subplots_adjust(bottom=0.25)

idx = 0
im = ax.imshow(stack[idx], cmap="gray")
ax.set_title(f"Frame {idx+1}/{stack.shape[0]}")

# Add slider
ax_slider = plt.axes([0.2, 0.1, 0.65, 0.03])
slider = Slider(ax_slider, 'Frame', 0, stack.shape[0]-1,
                valinit=0, valstep=1)

def update(val):
    idx = int(slider.val)
    im.set_data(stack[idx])
    ax.set_title(f"Frame {idx+1}/{stack.shape[0]}")
    fig.canvas.draw_idle()

slider.on_changed(update)
plt.show()
```

👉 This adds a slider at the bottom so you can scrub through frames.

------

✅ **Summary**:

- **Keyboard method** is lightweight and fast.
- **Slider method** is more user-friendly for browsing interactively.

------

- 