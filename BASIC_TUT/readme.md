# Virtual Environment
- virtualenv ENV_NAME
- source ENV_NAME/bin/activate

# Sphinx
- mkdir docs & cd docs
- sphinx-quickstart
- make html

# Git
### Commit to Git
- git add .
- git commit -m "Message"
- git checkout -b NEW_BRANCH_NAME
- git push -u origin Branch Name

### Create Branch
- git checkout -b NEW_BRANCH_NAME

### Switch branch 
- git switch BRANCH_NAME

### Pull
- git pull

# docker
- docker login
- docker build -t docker_image .
- docker run --t image_name /bin/bash
- docker tag image_name user_name/repositary_name
- docker push user_name/repositary_name

