FROM continuumio/anaconda3

RUN apt-get update
RUN apt-get install build-essential -y
RUN apt-get install swig -y

RUN /opt/conda/bin/conda install gxx_linux-64 gcc_linux-64
RUN /opt/conda/bin/conda install jupyter -y --quiet 
RUN pip install pyarrow
RUN pip install fastparquet
RUN pip install emcee scikit-optimize pyDOE
RUN pip install auto-sklearn

# Install other ML open source librairies
RUN pip install xgboost
RUN pip install lightgbm

# Install kxy
RUN pip install kxy==0.2.4

# Copy examples into the Notebooks folder
RUN git clone https://github.com/kxytechnologies/kxy-python.git /opt/kxy-python
RUN mkdir /opt/notebooks
RUN cp -R /opt/kxy-python/docs/latest/examples/* /opt/notebooks/
