# CovScript Package Manager Sources
This is official maintained CSPKG source in GitHub. We will sync contributions to this repo to main repository site.
## Main Repository Site
http://mirrors.covariant.cn/cspkg/
## How to build a mirror site
```
#!/bin/bash
# Settings of Sync Script
external_url='http://127.0.0.1/mirrors/cspkg/'
local_path='/var/www/html/mirrors/cspkg'

rsync -avz mirrors.covariant.cn::cspkg $local_path
find -name '*.json' | xargs perl -pi -e \
  "s|http://mirrors.covariant.cn/cspkg/|$external_url|g"
```
You need to install `rsync` and `perl` first.