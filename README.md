# Rutgers-Amarel-Cluster

## Amarel cluster access request
Request Amarel cluster access via the link below:  
https://oarc.rutgers.edu/amarel-cluster-access-request/

## Login
Open a terminal application and log in to the server using your NetID and password.

```bash
$ ssh <NetID>@amarel.rutgers.edu    # replace <NetID> with your own
```

## Data transfer
upload data to the server
```bash
scp -r <local directory> <NetID>@amarel.rutgers.edu:<hpc directory>
```

download data from the server
```bash
scp -r <NetID>@amarel.rutgers.edu:<hpc directory> <local directory>
```

## Setup Conda environment
Follow the Conda section in the Amarel cluster user guide:  
https://sites.google.com/view/cluster-user-guide/amarel/applications#h.rb853r90bnus

