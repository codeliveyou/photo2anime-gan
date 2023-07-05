# Photo to Anime
A Tensorflow implementation of AnimeGAN for fast photo animation ! &ensp;&ensp;&ensp;&ensp;  

-----
**Some suggestions:**
1. since the real photos in the training set are all landscape photos, if you want to stylize the photos with people as the main body, you may as well add at least 3000 photos of people in the training set and retrain to obtain a new model.  
2. In order to obtain a better face animation effect, when using 2 images as data pairs for training, it is suggested that the faces in the photos and the faces in the anime style data should be consistent in terms of gender as much as possible.  
3. The generated stylized images will be affected by the overall brightness and tone of the style data, so try not to select the anime images of night as the style data, and it is necessary to make an exposure compensation for the overall style data to promote the consistency of brightness and darkness of the entire style data.  

**News:**   
&ensp;&ensp;&ensp;&ensp;&ensp;  ***photo2anime-gan2*** has been released and can be accessed [here](https://github.com/codeliveyou/photo2anime-gan2).  
```yaml
The improvement directions of AnimeGANv2 mainly include the following 4 points:
```
&ensp;&ensp; 1. Solve the problem of high-frequency artifacts in the generated image.  
&ensp;&ensp; 2. It is easy to train and directly achieve the effects in the paper.  
&ensp;&ensp; 3. Further reduce the number of parameters of the generator network.  
&ensp;&ensp; 4. Use new high-quality style data, which come from BD movies as much as possible.  

___

## Requirements  
- python 3.7  
- tensorflow-gpu 1.15.0 (ubuntu, GPU 2080Ti, cuda 10.0.130, cudnn 7.6.0)  
- opencv  
- tqdm  
- numpy  
- glob  
- argparse  
  
## Usage  
### 1. Inference  
  e.g.  `python test.py --checkpoint_dir checkpoint/generator_Hayao_weight --test_dir dataset/test/real --style_name H`
    
### 2. Convert video to anime  
  e.g. `python video2anime.py  --video video/input/a.mp4  --checkpoint_dir  ./checkpoint/generator_Hayao_weight`  

#### 3. Do edge_smooth  
   e.g. `python edge_smooth.py --dataset Hayao --img_size 256`  
  
#### 4. Train
   e.g. `python train.py --dataset Hayao  --epoch 101 --init_epoch 5`  
  
#### 5. Extract the weights of the generator  
   e.g. `python get_generator_ckpt.py --checkpoint_dir  ../checkpoint/AnimeGAN_Hayao_lsgan_300_300_1_1_10  --style_name Hayao`  

____
## Acknowledgment  
This code is based on the [CartoonGAN-Tensorflow](https://github.com/taki0112/CartoonGAN-Tensorflow/blob/master/CartoonGAN.py) and [Anime-Sketch-Coloring-with-Swish-Gated-Residual-UNet](https://github.com/pradeeplam/Anime-Sketch-Coloring-with-Swish-Gated-Residual-UNet). Thanks to the contributors of this project.  

