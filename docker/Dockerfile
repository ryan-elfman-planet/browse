FROM continuumio/miniconda3

RUN conda update conda && conda install pip

COPY environment.yml /tmp/environment.yml
RUN conda env update -f /tmp/environment.yml -n base && rm /tmp/environment.yml

COPY . /tmp/stactools-browse
RUN cd /tmp/stactools-browse && pip install . && rm -rf /tmp/stactools-browse

ENTRYPOINT [ "python", "-m", "stactools.cli" ]
