# How to make, update, or add to this repository

## Make the new repository content

### Orchestrator Charts
```
cd ~
git clone https://github.com/cmusatyalab/magma-charts
git clone https://github.com/magma/magma # substitute your preferred fork/branch of magma
cd magma/orc8r/cloud/helm/orc8r
# edit/modify charts as needed then update dependencies
helm dependency update
# package the charts
cd ..
helm package orc8r
mv orc8r-<RELEASE>.tgz ~/magma-charts/
cd ~/magma-charts
# backup the current index file
cp index.html index.html.bak
helm repo index .
git add -A
git commit -m "new orc8r package"
git push
```

