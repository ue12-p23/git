# --------
FROM nbhosting/minimal-notebook

# NOTE
# qpdf is for zlib-flate that we use only in the last optional notebook
RUN true \
 && apt-get install -y qpdf \
 && pip install -U jupyterlab notebook jupytext jupyterlab-myst \
 && pip install -U jupyterlab-courselevels \
 && pip install calysto_bash \
 && true
