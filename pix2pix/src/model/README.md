# Training and evaluating

## Training

`python main.py`


positional arguments:
    
    patch_size            Patch size for D

optional arguments:

    -h, --help            show this help message and exit
    --backend BACKEND     theano or tensorflow
    --dset DSET           facade
    --batch_size BATCH_SIZE
                        Batch size
    --n_batch_per_epoch N_BATCH_PER_EPOCH
                        Number of training epochs
    --nb_epoch NB_EPOCH   Number of batches per epoch
    --epoch EPOCH         Epoch at which weights were saved for evaluation
    --nb_classes NB_CLASSES
                        Number of classes
    --do_plot DO_PLOT     Debugging plot
    --bn_mode BN_MODE     Batch norm mode
    --img_dim IMG_DIM     Image width == height
    --label_smoothing LABEL_SMOOTHING
                        Whether to smooth the positive labels when training D
    --label_flipping LABEL_FLIPPING
                        Probability (0 to 1.) to flip the labels when training
                        D
    --use_mbd USE_MBD     Whether to use minibatch discrimination

**Example:**

`python main.py 64 64`


### Expected outputs:

- Weights are saved in  pix2pix/models
- Figures are saved in  pix2pix/figures
- Save model weights every few epochs

## Notes:

- Upsampling is used instead of transposed convolutions
- The image dimension must be a multiple of the patch size (e.g. 256 is a multiple of 64)
- In the discriminator, each patch goes through the same feature extractor. Then the outputs are combined with a new dense layer + softmax