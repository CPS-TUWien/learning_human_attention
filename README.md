# Learning Human Attention
This is the repository of the work "Enhancing Robot Learning through Learned Human-Attention Feature Maps".

We provide instruction to work with the experimental data recorded in
driving tasks with F1TENTH miniature vehicles.

![experimental setup](docs/exp-setup.png)

# Download the raw dataset

The recorded data are freely available on Zenodo at [put-here-link](put-here-link).

We describe in the following the data content, its organization 
and report the instruction to download them.



# Preprocess the data

To process the raw data and map the focus points from the eye-tracking systems
into the view from the on-board camera, we perform a coordinate projection.

To reproduce the preprocessing, we provide the following docker image `cyberwyrm/eye-tracking_pipeline`.

![docker image](docs/docker-img.png)


### Instructions

1. Pull the docker image from Dockerhub
```
docker pull cyberwyrm/eye-tracking_pipeline:latest
```

2. Run the container from the folder containing the dataset (_see instructions above to download the data_)
```
docker run -v <path-to-dataset-folder>:/raw_data/dataset --name eye-tracking_pipeline cyberwyrm/eye-tracking_pipeline:latest
```

where `<path-to-dataset-folder>` is the absolute path on the host file system where the raw data are located. 

### Output description

The output of the processing pipeline is produced and stored for each run in the relative folder. 
The output consists of:
- `marked_frames` directory: contains all frame images,
- `transformed_coords.csv` file: contains the focus points for each frame.

# Citation
If you find this work useful for your own ideas, please cite our paper:

```
@online{scheuchenstuhl2023enhancing,
    title={Enhancing Robot Learning through Learned Human-Attention Feature Maps}, 
    author={Daniel Scheuchenstuhl and Stefan Ulmer and Felix Resch and Luigi Berducci and Radu Grosu},
    booktitle = {Workshop on effective Representations, Abstractions, and Priors for Robot Learning (ICRA 2023)},
    year={2023}
}
```

