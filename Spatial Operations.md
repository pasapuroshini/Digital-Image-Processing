<img width="854" alt="Screenshot 2025-04-15 at 3 54 18 PM" src="https://github.com/user-attachments/assets/065603a1-0af7-4f32-ab8c-dad82de2332e" />

**This diagram illustrates the mechanics of linear spatial filtering using a 3 × 3 filter mask in image processing.**

Linear spatial filtering involves applying a **filter mask (or kernel)** over an image to enhance features (like edges) or perform operations (like blurring or sharpening).

### 📦 **What the Diagram Shows:**

#### 1\. **Image Pixels Grid (Top-Left Section):**

*   This is a small section of the entire image, with pixels laid out in a 2D grid.
    
*   The filter mask is being placed on top of this image at a specific position centered on the pixel at (x, y).
    

#### 2\. **Filter Coefficients (Top-Right Black Box):**

*   The filter (or kernel) has a 3×3 set of coefficients denoted as:
  ```
w(-1, -1)  w(-1, 0)  w(-1, 1)
w(0, -1)   w(0, 0)   w(0, 1)
w(1, -1)   w(1, 0)   w(1, 1)
```
* These are weights that determine how much influence each neighboring pixel has on the new pixel value at (x, y).

#### 3\. **Image Pixels Under the Filter (Bottom Section):**

*   This is the **actual image pixel values** beneath the filter mask centered at pixel f(x, y).

  ```
f(x-1, y-1)  f(x-1, y)  f(x-1, y+1)
f(x,   y-1)  f(x,   y)  f(x,   y+1)
f(x+1, y-1)  f(x+1, y)  f(x+1, y+1)
```


### 🔍 **Why Use This?**

*   **Edge Detection** (e.g., Sobel filter)
    
*   **Smoothing** (e.g., Gaussian blur)
    
*   **Sharpening**
    
*   **Noise Reduction**
    

Each use case has its own specific set of w(s, t) coefficients.


**This whole process of moving the mask, multiplying and adding is known as ‘Convolution’**

Generally, when we are choosing the mask, it is good to choose the masks of odd sizes like 3×3, 5×5 and soon, because the masks of size 2×2, 4×4 soon are awkward (difficult) to implement because they do not have a clear center.


### 🎯 **Goal:**

To produce a new image g(x, y) by applying a filter (or kernel) w(i, j) on the original image f(x, y).

### 🔧 **What is Spatial Filtering?**

Spatial filtering is a process where we compute the new value of a pixel based on a **weighted combination of its neighboring pixel values**, using a kernel (a small matrix).

### 🧮 **Key Equation:**

#### General Case:

*   **f(x+i, y+j)**: Intensity of the image at a neighboring pixel.
    
*   **w(i, j)**: Weight from the kernel at that position.
    
*   **g(x, y)**: Output image value at position (x, y).
    

The kernel is typically centered at (0, 0) with range:

*   i ∈ \[-a, a\]
    
*   j ∈ \[-b, b\]
    

### 📏 **Example for 3×3 Mask:**

When the kernel size is 3×3, we have a = 1 and b = 1. So the summation limits become:

This means the output pixel at (x, y) is computed using the **3×3 neighborhood** around that pixel.

### 🔳 **Kernel Visualization (Right Side):**

*   The grid shows a kernel (filter mask) overlaid on an image.
    
*   The highlighted center represents the current pixel (x, y) being filtered.
    
*   The values around it (neighbors) are weighted by the kernel coefficients w(i, j).
    

### 🧠 **Takeaway:**

The filtered output g(x, y) is calculated as a **dot product between the filter kernel and the corresponding image patch** centered at (x, y).


<img width="692" alt="Screenshot 2025-04-15 at 5 28 10 PM" src="https://github.com/user-attachments/assets/330e7278-5d31-4a50-ba83-a42b7fc40378" />

<img width="191" alt="Screenshot 2025-04-15 at 5 33 35 PM" src="https://github.com/user-attachments/assets/81ccbd04-d7f2-4129-a713-43cd0a90498a" />


<img width="622" alt="Screenshot 2025-04-15 at 5 33 50 PM" src="https://github.com/user-attachments/assets/8195dd97-344c-4298-a90d-9679b24e374e" />


<img width="749" alt="Screenshot 2025-04-15 at 5 33 59 PM" src="https://github.com/user-attachments/assets/036b69ee-77fb-426e-bb31-568f642f38b3" />
