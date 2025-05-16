FROM kernel

RUN pip install --no-cache-dir jupyterlab ipykernel

RUN python -m ipykernel install --user --name python-prod --display-name 'Python (Production Env)'

CMD jupyter lab --ip=0.0.0.0 --port=8888 --allow-root --no-browser --ServerApp.token=''
