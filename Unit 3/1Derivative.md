### 🔹 **1\. Digital Derivatives: Why Use Differences?**

In continuous math, a derivative measures how a function changes as its input changes. But in **digital images**, which are **discrete**, we can’t take a true derivative. So we use **finite differences** to approximate them.

An image is essentially a 2D function f(x,y)f(x, y)f(x,y), where each value represents **intensity** at pixel coordinates (x,y)(x, y)(x,y).

### 🔹 **2\. First Derivative (Edge Detection)**

The **first derivative** tells us where the image intensity changes sharply — like edges.

#### Requirements:

*   ✅ **Zero in constant regions** (no change in intensity → no edge)
    
*   ✅ **Nonzero at the start of an intensity step or ramp** (abrupt change → edge detected)
    
*   ✅ **Nonzero along a ramp** (gradual change → still a detectable gradient)
    

#### Example Approximation:

In 1D:f′(x)≈f(x+1)−f(x)f'(x) \\approx f(x+1) - f(x)f′(x)≈f(x+1)−f(x)In 2D (x-direction):∂f∂x≈f(x+1,y)−f(x,y)\\frac{\\partial f}{\\partial x} \\approx f(x+1, y) - f(x, y)∂x∂f​≈f(x+1,y)−f(x,y)

### 🔹 **3\. Second Derivative (Edge Localization and Enhancement)**

The **second derivative** highlights regions where the rate of change itself changes — e.g., transitions between smooth and abrupt intensity changes.

#### Requirements:

*   ✅ **Zero in constant regions** (flat → no curvature)
    
*   ✅ **Nonzero at the onset and end of an edge or ramp** (where change starts/stops)
    
*   ✅ **Zero along a ramp** (constant slope → no curvature)
    

#### Example Approximation:

In 1D:f′′(x)≈f(x+1)+f(x−1)−2f(x)f''(x) \\approx f(x+1) + f(x-1) - 2f(x)f′′(x)≈f(x+1)+f(x−1)−2f(x)In 2D: **Laplacian operator**:∇2f(x,y)=f(x+1,y)+f(x−1,y)+f(x,y+1)+f(x,y−1)−4f(x,y)\\nabla^2 f(x, y) = f(x+1, y) + f(x-1, y) + f(x, y+1) + f(x, y-1) - 4f(x, y)∇2f(x,y)=f(x+1,y)+f(x−1,y)+f(x,y+1)+f(x,y−1)−4f(x,y)

### 🔹 **4\. Digital Nature of Images**

Since digital images are:

*   Made of **finite intensity values** (e.g., 0–255 in grayscale), and
    
*   Changes occur over **discrete steps** (from one pixel to the next),
    

👉 **The smallest distance** over which a change can be detected is **between two adjacent pixels**.So, all derivative approximations are based on differences **between neighboring pixel intensities**.
