# learning_human_attention
Repository of the work "Enhancing Robot Learning through Learned Human-Attention Feature Maps".

The docker image of our preprocessing pipeline is provided on Dockerhub and can be downloaded using the following command:

sudo docker pull cyberwyrm/eye-tracking_pipeline:latest

To build and run the container, execute the following commands using the synopsis below:

sudo docker build -t cyberwyrm/eye-tracking_pipeline .

sudo docker run -v <raw_data_src_path_host_abs>:/raw_data/dataset -it eye-tracking_pipeline:latest

<raw_data_src_path_host_abs> refers to the absolute path on the host file system where the raw data to be processed is located. The preprocessed data is then stored along each run's folder and given by 
the marked_frames directory which contains all images and the transformed_coords.csv file which contains the attention information for each corresponding frame.
