FROM jupyter/scipy-notebook:python-3.7.12

RUN conda install -y -c conda-forge dask[distributed] dask-kubernetes boto3 tensorflow graphviz mimesis 
RUN mkdir $HOME/bin

RUN wget https://dl.min.io/client/mc/release/linux-amd64/mc \
  -O $HOME/bin/mc \
  && chmod +x $HOME/bin/mc
RUN echo "export PATH=\$PATH:\$HOME/bin/" >> ~/.bashrc

RUN python -m pip install git+https://github.com/argoproj-labs/hera-workflows --ignore-installed

RUN wget https://github.com/argoproj/argo-workflows/releases/download/v3.4.3/argo-linux-amd64.gz \
    && gunzip argo-linux-amd64.gz \
    && chmod +x argo-linux-amd64 \
    && mv ./argo-linux-amd64 $HOME/bin/argo

CMD ["jupyterlab"] 
#COPY demo.ipynb $HOME/demo.ipynb