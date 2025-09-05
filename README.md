# Rutgers-Amarel-Cluster

## Amarel cluster access request
Request Amarel cluster access via the link below:  
https://oarc.rutgers.edu/amarel-cluster-access-request/

## Login
Open a terminal application, and log in to the server with your NetID and password.
```bash
$ ssh <NetID>@amarel.rutgers.edu  # replace <NetID> with your own
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
Youtube tutorial: https://www.youtube.com/watch?v=qvGs35QX6Ss  
<br>

- After logging into the server, request a compute node.
```bash
srun --cpus-per-task=1 --mem=4GB --time=02:00:00 --pty /bin/bash
```
The example above requests a node with 1 CPU and 4 GB of RAM for 2 hours.  
<br>

- Activate the Conda environment.
```bash
conda activate <environmant name>
```
<br>

- Launch Jupyter Notebook using the following command:
```bash
jupyter notebook --no-browser --ip=127.0.0.1 --port=8890
```
<br>

- Open a new terminal, type the following command, and then enter your password.
```bash
ssh -N -f -L localhost:8890:localhost:8890 <NetID>@amarel.rutgers.edu
```
<img alt="terminal_screenshot1" src="https://github.com/user-attachments/assets/11d4cc74-6f9b-4760-9429-fe98062da102" />  
<br><br>

- Copy the link from the terminal where Jupyter Notebook was launched, and paste the link into a browser.
<img alt="terminal_screenshot2" src="https://github.com/user-attachments/assets/ee3323d0-7df8-46b2-a051-969b3c631e92" />  
<br><br>

## Github basics
- Cone a repository
```bash
git clone <repository_url>
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
git commit -m "commit message about the command line"
```
<br>

- The git push command is used to upload local repository content to a remote repository. 
```bash
git push <remote_name> <branch_name>
```
<br>
