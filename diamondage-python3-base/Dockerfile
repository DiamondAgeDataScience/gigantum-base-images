FROM jupyter/scipy-notebook

ENV JUPYTER_ENABLE_LAB yes
ENV RESTARTABLE yes

USER root
RUN apt-get update
RUN apt-get -y install \
    xvfb \
    libxtst6 \
    libgconf-2-4

USER jovyan
RUN conda update -n base conda
RUN conda install -c plotly \
    plotly-orca \
    plotly \
    plotly_express \
    psutil
RUN conda install \
    seaborn \
    scikit-learn \
    statsmodels \
    numba \
    pytables
RUN conda install -c conda-forge \
    python-igraph \
    louvain \
    jupytext
RUN conda install -c bioconda scanpy
RUN pip install \
    scikit-plot \
    plotly_express
RUN conda update jupyterlab
ENV NODE_OPTIONS --max-old-space-size=4096
RUN jupyter labextension install @jupyter-widgets/jupyterlab-manager --no-build
RUN jupyter labextension install plotlywidget --no-build
RUN jupyter labextension install jupyterlab-plotly --no-build
RUN jupyter labextension install @karosc/jupyterlab_dracula --no-build
RUN jupyter lab build
ENV NODE_OPTIONS ""