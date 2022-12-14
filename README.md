# Guide to install Full node on the SUI 




![dMRcKOZrgpn_LT24AiwfK](https://user-images.githubusercontent.com/108979536/207665152-3d268127-f529-4d1d-bb72-2d85c6f13c81.jpeg)



Sui is the first permissionless Layer 1 blockchain designed from the ground up to enable creators and developers to build experiences that cater to the next billion users in web3.Sui is a boundless platform to build rich and dynamic on-chain assets from gaming to finance.


# 1 : Install Sudo update

       sudo apt update && sudo apt upgrade -y
    
    
 # 2 : Donwload tools
 
       apt-get update \
       && DEBIAN_FRONTEND=noninteractive TZ=Etc/UTC apt-get install -y --no-install-recommends \
       tzdata \
       git \
       ca-certificates \
       curl \
       build-essential \
       libssl-dev \
       pkg-config \
       libclang-dev \
       cmake
       
       
 # 3 : Install RUST
 
       curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
       
   ### Switch to source
   
       source $HOME/.cargo/env
   
   ### Update rustup
   
       rustup update

   ### Install screen
   
       apt-get install screen


# 4 : Open ports

       cd $home
       
   ### ports
   
       apt install ufw -y 
       ufw allow ssh 
       ufw allow https 
       ufw allow http 
       ufw allow 9000
       ufw allow 9184
       ufw enable
       
# 5 : Install Sui binaries

       cargo install --locked --git https://github.com/MystenLabs/sui.git --branch devnet sui sui-node
       
# 6 : Integrated Development Environment

       cargo install --git https://github.com/move-language/move move-analyzer --features "address20"
       
       
# 7 : Create wallet ( Enter y and Save all information)

      sui client active-address
      
   ( Press only number 0 and Enter )   
      
      
# 8 : Faucet on discord channel [Link](https://discord.gg/sui)

# 9 : Download the source code

      git clone https://github.com/MystenLabs/sui.git --branch devnet
      
# 10 : Configure your Node

      cd sui
      
   ### Set up the Sui repository as a git remote:
   
      git remote add upstream https://github.com/MystenLabs/sui
      
      
   ### Sync fork:
   
      git fetch upstream

   ### Make a copy of the fullnode configuration template:
   
   
      cp crates/sui-config/data/fullnode-template.yaml fullnode.yaml
      
# 11 : Downlaod the latest genesis

      curl -fLJO https://github.com/MystenLabs/sui-genesis/raw/main/devnet/genesis.blob
      
      
# 12 : Launch your fullnode 


      cd sui
      
      
  then  
  
  
      screen -S sui
      
      
  ### And run your full node 
  
      cargo run --release --bin sui-node -- --config-path fullnode.yaml

      
      


  [buy me cup of coffee](https://www.paypal.com/paypalme/AbdelAkridi?country.x=NL&locale.x=en_US)     
       
       
       
       
       
       
       
       

       
       
       
