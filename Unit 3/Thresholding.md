### 🔶 **Thresholding – Overview**

Thresholding is a **simple and effective** technique for **image segmentation**, where we partition an image into **regions** (typically object and background) based on **intensity values**.

It’s fast, easy to implement, and widely used in applications like document analysis, object detection, medical imaging, etc.

---

### 🔹 **Concept**

Suppose we have a grayscale image <math><semantics><mrow><mi>f</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo></mrow><annotation>f(x, y)</annotation></semantics></math>f(x,y), and the image histogram shows **two peaks** (or **modes**):

* One peak for **background pixels** (dark)

* One peak for **object pixels** (bright)

We can choose a **threshold value <math><semantics><mrow><mi>T</mi></mrow><annotation>T</annotation></semantics></math>T** that lies **between** these two peaks.

Then:
<math><semantics><mrow><mi>g</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>\=</mo><mrow><mo>{</mo><mtable><mtr><mtd><mstyle><mrow><mn>1</mn><mo>,</mo></mrow></mstyle></mtd><mtd><mstyle><mrow><mtext>if</mtext><mi>f</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>></mo><mi>T</mi><mtext>(object)</mtext></mrow></mstyle></mtd></mtr><mtr><mtd><mstyle><mrow><mn>0</mn><mo>,</mo></mrow></mstyle></mtd><mtd><mstyle><mrow><mtext>if</mtext><mi>f</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>≤</mo><mi>T</mi><mtext>(background)</mtext></mrow></mstyle></mtd></mtr></mtable></mrow></mrow><annotation>g(x, y) = \\begin{cases} 1, & \\text{if } f(x, y) > T \\quad \\text{(object)} \\\\ 0, & \\text{if } f(x, y) \\leq T \\quad \\text{(background)} \\end{cases}</annotation></semantics></math>g(x,y)\={1,0,​iff(x,y)>T(object)iff(x,y)≤T(background)​

Here, <math><semantics><mrow><mi>g</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo></mrow><annotation>g(x, y)</annotation></semantics></math>g(x,y) is the **segmented binary image**:

* `1` means **object**

* `0` means **background**

---

### 📊 **Histogram-Based Thresholding**

If you draw a histogram of pixel intensities:

* Two clear peaks mean the image can be easily segmented using a **single global threshold**.

* If there are multiple peaks or no clear separation, advanced methods (like Otsu's method or adaptive thresholding) are needed.

---

### 🔁 **Summary**

* Thresholding uses **intensity values** to segment an image.

* A pixel is assigned to object or background based on whether its intensity is greater than a **threshold <math><semantics><mrow><mi>T</mi></mrow><annotation>T</annotation></semantics></math>T**.

* It's particularly effective when the image histogram shows **bimodal distribution**.

---


### 🔶 **Types of Thresholding in Image Processing**

#### 1\. **Global Thresholding**

* A **single constant threshold** <math><semantics><mrow><mi>T</mi></mrow><annotation>T</annotation></semantics></math>T is applied to the entire image.

* If <math><semantics><mrow><mi>f</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>></mo><mi>T</mi></mrow><annotation>f(x, y) > T</annotation></semantics></math>f(x,y)>T, pixel is object; otherwise, background.

* Best used when the image has **uniform lighting** and **bimodal histogram**.

> 📌 Example: Basic thresholding using a fixed value like <math><semantics><mrow><mi>T</mi><mo>\=</mo><mn>127</mn></mrow><annotation>T = 127</annotation></semantics></math>T\=127 for all pixels.

---

#### 2\. **Variable Thresholding**

* Threshold value <math><semantics><mrow><mi>T</mi></mrow><annotation>T</annotation></semantics></math>T **changes across the image**.

There are two important types under variable thresholding:

##### a. **Local (Regional) Thresholding**

* <math><semantics><mrow><mi>T</mi></mrow><annotation>T</annotation></semantics></math>T is computed based on **local neighborhood properties** (e.g., average or median intensity around each pixel).

* Useful when the image has **non-uniform lighting**.

> 📌 Example: Each region may have its own threshold based on local contrast.

##### b. **Dynamic or Adaptive Thresholding**

* A special case where <math><semantics><mrow><mi>T</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo></mrow><annotation>T(x, y)</annotation></semantics></math>T(x,y) depends on **pixel coordinates** or **local statistics**.

* Automatically adapts the threshold value for different parts of the image.

> 📌 Common in real-world applications like document binarization in OCR.

---

#### 3\. **Multiple Thresholding**

* **More than one threshold value** is used to divide the image into multiple classes.

> 📌 Example: Use thresholds <math><semantics><mrow><msub><mi>T</mi><mn>1</mn></msub></mrow><annotation>T\_1</annotation></semantics></math>T1​ and <math><semantics><mrow><msub><mi>T</mi><mn>2</mn></msub></mrow><annotation>T\_2</annotation></semantics></math>T2​ to classify pixels into background, object1, and object2.
<math><semantics><mrow><mi>g</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>\=</mo><mrow><mo>{</mo><mtable><mtr><mtd><mstyle><mn>0</mn></mstyle></mtd><mtd><mstyle><mrow><mtext>if</mtext><mi>f</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>≤</mo><msub><mi>T</mi><mn>1</mn></msub></mrow></mstyle></mtd></mtr><mtr><mtd><mstyle><mn>1</mn></mstyle></mtd><mtd><mstyle><mrow><mtext>if</mtext><msub><mi>T</mi><mn>1</mn></msub><mo><</mo><mi>f</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>≤</mo><msub><mi>T</mi><mn>2</mn></msub></mrow></mstyle></mtd></mtr><mtr><mtd><mstyle><mn>2</mn></mstyle></mtd><mtd><mstyle><mrow><mtext>if</mtext><mi>f</mi><mo>(</mo><mi>x</mi><mo>,</mo><mi>y</mi><mo>)</mo><mo>></mo><msub><mi>T</mi><mn>2</mn></msub></mrow></mstyle></mtd></mtr></mtable></mrow></mrow><annotation>g(x, y) = \\begin{cases} 0 & \\text{if } f(x, y) \\leq T\_1 \\\\ 1 & \\text{if } T\_1 < f(x, y) \\leq T\_2 \\\\ 2 & \\text{if } f(x, y) > T\_2 \\end{cases}</annotation></semantics></math>g(x,y)\=⎩⎨⎧​012​iff(x,y)≤T1​ifT1​<f(x,y)≤T2​iff(x,y)>T2​​
---

### 📝 Quick Summary Table

|Type|Threshold Value|Used When|
|---|---|---|
|**Global**|Constant for entire image|Uniform lighting, simple images|
|**Local / Regional**|Varies by neighborhood|Uneven lighting, local contrast|
|**Adaptive / Dynamic**|Depends on (x, y)|Complex lighting conditions|
|**Multiple**|Multiple values <math><semantics><mrow><msub><mi>T</mi><mn>1</mn></msub><mo>,</mo><msub><mi>T</mi><mn>2</mn></msub><mo>,</mo><mi>.</mi><mi>.</mi><mi>.</mi></mrow><annotation>T\_1, T\_2,...</annotation></semantics></math>T1​,T2​,...|Multilevel classification|

---
