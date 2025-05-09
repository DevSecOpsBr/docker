# Vault

## Getting Started

Vault secures, stores, and tightly controls access to tokens, passwords, certificates, API keys, and other secrets in modern computing. Vault handles leasing, key revocation, key rolling, and auditing. Through a unified API, users can access an encrypted Key/Value store and network encryption-as-a-service...

### Prerequisites

* docker ce
* docker cli
* docker swarm cluster (alread setup)

### Running

```sh
docker stack deploy -c vault.yml vault
```

### Checking

```shell
docker service ls

or

docker stack ls
```

### Unseal vault

To unseal vault just run the command below.

```shell
docker container exec -it <container-id> vault operator init
```

The output will show you all the keys and token to unseal vault. Save the output in a safe place.

Once you have all information is time to unseal vault follow the steps.

```(url)
http://<ip_of_your_docker_node>:8200/ui
```

When asked by the key please provider one by one till be asked by the token.

Done your vault is unseal and ready to use and completly integrated with consul as storage backend.
