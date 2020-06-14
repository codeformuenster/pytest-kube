[![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/codeformuenster/pytest-kube)](https://cloud.docker.com/u/codeformuenster/repository/docker/codeformuenster/pytest-kube/builds)

# pytest-kube


```bash
docker build -t local/pytest-kube .

docker run -ti \
  -v /var/run/docker.sock:/var/run/docker.sock \
  --network host \
  -v $PWD:/pytest \
  local/pytest-kube
```


## Hints for development

```bash
# add a python package to pyproject.toml
docker run -ti -v $PWD:$PWD -w $PWD -- local/pytest-kube \
  poetry add --dev git+https://github.com/hjacobs/pytest-kind@master

# update package versions in pyproject.toml
docker run -ti -v $PWD:$PWD -w $PWD -- local/pytest-kube \
  poetry update
```
