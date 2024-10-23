java c
Theoretical Foundations in Multimedia
AY2024/25 Semester 1
Assignment 4:  Medical Image Segmentation (12 marks)
Submission Deadline:  24  October 2024 Thursday11:59pm
Figure 1: Segmentation of liver in CT volume image. (a) 3D elastic model. (b) Initialization of elastic model (yellow).  (c) Fitting of elastic model to liver surface.   (d) Segmentation result. (b) and (c) each shows the view in a 2D slice of the 3D volume image.You are the Chief Technical Officer of SmartHealth.  Your team is tasked to develop a software for segmenting the outer surface of the liver in a 3D CT volume, which is a stack of 2D images. After studying some example CT images, you discover that the 3D shapes of the liver of diferent patients are similar but vary in shape details. You decide to solve the problem by ﬁtting a 3D elastic model to the liver surface. The ﬁtted 3D model should not have surface overlap and self-intersection.
After some deliberation, your team arrive at the following concepts:
•                      The 3D elastic model M consists of a set of mesh points pi , i = 1, . . . , m.
•                      The CT volume image V  contains a set of voxels (volume pixels) located at qj , j  = 1, . . . , n.
•                      Each voxel at position qj   has a feature s(qj ) whose value ranges from 0 to 1.  The larger the value of s(qj ), the more likely is qj   a surface point of the liver.  Due to imperfection of CT volume, some liver surface points may have small s values, making them indistinguishable from their surrounding non-surface points.
•                      A non-rigid transformation function f is needed to transform. the elastic model M to ﬁt it to the outer surface of the liver in the CT volume.  The notation f (pi ) denotes the position of point pi  after non-rigid transformation.
•                      The correspondence between the elastic model M and the CT volume V is unknown. So, a function c : M → V is needed to describe the correspondence between them.If c(pi ) = qj  for a particular qj  in V , then s(qj ) is large, which means that qj  is a likely liver surface point.  Otherwise, c(pi ) = φ which means that pi   has no corresponding point. You don’t want c(pi ) to be an unlikely liver surface point.
•                      The non-rigid transformation f does not ensure good distribution of mesh points over the mesh surface after transformation.  So, a re-distribution function d  is needed to re-distribute mo代 写Theoretical Foundations in Multimedia AY2024/25 Semester 1 Assignment 4: Medical Image SegmentationMatlab
代做程序编程语言re mesh points over surfaces with higher curvature, and fewer mesh points over surfaces with lower curvature. The notation d(pi ) denotes the position of point pi  after re-distribution.  The re-distribution changes the positions of the mesh points over the mesh surface without changing the shape of the mesh. It can be applied to the mesh before or after non-rigid transformation.
•                      The resultant 3D model R is a transformed version of the elastic model M. It contains a set of mesh points ri , i = 1, . . . , m.  Each point ri   in R corresponds to the point pi in M , and R and M have the same mesh connectivity. The mesh points ri  of R should be well distributed over the mesh surface.
Assignment Questions(a) What is an appropriate optimization objective of this problem? Why is it appropriate?
(b) What are the appropriate constraints of this problem? Why are they appropriate?
Note: You may describe the constraints using English sentences instead of mathemat- ical expressions.
(c) Based on the problem deﬁnition, including your answers to parts (a) and (b), design an algorithm that performs segmentation of the liver CT volume. Express your algorithm using high-level, conceptual instructions. You don’t need to explain how the functions f , c, and d work internally. Just use them as black-box methods in your algorithm.
Liver Volume Segmentation Algorithm
1   Initialize M to be a small sphere within the liver.
2   repeat
3           . . .
4   until . . .In your segmentation algorithm, you may use any algorithm described in the lecture as a black-box helper algorithm. You don’t need to describe the details of the helper algorithms; just describe what the helper algorithms work on, i.e., the inputs to the helper algorithms.  Other parts of your segmentation algorithm should be described with sufficient details.
(d) Explain how your segmentation algorithm satisﬁes the optimization objective and con- straints. You don’t need to explain why the algorithm can converge.
Submission
Write your answer in single-spaced, 12pt font. Images are not needed, but you can include images if you like. Include the following at the top of your assignment paper:
•                           “Assignment 4”
•                     Your name and student number
Save your assignment paper in PDF format. Use your student number as the ﬁle name, e.g., A0123456Z-assignment-4.pdf.



         
加QQ：99515681  WX：codinghelp  Email: 99515681@qq.com
