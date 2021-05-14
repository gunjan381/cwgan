### Files to be used

**cwgan** folder can be downloaded from this GitHub repository.

You would be having 4 data sets with you namely

- Middlebury_GT.zip 
- Middlebury_Hazy.zip 
- NYU_GT.zip
- NYU_Hazy.zip

### Creating the datasets

Create folder `/path/to/data` with subdirectories `A` and `B`. `A` and `B` should each have their own subdirectories `train`, `val`, `test`, etc. In `/path/to/data/A/train`, put training images in style A. In `/path/to/data/B/train`, put the corresponding images in style B. Repeat same for other data splits (`val`, `test`, etc).

Corresponding images in a pair {A,B} must be the same size and have the same filename, e.g., `/path/to/data/A/train/1.jpg` is considered to correspond to `/path/to/data/B/train/1.jpg`.

Once the data is formatted this way, call:

```bash
python datasets/combine_A_and_B.py --fold_A /path/to/data/A --fold_B /path/to/data/B --fold_AB /path/to/data
```

This will combine each pair of images (A,B) into a single image file, ready for training.



#### For training the model for 100 epoch

The results would be saved in the **checkpoints** directory.

```python
python train.py --dataroot /path/to/data --name haze_to_unhaze --niter 60 --niter_decay 40 --model pix2pix --netG unet_256
```



