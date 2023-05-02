# ds-images
Templates for data science images  
Base image is jupyter/scipy-notebook [Jupyter Docker Stack](https://jupyter-docker-stacks.readthedocs.io/en/latest/using/selecting.html)

```
# cp setup.sh work/
docker run --rm --name ts -p 8889:8888 -v $(pwd):/home/jovyan/work dsml4s8e bash setup.sh
```


