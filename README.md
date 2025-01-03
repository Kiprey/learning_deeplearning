# learning_deeplearning

## Presiqute

- Install miniconda, see [Quick command line install - miniconda](https://docs.anaconda.com/free/miniconda/#quick-command-line-install):

  ```bash
  mkdir -p ~/miniconda3
  wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
  bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
  rm -rf ~/miniconda3/miniconda.sh

  export PATH=$PATH:~/miniconda3/bin
  conda init `basename $SHELL`
  conda --version

  # prepare conda channel
  echo -e "channels:\n  - conda-forge\n  - defaults\nchannel_priority: strict" > ~/.condarc
  ```

- Prepare the Python enviroments and the compiler used for instrumentation:

  ```bash
  conda create -c conda-forge -y --prefix ./venv python=3.12
  source activate ./venv

  # developer use only
  pip install pre-commit
  pre-commit install
  pre-commit run --all-files
  ```