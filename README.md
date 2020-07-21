# MoNuSeg-Challenge
This is my implementation of a model to carry out instance segmentation of nuclei in various tissue images as part of the [MoNuSeg Challenge](https://monuseg.grand-challenge.org/). I have created a model carrying out patch-based segmentation on 51x51 images extracted from the original images. The model is a CNN-2 model and classifies all pixels as either belonging to the nuclei (value = 1) or the background (value = 0).

The MATLAB code to read in an H&E image and xml file containing annotations and give the binary and colored maps based on annotated objects was taken from - 
[N. Kumar, R. Verma, S. Sharma, S. Bhargava, A. Vahadane and A. Sethi, "A Dataset and a Technique for Generalized Nuclear Segmentation for Computational Pathology," in IEEE Transactions on Medical Imaging, vol. 36, no. 7, pp. 1550-1560, July 2017](https://ieeexplore.ieee.org/document/7872382)

The color normalization part during the data preprocessing was carried out following - [Vahadane, Abhishek & Peng, Tingying & Albarqouni, Shadi & Baust, Maximilian & Steiger, Katja & Schlitter, Anna & Sethi, Amit & Esposito, Irene & Navab, Nassir. (2015). Structure-preserved color normalization for histological images. 1012-1015. 10.1109/ISBI.2015.7164042.](https://www.researchgate.net/publication/280384373_Structure-preserved_color_normalization_for_histological_images)

Training was done on 9600 patches extracted from a set of 24 images and 7500 patches extracted from 6 other images were used for cross-validation. Training lasted for 41 epochs using early stopping with a patience of 15 on the validation loss. Final accuracy achieved on the training set was 0.886 and on the validation set was 0.911. Average Jaccard Index computed on the validation set came out to be 0.665 following post-processing operations carried out to remove noisy pixels.

Further improvements to be made on the model by utilising a CNN-3 architechture and better post-precessing techniques following the training.
