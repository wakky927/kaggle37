# kaggle37

## How to build
`docker build -t <tag_name> -f <docker_file_path> .`

## How to run image
`docker run -it --gpus all -v <local_data_path>:<container_data_path> -p 8888:8888 <tag_name>`

## How to run jupyter lab
`jupyter lab --ip=0.0.0.0 --allow-root --LabApp.token=''`

## How to access
localhost:8888 on browser

## How to conda env
`conda env create -f venv.yaml` & `conda activate venv`
