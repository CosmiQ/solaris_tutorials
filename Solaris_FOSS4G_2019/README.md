<p align="center">
<img src="https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/foss4g_solaris.png" width="650" alt="Powered by Solaris">
</p>

# Materials for the `solaris` workshop at FOSS4G International 2019

This directory comprises the materials for the FOSS4G 2019 Workshop at FOSS4G 2019.

## Notes for workshop participants

All workshop participants will be provided with access to a Jupyter Notebook running an AWS EC2 P3.2xlarge instance with Solaris and all of its dependencies pre-installed, so you won't need to install these materials on your own computer; just bring your computer with you and make sure you have configured the FOSS4G wifi so you can access the notebooks. The relevant files from this repository as well as the data files you'll use for model training will be pre-installed within your instance.

## Notes for non-workshop participants

This workshop uses a number of files from the [SpaceNet Datasets](https://spacenet.ai) which are not included within the repository. Specifically, you'll need to add a few subdirectories to the `data` folder here, and update a few of the paths in config and .csv files under `data/workshop_configs`. The instructions for doing so are below.

#### Data preparation for use within the notebooks:

1. [Download the Khartoum training dataset from the SpaceNet AWS S3 bucket](http://s3.amazonaws.com/spacenet-dataset/spacenet-dataset/SpaceNet_Buildings_Dataset_Round2/spacenetV2_Train/AOI_5_Khartoum_Train.tar.gz) __5 GB download__
2. Create a directory under the `data` folder called `Khartoum_data`
3. Decompress the tarball that you downloaded
4. Move the `RGB-PanSharpen` directory from the new `AOI_5_Khartoum_Train` directory from the tarball into the `Khartoum_data` directory, and rename it `RGB_imagery`
5. Copy the `buildings` directory from the `AOI_5_Khartoum_Train/geojson` directory into the `Khartoum_data` directory, and rename it `geojson`
6. Open each .yml file under workshop_configs and update the `inference_data_csv` value to point correctly to the file in your data folder.
7. In the `xdxd_workshop_khartoum_train.yml` file, change the `training_data_csv` path to point correctly to the corresponding file in your data folder.
8. Open the CSV files and update the `/data` paths to point instead to wherever you've stored the `data` directory.
9. In the first code cell of each Jupyter notebook, the variable `data_path` is assigned to `/data`. You'll need to update this to point to your data path.

#### `solaris` installation
You'll need to have `solaris` [installed](https://solaris.readthedocs.io/en/latest/installation.html) to run the code contained within these notebooks.

#### Compute resources
All of these notebooks _can_ be run on a laptop; however, the re-training step in `4_fine_tuning_a_spacenet_model.ipynb` is _extremely_ slow (likely >1 day) without access to a GPU. If you lack GPU compute resources, we recommend you simply follow along through the end of that notebook rather than re-training from scratch.

__Even if you have GPU resources, they may not have enough GPU memory to hold some of the models within these notebooks__. These models were trained on 2xTitan Xp GPUs with a total of 24 GB GPU memory. If you find yourself encountering GPU errors, you can [modify the YAML config files](https://solaris.readthedocs.io/en/latest/tutorials/notebooks/creating_the_yaml_config_file.html) in the `data/workshop_configs` directory to reduce the batch size of the models. Though this will change performance subtly and slow training down somewhat, it should allow you to complete the tutorials.

#### Recommended order

We recommend you go through the contents of this workshop in the following order:
1. [CosmiQ_Solaris_FOSS4G_Workshop_Intro.pdf](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/CosmiQ_Solaris_FOSS4G_Workshop_Intro.pdf)
2. [1_intro_to_solaris.ipynb](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/1_intro_to_solaris.ipynb)
3. [2_under_the_hood.ipynb](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/2_under_the_hood.ipynb) When that suggests you pause to look at slides, check out
4. [CosmiQ_Solaris_Inference_Intro.pdf](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/CosmiQ_Solaris_Inference_Intro.pdf), then go back to 2_under_the_hood.ipynb.
5. [3_evaluating_performance.ipynb](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/3_evaluating_performance.ipynb)
6. [CosmiQ_Solaris_Evaluating_Perfomance.pdf](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/CosmiQ_Solaris_Evaluating_Perfomance.pdf), then back to 3_evaluating_performance.ipynb
7. [CosmiQ_Solaris_Training_Intro.pdf](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/CosmiQ_Solaris_Training_Intro.pdf)
8. [4_fine_tuning_a_spacenet_model.ipynb](https://github.com/CosmiQ/solaris_tutorials/blob/master/Solaris_FOSS4G_2019/4_fine_tuning_a_spacenet_model.ipynb). Note that model re-training within this notebook takes a lot of computing power, but the results are pre-filled so you can follow along even if you don't have access.
