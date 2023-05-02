# ds-images
Templates for data science images  
Base image is jupyter/scipy-notebook [Jupyter Docker Stack](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html)

```
docker run --rm --name ts --gpus all -p 8889:8888 -v ${pwd}:/home/jovyan/work ts bash setup.sh
```


