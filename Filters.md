# Filters

**Basically Filters are of two types:**
          * Smoothing filters or low pass filters.
          * Sharpening filters or high pass filters


**1). Smoothing Filters
  These smoothing filters are mainly classified into two types:
           i). Smoothing linear filters (or) Averaging filters
           ii). Smoothing nonlinear filters (or) Order statistic filters.**        


**ii). Smoothing nonlinear filters (or)
Order statistics filters:
The different order statistics filters are:
a). Median filters.
b). Max. filters.
c). Min. filters
d). Modal filters
e). k-closest averaging**

  🔍 **k-Closest Averaging Filter – Step-by-Step**
------------------------------------------------

### ✅ **Step 1: Sort the Pixels in the Window**

For a typical 3×3 window:


[ p1 p2 p3
  p4 p5 p6
  p7 p8 p9 ]



*   Sort these 9 values in ascending or descending order.
    

### ✅ **Step 2: Choose 'k' Closest Pixels to the Center Pixel**

*   Take the **center pixel**, say p5.
    
*   Calculate the **absolute difference** between p5 and each of the other pixels.
    
*   Select the **k pixels that have the smallest difference** from p5.
    

📌 Example: If k = 5, pick the 5 values closest in intensity to p5.

### ✅ **Step 3: Average Those k Pixels**

*   Compute the mean (average) of the k closest values.
    
*   Replace the center pixel p5 with this **average**.
    

### 💡 **Note:**

*   This technique is good at **preserving edges** while still **removing outliers**.
    
*   Works better than a basic average or even median in some contexts, but it’s **computationally expensive** due to:
    
    *   Sorting
        
    *   Difference calculations
        
    *   Selection and averaging
 





 # 2.Sharpening filters (or) High pass filters
 
➢Since averaging is analogous to integration, it is logical to conclude that sharpening could be accomplished by spatial differentiation.


Sharpening filters are of two types:

**i). First order derivative filters
ii). Second order derivative filters**





