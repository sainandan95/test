# test

from PIL import Image
import numpy as np

# Load image
img = Image.open("image.png").convert("RGB")
pixels = np.array(img)
h, w, _ = pixels.shape

# Flatten and sort by brightness or any channel
flattened = pixels.reshape(-1, 3)
sorted_pixels = sorted(flattened, key=lambda x: sum(x))  # sort by total intensity

# Reshape back to image shape
sorted_img = np.array(sorted_pixels).reshape(h, w, 3)

# Save
Image.fromarray(sorted_img.astype(np.uint8)).save("sorted_output.png")
