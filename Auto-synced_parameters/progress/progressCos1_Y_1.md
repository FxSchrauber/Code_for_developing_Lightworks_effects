# progressCos1_Y_1  
![](images/progressCos1_Y_1.png)  
### Three-point progress: 1 ...  adjustable central value  ... 1  
  
  ---
    
### Required global variable declaration and definition 
*(add outside and above all shaders and functions):*
```` Code
//--------------------------------------------------------------//
// Definitions, declarations und macros
//--------------------------------------------------------------//

#define TWO_PI  6.2831853072
float _Progress;
````
---
  
### Code (Example as a function):  
```` Code
float fn_progressCos1_Y_1 (float centralValue)
{
   float progressCos1_0_1 = cos(_Progress * TWO_PI) * 0.5 + 0.5;
   return progressCos1_0_1 * (1.0 - centralValue) + centralValue;
}
````
---
  
### Parameter Description:
  
1. `centralValue`:  
   The adjustable central value.  
   This defines the return value at 50% effect progress  (`_Progress = 0.5`).  
   - **Type:** `float`, local   
   - **Permissible value range:** Unlimited, positive and negative.  
   
2. `_Progress`
   Auto-synced parameter
   - **Type:** `float`, global  
   - **Value range:** 0.0 to 1.0
   - **Alternative:** Often, it may be better to use another variable instead of `float _Progress`,  
      whose ramp is [generated by keyframing.](../../Basics/Variables_etc/Auto_synced/_Progress.md)
  
---
  
## Return value:
   - If `_Progress = 0.0`: 1.0  
   - If `_Progress = 0.5`: identical to `centralValue` (unlimited, positive and negative)  
   - If `_Progress = 1.0`: 1.0
   - The return values between the three Progress points (0.0 and 0.5 and 1.0) are calculated by the cosine wave.
   - **Type:** `float`   
   - **Value range:** Unlimited, positive and negative.  

