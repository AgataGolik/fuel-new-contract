sudo apt update
sudo apt upgrade -y
sudo apt-get install curl screen -y 

curl --proto '=https' --tlsv1.3 https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env
rustc --version

rustup install stable
rustup update stable
rustup default stable

sudo apt install git -y 

curl https://install.fuel.network | sh

source /root/.bashrc

fuelup toolchain install latest
fuelup self update
fuelup update && fuelup default latest

sudo apt install vim

vim counter-contract/src/main.sw

Clear/delete everything and paste below:
contract;
 
storage {
    counter: u64 = 0,
}
 
abi Counter {
    #[storage(read, write)]
    fn increment();
 
    #[storage(read)]
    fn count() -> u64;
}
 
impl Counter for Contract {
    #[storage(read)]
    fn count() -> u64 {
        storage.counter.read()
    }
 
    #[storage(read, write)]
    fn increment() {
        let incremented = storage.counter.read() + 1;
        storage.counter.write(incremented);
    }
}

Press <Esc> key to escape from Insert more 
:wqa and ENTER

cd counter-contract
forc build 

forc wallet import 

forc wallet account new

forc deploy --testnet 

Enter 0 as Index and click y

CONTRACT DEPLOYED

