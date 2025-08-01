# System Requirements [Click Here](https://github.com/AdityaNarayan02/Gensyn-Node/blob/main/README.md#system-requirements)

# Install Dependencies

**1. Update System Packages**
```bash
sudo apt-get update && sudo apt-get upgrade -y
```
**2. Install General Utilities and Tools**
```bash
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```

**3. Install Docker**
```bash
# Remove old Docker installations
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove $pkg; done

# Install dependencies
sudo apt install apt-transport-https ca-certificates curl software-properties-common -y

# Add Docker’s official GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Set up the stable Docker repository
echo \
  "deb [arch="$(dpkg --print-architecture)" signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  "$(. /etc/os-release && echo "$VERSION_CODENAME")" stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null


# Install Docker
sudo apt install docker-ce docker-ce-cli containerd.io -y

# Verify Docker installation
sudo docker --version

# Start and enable Docker
sudo systemctl enable docker
sudo systemctl start docker

# Run Docker without sudo (optional)
sudo usermod -aG docker $USER

# Test Docker installation
docker run hello-world

```
**4. Install Python**
```bash
sudo apt-get install python3 python3-pip python3-venv python3-dev -y
```

**5. Install Node**
```
sudo apt-get update
```
```
curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
```
```
sudo apt-get install -y nodejs
```
```
node -v
```
```bash
sudo npm install -g yarn
```
```bash
yarn -v
```

**6. Install Yarn**
```bash
curl -o- -L https://yarnpkg.com/install.sh | bash
```
```bash
export PATH="$HOME/.yarn/bin:$HOME/.config/yarn/global/node_modules/.bin:$PATH"
```
```bash
source ~/.bashrc
```

---

## 2) Clone the Repository
```bash
git clone https://github.com/gensyn-ai/rl-swarm/
```
```
cd rl-swarm
```
---

---

## 3) Get HuggingFace API Key 
**1- Create account in [HuggingFace](https://huggingface.co/)**

**2- Create an Access Token with `Write` permissions [here](https://huggingface.co/settings/tokens) and save it**

## 4) Run the Node (For VPS)
Open a screen to run it in background
```bash
screen -S swarm
```
### To run the Node (WSL and VPS)
```bash
python3 -m venv .venv
```
```
source .venv/bin/activate
```
### Here's an optional step( if you're encountering errors for outdated builds)
```
pip install -r requirements.txt
```
```
cd modal-login
```
```
yarn install
```
```
yarn upgrade &&  yarn add next@latest &&  yarn add viem@latest
```
```
cd..
```
```
cd rl-swarm
```


* Start the Node
```
./run_rl_swarm.sh
```
Press `Y`

---

## 5) Login
**1- You have to receive `Waiting for userData.json to be created...` in logs**

![image](https://github.com/user-attachments/assets/140f7d32-844f-4cf0-aac4-a91e9a14c1aa)

**2- Open login page in browser**
* **Local PC:** `http://localhost:3000/`
* **VPS users:** Do not receive OTP code in emails by logging in 3000 port on browser. You have to forward port by entering a command in their local pc powershell command prompt. (Step 3 of this section)

**3- ⚠️ If you can't login or no email code received, Forward port:** (ONLY FOR VPS USERS)
* In windows start menu, Search **Powershell** and open its terminal in your local PC
* Enter the command below and replace your vps ip with `Server_IP` and your vps port(.eg 22) with `SSH_PORT`
```
ssh -L 3000:localhost:3000 root@Server_IP -p SSH_PORT
```
### Example
```
ssh -L 3000:localhost:3000 root@137.12.0.0 -p 22
```
``
    *After you enter this command type `YES` and Provide your VPS Password 
    
---
    
* 🔴 Make sure you enter the command in your own local Windows Powershell cmd and NOT your VPS terminal.
* This prompts you to enter your VPS password, when you enter it, you connect and tunnel to your vps
* Now go to browser and open `http://localhost:3000/` and login

* Official dashboard: https://dashboard.gensyn.ai/

**You can search your Node name in the dashboard after a while when you have done your first training completed**

# For Next Day 
```
cd rl-swarm
```

## VPS
```bash
screen -S swarm
```

## For WSL and VPS
Also for Restarting the Node
```bash
python3 -m venv .venv
```
```
source .venv/bin/activate
```
```
./run_rl_swarm.sh
```
Press `Y`

---

MY TG- @Ghosty880

