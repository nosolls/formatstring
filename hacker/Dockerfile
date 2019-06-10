# Based on jupyter base notebook
FROM jupyter/base-notebook:61d8aaedaeaf

# File Creator
MAINTAINER Noah Oller Smith <nollersm@purdue.edu>

USER root

# Updates and installs needed packages for user
RUN apt update && \
	apt install -y \
	gcc \
	procps \
	&& apt clean

# Allows user to run certain commands under sudo
ADD hackersudo /etc/sudoers.d/
RUN chmod 0400 /etc/sudoers.d/hackersudo

# Creates Python environtment via conda
RUN conda create --quiet --yes -p $CONDA_DIR/envs/python2 python=2.7 \ 
	ipython ipykernel kernda && conda clean -tipsy

# Create a global kernelspec in the image and modify it so that it 
# properly activates the python2 conda environment.
RUN $CONDA_DIR/envs/python2/bin/python -m ipykernel install && \
    $CONDA_DIR/envs/python2/bin/kernda -o -y \
    /usr/local/share/jupyter/kernels/python2/kernel.json && \
    echo "source activate python2" > ~/.bashrc

# Add the new python2 binaries to the standard path
ENV PATH $CONDA_DIR/envs/python2/bin:$PATH

# Copies files to directory
COPY --chown=1000:100 vul_prog.c $HOME/
COPY --chown=1000:100 write_string.c $HOME/

WORKDIR $HOME

CMD ["start-notebook.sh","--NotebookApp.token="]
