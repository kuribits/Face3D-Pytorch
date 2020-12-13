# Face3D: 3D Face Recognition

This is a fork for implementing [XingwXiong's PyTorch 3D Face Recognition](https://github.com/XingwXiong/Face3D-Pytorch) for real-time prediction on Kinect RGBD input. 

Given an RGB image and a corresponding depth image, the task is to predict the identity of the individual in the image(s).


## To-Do
- [ ] Prediction script
- [ ] Support for Kinect input

## Dependencies
`python==3.8`

See `requirements.txt` for a list of all dependencies.

## Dataset
Dataset is available from [here](http://125.39.136.212:8484/3dvggface2_1.tar.gz).

The data set contains **403,067** pairs of face images of **1,208** people. Each pair of face images is registered and contains an RGB image and a depth image.

<div style="text-align:center;" align="center">
    <!-- Image Caption Template -->
    <div style="padding:0; margin-bottom: 0;">
        <img style="border-radius: 0.3125em; box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08); margin: 0 10px;"
        src="./README/rgb_0001_03.jpg" alt="the RGB image">
         <img style="border-radius: 0.3125em; box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08); margin: 0 10px;"
        src="./README/dep_0001_03.jpg" alt="the depth image">
    </div>
    <div style="border-bottom: 1px solid #d9d9d9; display: inline-block; padding: 0; color: #999"><strong> The RGB image and the corresponding depth image.</strong></div>
</div>

## Model
As in the original repository, `ResNet50` models (CNN) are used for feature extraction, whose input channel is modified to take images of size 4 in the channel dimension as input.

## Install

```bash
pip install -r requirements
```

### Dataset splitting
To split the whole dataset randomly into 3 sub-datasets, (i.e., training dataset, evaluation dataset, test dataset), by generating 3 corresponding csv files to record the paths and labels of each images.

```bash
python preprocess/get_dataset_csv.py
```

After that, the file structure of the data set is as follows. 

```text
vggface3d
|── train.csv
|── eval.csv
|── test.csv
|── dirty.csv
├── n000853
│   ├── 0001_03.npy
│   ├── 0001_03.png
│   ├── 0002_01.npy
│   ├── 0002_01.png
│   ├── 0003_01.npy
│   ├── 0003_01.png
│   ├── 0004_01.npy
│   ├── ......
```

## Predict
Available soon.

