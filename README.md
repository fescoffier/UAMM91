# Français

### Mise en place de l'environnement

Pour configurer l'environnement de test, il vous faut un déploiment Docker fonctionnel. Vous pouvez utiliser [Docker Desktop](https://www.docker.com/products/docker-desktop/) sur Linux, Windows et Mac.

Pour lancer l'environnement de test, exécutez la commande suivante :

```bash
docker-compose -f docker/docker-compose.yaml up -d
```

Pour éteindre l'environnement de test et préserver les données, exécutez la commande suivante :

```bash
docker-compose -f docker/docker-compose.yaml down
```

Pour éteindre l'environnement de test et supprimer toutes les données, exécutez la commande suivante :

```bash
docker-compose -f docker/docker-compose.yaml down -v
```

### Connexion à ClickHouse

Pour vous connecter à ClickHouse, vous pouvez soit utiliser [DBeaver](https://dbeaver.io/) ou l'outil en ligne de commande [clickhouse-client](https://clickhouse.com/docs/en/interfaces/cli). L'outil en ligne de commande de ClickHouse ne foncitonne que sur Linux et Mac. Si vous êtes sur Windows, vous pouvez utiliser [WSL](https://learn.microsoft.com/fr-fr/windows/wsl/install)

Pour vous connecter à ClickHouse :

```bash
clickhouse-client --password password -m
```

La paramètre `-m` indique à la CLI que les requêtes peuvent s'étendre sur plusieurs lignes, par conséquent, l'outil s'attend à ce que chacune des requêtes soient terminées par un point virgule.

```
clickhouse-client --password password -m
ClickHouse client version 23.10.4.25 (official build).
Connecting to localhost:9000 as user default.
Connected to ClickHouse server version 23.10.4 revision 54466.

af4b76ad5ccc :) SELECT version();

SELECT version()

Query id: 3c7331d1-ba91-46bc-8121-5e71cf63d872

┌─version()──┐
│ 23.10.4.25 │
└────────────┘

1 row in set. Elapsed: 0.001 sec.

```

### Inspecter les topics Kafka

Pour inspecter les topics Kafka, naviguez à la page http://localhost:8080 avec votre navigateur internet.

# English

## Français

### Environment setup

To configure the test environment, you need a functional Docker deployment. You can user [Docker Desktop](https://www.docker.com/products/docker-desktop/) on Linux, Windows and Mac.

To start the test environment, execute the following command:

```bash
docker-compose -f docker/docker-compose.yaml up -d
```

To shutdown the test environment and preserve the data, execute the following command:

```bash
docker-compose -f docker/docker-compose.yaml down
```

To shutdown the test environment and wipe all the data, execute the following command:

```bash
docker-compose -f docker/docker-compose.yaml down -v
```

### Connect to ClickHouse

To connect to ClickHouse, you can either use [DBeaver](https://dbeaver.io/) or the Command Line Interface [clickhouse-client](https://clickhouse.com/docs/en/interfaces/cli). The CLI is only available for Linux and Mac. If you are using Windows, check the [WSL](https://learn.microsoft.com/fr-fr/windows/wsl/install)

To connect to ClickHouse, execute the following command:

```bash
clickhouse-client --password password -m
```

The `-m` parameter indicates to the CLI that the requests are multilines, hence, the tool expect them to be terminated by a semi-colon.

```
clickhouse-client --password password -m
ClickHouse client version 23.10.4.25 (official build).
Connecting to localhost:9000 as user default.
Connected to ClickHouse server version 23.10.4 revision 54466.

af4b76ad5ccc :) SELECT version();

SELECT version()

Query id: 3c7331d1-ba91-46bc-8121-5e71cf63d872

┌─version()──┐
│ 23.10.4.25 │
└────────────┘

1 row in set. Elapsed: 0.001 sec.

```

### Inspect Kafka topics

To inspect the Kafka topics, navigate to the page http://localhost:8080 with your browser.