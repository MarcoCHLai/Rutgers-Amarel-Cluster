# Rutgers-Amarel-Cluster

## Amarel cluster access request
Request Amarel cluster access via the link below:  
https://oarc.rutgers.edu/amarel-cluster-access-request/

## Login
Open a terminal application, and log in to the server with your NetID and password.
```bash
ssh <NetID>@amarel.rutgers.edu  # replace <NetID> with your own
```

## Data transfer
- Upload data to the server
```bash
scp -r <local_path> <NetID>@amarel.rutgers.edu:<hpc_path>
```

- Download data from the server
```bash
scp -r <NetID>@amarel.rutgers.edu:<hpc_path> <local_path>
```

## Setup Conda environment
See the Conda section in the Amarel cluster user guide:  
https://sites.google.com/view/cluster-user-guide/amarel/applications#h.rb853r90bnus  
<br>

## Launch Jupyter Notebook on the cluster
Tutorial from Princeton: https://researchcomputing.princeton.edu/support/knowledge-base/jupyter
<br>

- After logging into the server, request a compute node. The example below requests a node with 1 CPU and 4 GB of memory for 2 hours.  
```bash
ssh <NetID>@amarel.rutgers.edu
srun --cpus-per-task=1 --mem=4G --time=02:00:00 --pty /bin/bash
```
<br>

- Run the ```hostname``` command to get the name of the node.
<img width="900" alt="cluster_jupyter00" src="https://github.com/user-attachments/assets/13e7c859-951b-4021-9663-fe600d4c5621" />
<br><br>

- Activate the Conda environment.
```bash
conda activate <environmant name>
```
<br>

- Launch Jupyter Notebook using the following command:
```bash
jupyter-notebook --no-browser --port=8889 --ip=0.0.0.0
```
<br>

- Open a new terminal, type the following command, and then enter your password.
```bash
ssh -N -f -L 8889:<hostname>:8889 <NetID>@amarel.rutgers.edu
```
<img width="900" alt="cluster_jupyter01" src="https://github.com/user-attachments/assets/d9c118d6-33b1-4126-8064-e54fa6ba1a5d" />
<br><br>

- Copy the link from the terminal where Jupyter Notebook was launched.
<img width="900" alt="cluster_jupyter02" src="https://github.com/user-attachments/assets/a00850c5-e2e9-47e3-b880-2c2ecf5a2bf5" />
<br><br>

- Paste the link into a browser.
<img width="900" alt="cluster_jupyter03" src="https://github.com/user-attachments/assets/cc4ebded-9b45-482b-b42d-c082ba451ed1" />

## Github basics
- Clone a repository
```bash
git clone <repository_url>
```
<br>

- The git config --global command is used to set configuration options that apply to all Git repositories for the current user on a given system.
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```
<br>

- The git status shows the current state of your Git working directory and staging area.
```bash
git status
```
<br>

- The git add command adds new or changed files in your working directory to the Git staging area.
```bash
git add <file_name>
git commit -m "commit message"
```
<br>

- The git push command is used to upload local repository content to a remote repository. 
```bash
git push <remote_name> <branch_name>
```
<br>
