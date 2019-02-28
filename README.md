# WPCD Workflows documentation

Migrated eufus.eu documentation available as http://wpcd-workflows.github.io/ and http://wpcd-workflows.readthedocs.io/ (autobuild without assets at this point)

To commit to this repository user needs to become Collaborator 
and to create "personal access token" with *admin:repo_hook, public_repo, repo:status* 
at your https://github.com/settings/tokens page.

Created TOKEN is then used as a user/password for HTTPS access to the repository.

To clone please use:

    git clone https://TOKEN@github.com/WPCD-Workflows/documentation.git wpcd-doc
    
    
To change the TOKEN or remote URL:

    git remote set-url origin https://TOKEN@github.com/WPCD-Workflows/documentation.git

To commit large files to the https://github.com/WPCD-Workflows/assets repository use 

    make push asset=your.file
    make push asset=source/static/Phase4.10b.8_HTML.zip
    make push asset='source/archive/*.zip'
    
If using new location for large files then edit ASSETS wildcard in Makefile

## Building documentation

    make html
    
## Publishing documentation

Unless the directory is cloned firstly a local directory WPCD-Workflows.github.io 
will be created and the content of the HTML documentation can be viewed with

    xdg-open ../WPCD-Workflows.github.io/index.html
    
To be able to push documentation remove WPCD-Workflows.github.io and 

    git clone https://USER:TOKEN@github.com/WPCD-Workflows/WPCD-Workflows.github.io.git
   
at the same level as wpcd-doc. To push everything therein use:

    git add .
    git commit -m "Updated public documentation"
    git push
