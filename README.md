# Install Caldera On Ubuntu 24


## 1-Update and Install dependencies
    sudo apt update && sudo apt upgrade -y
    sudo apt install git python3 python3-pip python3-venv -y


## 2-Clone the CALDERA repo
    git clone https://github.com/mitre/caldera.git --recursive
    cd caldera
## 3-Create and activate a virtual environment (recommended)
    python3 -m venv venv
    source venv/bin/activate

## 4-Install required Python packages

    pip install -r requirements.txt

## 5-Alternative requirement (If requier)

    git submodule update --init --recursive
    sudo apt install python3.10 python3.10-venv -y
    pip install docker
    sudo apt remove golang-go -y
    wget https://github.com/phuslu/go/releases/download/v0.0.0/go1.24.linux-amd64.tar.xz
    tar -xf go1.24.linux-amd64.tar.xz
    sudo rm -rf /usr/local/go # Remove old Go (if any)
    mv go /usr/local/
    echo 'export PATH=$PATH:/usr/local/go/bin' >> ~/.bashrc
    source ~/.bashrc
    go version
    sudo apt remove nodejs -y
    curl -fsSL https://deb.nodesource.com/setup_18.x | sudo -E bash -
    sudo apt install -y nodejs
    node -v
    npm -v
    cd /home/{YOUR_USER}/caldera/plugins/magma
    npm install
    npm run build
    ls dist/assets
if there are files in this directory it's true!


## 6-Run CALDERA
    cd caldera
    source venv/bin/activate
    export PATH=$PATH:/usr/local/go/bin
    python3 server.py --insecure

## 7-Access
    https://localhost:8888

## 8-User&Pass
    cat /home/{YOUR_USER}/caldera/conf/default.yml
