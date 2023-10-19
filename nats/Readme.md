### Install nats server


```sh 
# Add the NATS APT repository key
curl -sSL https://nats.io/nats-repo.gpg | sudo gpg --dearmor -o /usr/share/keyrings/nats-archive-keyring.gpg

# Add the NATS APT repository to your sources list
echo "deb [signed-by=/usr/share/keyrings/nats-archive-keyring.gpg] https://apt.nats.io/debian/ buster main" | sudo tee /etc/apt/sources.list.d/nats.list

# Update your package list again to include the NATS repository
sudo apt update

# Install the NATS server
sudo apt install nats-server


```



```sh

sudo systemctl start nats-server



sudo systemctl enable nats-server



```

#### Start the server

```sh

nat-server -c server.conf

```


## Create cli context

```sh

nats context ls

```sh

nats context save cluster_fil

nats context edit 


```
