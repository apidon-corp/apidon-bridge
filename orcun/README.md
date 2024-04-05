## TABLE OF CONTENTS
- [APIDON-BRIDGE](#apidon-bridge)
  - [REQUIREMENTS](#requirements)
  - [SETUP AND INSTALLATION](#setup-and-installation)
    - [INSTALL THE NECESSARY PYTHON PACKAGES](#install-the-necessary-python-packages)
    - [START THE FASTAPI SERVER WITH THIS COMMAND](#start-the-fastapi-server-with-this-command)
  - [DOCKER CONTAINER SET-UP](#docker-container-set-up)
    - [HOW TO USE DOCKERFILE](#how-to-use-dockerfile)
  - [KNOWN ISSUES](#known-issues) 
  - [CONCLUSION](#conclusion) 
  - [API FEATURES](#api-features)
    - [MODEL DOWNLOAD AND STORAGE](#model-download-and-storage)
    - [CLASSIFY](#classify)

## APIDON-BRIDGE
APIDON-BRIDGE enables easy deployment of PyTorch, TensorFlow Lite, and TensorFlow models with a FastAPI backend, featuring automatic model download and save functionality.

## API FEATURES

In this section, you can find the API features provided by APIDON-BRIDGE.

### MODEL DOWNLOAD AND STORAGE
APIDON-BRIDGE now includes an API endpoint that allows you to download PyTorch or TensorFlow model files and save them to a specified directory on your computer.

Endpoint: *http://127.0.0.1:8000/upload_model*
When sending a POST request to the /upload_model endpoint, include the following parameters:

*url: The URL where the model file is located.*
*path: The local directory path where you want to save the model file.*


### CLASSIFY
To make predictions on image classification models, you can send a POST request to the following endpoint using Postman or any other HTTP client:

Endpoint: *http://127.0.0.1:8000/classify*
When sending a POST request to the /classify endpoint, include the following parameters:

*model_path_url: The URL where the model file is located.*
*model_extension: The extension of the model file.*
*image_url: The URL of the image you wish to classify.*


## REQUIREMENTS
- Python 3.8 or higher (recommended: 3.10 for optimal compatibility)
- FastAPI
- An HTTP client for API interaction (e.g., Postman, cURL)

## SETUP AND INSTALLATION
First, clone the repository or download the source code to your local machine. Then, follow these steps to set up your environment:

### INSTALL THE NECESSARY PYTHON PACKAGES
```bash
pip install -r requirements.txt
```
START THE FASTAPI SERVER WITH THIS COMMAND
```bash

uvicorn hosting.main:app --reload
```
This command starts a local development server that automatically reloads upon any file changes, making it ideal for development purposes.

## DOCKER CONTAINER SET-UP

For deploying APIDON-BRIDGE on a remote server using Docker, use the provided Dockerfile to build and run the container. The Dockerfile contains all necessary instructions to create a containerized environment for the API.

## HOW TO USE DOCKERFILE
Follow these steps to build and run your Docker container:

Ensure Docker is installed on your machine.
Navigate to the project directory containing the Dockerfile.
Build the Docker image:
```bash

docker build -t <container-name> .
```
Run the Docker container:
```bash

docker run  -p 8000:8000 <container_location>:<local_location> -it <container-name>
```
## KNOWN ISSUES

Users may encounter package-related issues when using the Tensorflow model. To avoid these problems, it is recommended to use Python version 3.10 or 3.11.

CONCLUSION

APIDON-BRIDGE offers a streamlined approach to deploying machine learning models, ensuring ease of access and reliability. The additional feature for downloading and saving model files broadens the utility of the service, making it even more convenient for users managing multiple models. For further assistance or to report issues, please consult the documentation or raise an issue on the project repository.
