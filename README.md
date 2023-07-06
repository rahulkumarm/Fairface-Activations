# Fairface-Activations

This project makes use of PyTorch to generate activations for all the units of any layer in a deep learning model. An example is shown for the Fairface model where the generated activations are stored in a csv file.

## FairFace: Face Attribute Dataset for Balanced Race, Gender, and Age

The paper: https://openaccess.thecvf.com/content/WACV2021/papers/Karkkainen_FairFace_Face_Attribute_Dataset_for_Balanced_Race_Gender_and_Age_WACV_2021_paper.pdf

Karkkainen, K., & Joo, J. (2021). FairFace: Face Attribute Dataset for Balanced Race, Gender, and Age for Bias Measurement and Mitigation. In Proceedings of the IEEE/CVF Winter Conference on Applications of Computer Vision (pp. 1548-1558).

### Instructions to use FairFace

- Download Clone original [repo](https://github.com/dchen236/FairFace).
- Install Dependencies
   1. Please follow the [Pytorch's official documentation](https://pytorch.org/get-started/locally/) to install Pytorch
   2. Please also install dlib, if you have pip installed on your system. Simply type the following command on your terminal.

   ```
   pip install dlib
   ```
- Download models
   Download pretrained models from [here](https://drive.google.com/drive/folders/1F_pXfbzWvG-bhCpNsRj6F_xsdjpesiFu?usp=sharing) and save it in the same folder as where predict.py is located. Two models are included, race_4 model predicts race as White, Black, Asian and Indian and race_7 model predicts races as White, Black, Latino_Hispanic, East, Southeast Asian, Indian, Middle Eastern.
- Unzip the downloaded FairFace model as well as dlib face detection models in dlib_models.
- Prepare the images
   - prepare a csv and provide the paths of testing images where the colname name of testing images is "img_path" (see [template csv file](https://github.com/dchen236/FairFace/blob/master/test_imgs.csv).


### Run script predict.py
Run the predict.py script and provide the csv path (described in the section above).
```
python3 predict.py --csv "NAME_OF_CSV"
```

### Results
The results will be saved at "test_outputs.csv" (located in the same folder as predict.py, see sample [here](https://github.com/dchen236/FairFace/blob/master/test_outputs.csv).

The activations will be saved at "fairface_activations.csv"
