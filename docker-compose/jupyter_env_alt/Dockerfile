FROM jupyter/datascience-notebook

RUN pip install --upgrade pip
RUN pip install jupyterlab
RUN jupyter serverextension enable --py jupyterlab
RUN conda install -c conda-forge nodejs && \
    conda install -c esri arcgis=1.6.2=post1* && \     
    jupyter labextension install @jupyter-widgets/jupyterlab-manager && \
    jupyter labextension install arcgis-map-ipywidget@v1.6.2-post1
RUN pip install jupyter-lsp
RUN jupyter labextension install @krassowski/jupyterlab-lsp && \
    conda install -c conda-forge python-language-server r-languageserver


WORKDIR /workdir
EXPOSE 8888
ENTRYPOINT ["jupyter-lab", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root", "--NotebookApp.token=''"]

CMD ["--notebook-dir=/workdir"]

