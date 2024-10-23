# Base image
FROM pytorch/pytorch:2.4.0-cuda11.8-cudnn9-devel

# If CUDA is not needed, you can use:
# FROM pytorch/pytorch:2.0.1-cpu

# Set the working directory
WORKDIR /workspace

# Install additional dependencies
RUN apt-get update && apt-get install -y \
    python3-pip \
    && pip install --no-cache-dir \
    pandas \
    numpy \
    scipy \
    scikit-learn \
    matplotlib \
    jupyterlab

# Copy the Jupyter config to the container
COPY jupyter_lab_config.py /root/.jupyter/jupyter_lab_config.py

# Expose the Jupyter port
EXPOSE 8888

# Command to run Jupyter Lab
CMD ["jupyter", "lab", "--ip=0.0.0.0", "--no-browser", "--allow-root"]
