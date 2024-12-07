The following code in this repo allows to run an RL experiment with StandardBaselines3. In Nautilus: mkdir -p Downloads/persistent/miniconda3 wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -O Downloads/persistent/miniconda3/miniconda.sh bash Downloads/persistent/miniconda3/miniconda.sh -b -u -p Downloads/persistent/miniconda3 rm -rf Downloads/persistent/miniconda3/miniconda.sh

Downloads/persistent/miniconda3/bin/conda init bash Downloads/persistent/miniconda3/bin/conda init zsh

source ~/.bashrc source ~/.zshrc

Downloads/persistent/miniconda3/bin/conda create -n carla python=3.8 -y

source Downloads/persistent/miniconda3/bin/activate carla

sudo wget https://carla-releases.s3.us-east-005.backblazeb2.com/Linux/CARLA_0.9.15.tar.gz -P Downloads/persistent sudo mkdir -p Downloads/persistent/CARLA_LATEST echo "Extracting Carla to Downloads/persistent/CARLA_LATEST/" sudo tar -xvf Downloads/persistent/CARLA_0.9.15.tar.gz -C Downloads/persistent/CARLA_LATEST > /dev/null sudo rm Downloads/persistent/CARLA_0.9.15.tar.gz

pip3 install carla

cd Downloads/persistent/CARLA_LATEST/PythonAPI/examples

python3 -m pip install -r requirements.txt

pip install stable-baselines3 pip install tensorflow pip install opencv-python

cd ~ cd ~/persistent/CARLA_LATEST ./CarlaUE4.sh -carla-rpc-port=2000 -norelativemousemode

To open VSCode IDE in Nautilis, open new tab:

sudo apt update sudo apt install software-properties-common apt-transport-https wget -y wget -q https://packages.microsoft.com/keys/microsoft.asc -O- | sudo gpg --dearmor -o /usr/share/keyrings/packages.microsoft.gpg echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list sudo apt update sudo apt install code -y

write in "code" conda activate [env-name] in IDE terminal python train.py

