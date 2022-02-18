# I2b2 Docker Image

This folder contains an i2b2 Docker image which loads its data structure at the first startup and with test data.
It is configurable through environment variables and easily customisable, either with patches to the source code or with
tweaks to the data loaded. 

## Source code organization
- `patches/`: (see README.md)[patches/README.md]
- `pre-init-scripts/`: (see README.md)[pre-init-scripts/README.md]
- `sql/`: (see README.md)[sql/README.md]
- `docker-entrypoint.sh`: entrypoint for the docker container, it waits for the
  database to be available and then triggers the data loading if needed before starting i2b2
- `Dockerfile`: the dockerfile defining the image
- `download-i2b2-sources.sh`: scripts used during the image build that downloads the i2b2 source code and its data definitions
- `I2b2PasswordHash.java`: a Java snippet that replicates the password hashing function of i2b2, allowing to set i2b2
  passwords directly in the database
- `install-i2b2.sh`: script that compiles and install i2b2 in the docker image at build time
