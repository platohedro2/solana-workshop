# solana-workshop

Sesiones dirigidas por Alex ramirez 

Instalar solana y el cli en linux  

* usar terminal bash "recomendado"

~~~
sh -c "$(curl -sSfL https://release.solana.com/v1.16.4/install)"
~~~

luego creamos un alias para activar el comando solana en la terminal 

~~~
nano ~/.bashrc
~~~

al final de documento agregamos la sigueinte linea

~~~
alias neas='export PATH="/home/noisk8/.local/share/solana/install/active_release/bin:$PATH"'
~~~

con esto podemos escribir neas y se activara el comando solana 


luego instalamos el  cli, para esto debemos de tener rust instalado 

instalando rust 
~~~
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
~~~

instlando spl token cli 

~~~
cargo install spl-token-cli
~~~


Luego de tener esto instalado pasamos a ver la configuración de solana 

~~~
solana config get 
~~~

el resulatdo es algop cómo esto 

~~~
Config File: /home/noisk8/.config/solana/cli/config.yml
RPC URL: https://api.mainnet-beta.solana.com 
WebSocket URL: wss://api.mainnet-beta.solana.com/ (computed)
Keypair Path: /home/noisk8/.config/solana/id.json 
Commitment: confirmed 
~~~

Esto nos indica que: la configuración está apuntando al mainet, pero para este ejercicio queremos trabajar sobre la dev net pero antes debemos de generar una llave publica y una privada

~~~
solana-keygen  new --outfile /home/noisk8/.config/solana/id.json 
~~~
esto nos arrojara las 12 palanras que debemos de guardar

para saber nuestra public key 

~~~
solana-keygen pubkey
~~~

para saber la llaver privada 

~~~
cat /home/noisk8/.config/solana/id.json
~~~


para cambiar nuestro entorno a la dev net 

~~~
solana config set --url https://api.devnet.solana.com
~~~








