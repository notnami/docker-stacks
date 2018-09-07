FROM notnami/gpupyter:0.2

USER root
RUN apt-get update && apt-get install -y git

USER $NB_UID

RUN conda install --quiet --yes pytorch torchvision cuda92 ipywidgets s3fs \
    tensorflow-gpu keras scikit-learn pandas dask pymongo tqdm -c pytorch -c conda-forge
RUN conda install --quiet --yes spacy && python -m spacy download en
RUN pip install git+https://github.com/pytorch/text.git

ENTRYPOINT ["tini", "-g", "--"]
CMD ["start-notebook.sh"]
