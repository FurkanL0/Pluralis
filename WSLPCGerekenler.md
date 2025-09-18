#### Nvidia Toolkit ; 

```bash
sudo apt-get update
sudo apt-get install -y nvidia-cuda-toolkit
```
```bash
nvidia-smi
```
```bash
nvcc --version
```


#### Pyhton ; 
```bash
sudo apt install -y python3-pip
sudo apt install pip
sudo apt install -y build-essential libssl-dev libffi-dev python3-dev
```

#### Conda ; 

```bash
mkdir -p ~/miniconda3
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O ~/miniconda3/miniconda.sh
bash ~/miniconda3/miniconda.sh -b -u -p ~/miniconda3
rm ~/miniconda3/miniconda.sh
```
```bash
source ~/miniconda3/bin/activate
```

```bash
conda init --all
```
