<h1 align="center">
    conda-setup
</h1>
<p align="center">
     <em>
          Miniconda3 installation and configuration script
     </em>
</p>
<p align="center">
    <a href="https://github.com/theo-brown/conda-setup/blob/main/LICENSE">
        <img src="https://img.shields.io/github/license/theo-brown/conda-setup">
    </a>
    <img src="https://img.shields.io/maintenance/yes/2022">
</p>

**conda-setup** is a shell script to help you install and configure Miniconda.
It offers a number of configurable options:
- Choose between global/local install
- Set install location
- Select base Python version
- Enable/disable automatic activation of the base environment
- Show/hide the environment prompt for the base environment
- Choose whether to run `conda init` or to perform manual setup

The script defaults to running in an interactive mode, where the user is prompted to set each option.
Non-interactive mode is also available, and options can be set by running the script with specific flags.

### Quickstart
Interactive mode:
```
bash <(curl -s theobrown.uk/setup/conda)
```
Non-interactive mode:
```
curl -s theobrown.uk/setup/conda | bash -s -- -q ...
```
Where `...` is replaced with additional flags you want set. If none are set, the defaults will be used.

### Defaults
The default options will:
- Install Miniconda to `~/.miniconda3`, unless an existing conda installation exists
- Install the default Python version set by Miniconda
- Run `conda init` to set up the shell

### Detailed Usage
```
  conda-setup [-f | --force] [-g | --global] [-h | --help] [-q | --quiet] [-s | --silent]
              [-d DIR | --install-dir DIR] [-p VER | --python-version VER]
              [-B | --hide-base] [--no-auto-activate] [--no-init]
```

| Short flag | Long flag            | Description                                                                                   |
|:-----------|:---------------------|:----------------------------------------------------------------------------------------------|
| `-f`       | `--force`            | If conda is already installed at the specified install location, overwrite it                 |
| `-g`       | `--global`           | Install conda system-wide, equivalent to `conda-setup -d /opt`                                |
| `-h`       | `--help`             | Print help message                                                                            |
| `-q`       | `--quiet`            | Non-interactive mode - run without prompt and use defaults for any options not set with flags |
| `-s`       | `--silent`           | Silent mode - suppress all output, and use defaults for any options not set with flags        |
| `-d DIR`   | `--install-dir DIR`  | Install conda to the given location; it will be found at `$DIR/miniconda`        |
| `-p VER`   | `--python VER`       | Install the specified version of Python (default: Miniconda's default Python version)         |
| `-B`       | `--hide-base`        | Hide `(base)` in shell prompt (for non-base environments it will still appear)                |
|            | `--no-auto-activate` | Disable automatic activation of base environment
|            | `--no-init`          | Don't run `conda init` after installation
