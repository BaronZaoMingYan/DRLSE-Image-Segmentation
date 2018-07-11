# Distance Regularized Level Set Evolution and Its Application to Image Segmentation
Level Set Evolution (LSE) is well-known method for contour extraction (determine the border of the object) and object segmentation. The main handicap of LSE is re-initialization step. This step has to be implemented to get rid of irregularities of extracted border of object (contour). Basically, level set has to be periodically re-initialize according to some distance based criteria. To the fact that how we can implement re-initialization step is not theoretical solved problem. In engineering practice, there could be significant amount of errors on to the results. In this paper, researcher proposed the new variation of LSE method which intrinsically maintains level set function instead of re-initialization step by the way of adding new term named distance regularized. That is why this new method’s name is Distance regularized LSE (DRLSE). 

## Theoretical Background:
In computer vision, “active contour” or by other name “snakes” is very important step for object detection. We can say this method is special kind of object segmentation. With this method, we need to start initial object border and the method iteratively find the object border step by step. Generally all active contour literature use energy minimization algorithm. Energy minimization’s name comes from physic. It is about the fact that all matters in our universe comes from high energy level and goes to minimum energy level. So if the matter at the minimum energy level, we can say “stable” for this matter. With this analogy, we can say if the extracted contour’s energy is at the minimum energy then it represent the border of the object as good as possible.  
In the proposed method, Level Set Function (LSF) is shown by ϕ, it is matrix with the same dimension of given image and every single cell value refer a real number in range of [-2 2] in our example. This LSF matrix ϕ, is setted initial given object region as -2 and rest of them with 2. At the last iteration we need to check  ϕ matrix, and we assign the cell, which value is 0, as a border of the object. So ϕ matrix is very important variable for us. The energy function which has to be minimize is the function of ϕ matrix as it shown in following equation in the paper [1] as follows;

ε(ϕ)=μR_p (ϕ)+λL_g (ϕ)+αA_g (ϕ)

The proposed method offer to write an energy function as a sum of 3 part which are regularized distance term R_p (ϕ)  with its weight μ, Length term L_g (ϕ)  with its weight λ, and area term A_g (ϕ)  with its weight α.  

Energy minimization algorithms aim is to find ϕ which get the energy function ε(ϕ) minimum. To solve this problem, proposed method used gradient descent algorithm which is well-known numerical analysis method.


![Alt Text](Outputs/bone.gif)
![Alt Text](Outputs/femur.gif)
![Alt Text](Outputs/capeverde.gif)
![Alt Text](Outputs/eigg.gif)


## Reference
[1] C. Li, C. Xu, C. Gui, M. D. Fox, "Distance Regularized Level Set Evolution and Its Application to Image Segmentation", IEEE Trans. Image Processing, vol. 19 (12), pp. 3243-3254, 2010.