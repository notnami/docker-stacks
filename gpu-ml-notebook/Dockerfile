FROM notnami/gpupyter

RUN conda install --quiet --yes pytorch torchvision cuda91 \
    tensorflow-gpu keras scikit-learn -c pytorch

ENTRYPOINT ["tini", "-g", "--"]
CMD ["start-notebook.sh"]

USER $NB_UID

