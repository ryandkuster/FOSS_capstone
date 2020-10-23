# FOSS_capstone
Capstone project for FOSS 2020 workshop


### Set up instance in Cyverse Atmosphere
- Used instance "Ubuntu 18_04 NoDesktop Base"
- large2 (CPU: 8, Mem: 48 GB, Disk: 320 GB root)



```
# Log Into Atmosphere
ssh <cyverse user name>@<Instance IP address>

# Set super user
sudo su

# Connect to Data Store using Cyverse credentials
iinit
#host name = data.cyverse.org
#port number = 1247
#zone = iplant

# Check mounted volumes
df -h 

# cd into /scratch
cd /scratch
ls

# Connect to github
git clone https://github.com/lizsuter/FOSS_capstone.git


```

### Install Conda, Jupyterlab, Docker 
- Using instructions from [Foss Reproducibility Tutorial](https://learning.cyverse.org/projects/cyverse-cyverse-reproducbility-tutorial/en/latest/step2.html#install-conda)

### Back up to github
```
git status

# commit changes with a helpful message
git commit -am "update readme"

#push changes to github
git push
```


#### Test out RStudio+ Tidyverse docker

```
cd FOSS_capstone

# make a testfile
touch test.file
cd ..

# launch the container,  see if you can see the test.file
docker run -v /scratch/FOSS_capstone/:/home/rstudio/work -e PASSWORD=rstudio1 -p 8787:8787 rocker/tidyverse


```

- **If on local computer** go to `http://localhost:8787/`  
- **If on VM** go to `http://INSTANCE_IP_ADDRESS:8787/`
- rstudio and rstudio1 are the user name/ password
- make sure to Ctl+C to quit the docker image, or it will still be running even if you close the window


### Next Steps
- Make a bash script?
	- set up environment/ get data
		- list data files in a gitignore file?
	- launch RStudio Docker with Tidyverse
	- Installing some R tool and running an R script?
