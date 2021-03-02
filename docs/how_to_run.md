> Refer this file after you have the necessary environment for running the model.

# Files to be used

![](/home/gunjan/Pictures/Screenshot from 2021-03-02 20-22-43.png)

**cwgan** folder can be downloaded from this GitHub repository.

You would be having 4 data sets with you namely

- Middlebury_GT.zip 
- Middlebury_Hazy.zip 
- NYU_GT.zip
- NYU_Hazy.zip

**organise_folder.ipynb** can be downloaded from the following link

https://drive.google.com/file/d/1izJ0wFeZ5jZeq3ktJBHHMf7wEfZP6g0v/view?usp=sharing

Run the python notebook **organise_folder.ipynb**

After you run the python notebook a folder named  **D-HAZY_DATASET** would be created which consists of required unzipped files.

Train the model using following command 

Here it is assumed that you are in the **cwgan** folder.

```python
python train.py --dataroot ../D-HAZY_DATASET --name DHaze_Dataset_Haze_Removal --model pix2pix --dataset_mode unaligned --no_flip 
```

