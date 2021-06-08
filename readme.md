# Prometheus, Grafana, AlertMamager, Exporter with Docker

├── alertmanager
│   └── config.yaml
├── docker-compose.yaml
├── grafana
│   └── grafana.env
└── prometheus
    ├── alert.rules
    ├── node.yaml
    └── prometheus.yaml

> Exportador é uma ferramenta que coleta e produz as métricas do servidor de monitoramento, e o Prometheus as coleta. Métricas. .. O Prometheus coleta isso na ferramenta de saída. Métricas. .. .. .. .. .. tão.
Existem vários tipos de Exportador, como os elaborados por Oficial e os elaborados por terceiros, para cada objeto a ser monitorado.

## Criação de um volume para armazenar os dados de métricas
O local onde os dados métricos são salvos é em / var / lib / prometheus / métricas quando instalado a partir do pacote. Na imagem oficial da encaixe, ele está salvo em / prometheus.

`$ docker volume create metrics_data`

`$ docker-compose up -d --build`


## Prometeu - Métricas
- http://your_prometeus.com:9090/graph


## Tente monitorar e abaixar.

Depois disso, se você entrar no conjunto PromQL em alert.rules, o nó correspondente será detectado. O valor é 0.

## Lista de elefantes de vigilância
- https://your_prometeus.com:9090/targets

## AlertManager

- https://your_prometeus.com:9093

Quando o objeto de monitoramento é Baixo, um elefante é detectado. (Neste exemplo, se não houver resposta por 5 minutos, o alerta aumentará.)

## Notificação de alerta
O Slack será notificado sobre o alerta.


## Grafana
- https://your_prometeus.com:3000

A conta inicial é admin: admin

## Adicionado Fonte de dados
 Data Sources
- Clique em Adicionar fonte de dados
- Prometheus Selecione
- Insira as informações necessárias e insira "Salvar e testar"
- Se "A fonte de dados está funcionando" for exibido, está OK.
- Clique na guia Dashbord e selecione importar.
- Clique na parte do nome
- Painel de controle é exibido.
- O uso detalhado de Grafana é omitido.

## Install Docker and create Swarm cluster

```sh
# curl -fsSL https://get.docker.com | sh
# docker swarm init
```