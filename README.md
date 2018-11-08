Work-in-progress port of [MzS Tools](https://github.com/CNR-IGAG/mzs-tools) to QGIS 3.

## Development setup

- Install [pipenv](https://pipenv.readthedocs.io/en/latest/install/#installing-pipenv)

    ```bash
    pip3 install pipenv --user
    ```

- Clone or download repository

- Install dependencies and create virtualenv

    ```bash
    cd mzs-tools-qgis3
    pipenv install --dev
    ```

- Activate virtualenv

    ```bash
    pipenv shell
    ```

- Set your QGIS plugins folder in `pb_tool.cfg`

    ```
    plugin_path: /your/.local/share/QGIS/QGIS3/profiles/default/python/plugins
    ```

- Use [pb_tool](http://g-sherman.github.io/plugin_build_tool/)

    ```bash
    pb_tool validate
    pb_tool compile

    # deploy in the qgis plugin folder
    pb_tool deploy
    ```

### Caveats

- On Ubuntu some packages should be installed:

    ```bash
    sudo apt install python3-pip virtualenv python3-venv qttools5-dev-tools
    ```

- Sphinx autodoc function likely requires to set the path to system libraries in `conf.py`:

    ```python
    sys.path.insert(0, '/usr/lib/python3/dist-packages/')
    extensions = [..., 'sphinx.ext.autodoc']
    ```
