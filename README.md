# VoxelNet-Tensorflow

A tensorflow implementation for [VoxelNet](https://arxiv.org/abs/1711.06396).

## Requirement

1. `Python 3.5+`
2. `tensorflow 1.4+`
3. `NumPy`, etc.

## Usage

0. have a look at `config.py` for model configurations, split your data into test/train set by [this](https://xiaozhichen.github.io/files/mv3d/imagesets.tar.gz).
1. run `setup.py` to build the Cython module.
```bash
$ python setup.py build_ext --inplace
```
2. make sure your working directory looks like this (some files are omitted):
```plain
├── build   <-- Cython build file
├── model   <-- some src files
├── utils   <-- some src files
├── setup.py   
├── config.py   
├── test.py   
├── train.py   
├── train_hook.py   
├── README.md    
└── data    <-- KITTI data directory 
    └── object 
        ├── training   <-- training data
        |   ├── image_2   
        |   ├── label_2   
        |   └── velodyne  
        └── testing  <--- testing data
            ├── image_2   
            ├── label_2   
            └── velodyne  
```

3. run `train.py`. Some cmdline parameters is needed, just check `train.py` for them.
4. launch a tensorboard and wait for the training result.

## Data augmentation
Since [c928317](https://github.com/jeasinema/tf_voxelnet/commit/c928317169f1bf23e2157dab20cb402bddb8ffe0), data augmentation is done in an online manner, so there is no need for generating augmented samples.

## Result

TBD

## Acknowledgement

Thanks to [@ring00](https://github.com/ring00) for the implementation of VFE layer and **Jialin Zhao** for the implementation of the RPN.

## License

MIT
