# Deployment

## Prerequisities
- Install Strimzi Kafka Operator
- Install [Grafana Operator](https://grafana.github.io/grafana-operator)
- Install Debezium Operator (at least 2.7.0.Beta1)

## Deployment order
1. `kubectl create-namespace devconf`
2. `kubectl apply -n devconf -f postgres.yaml`
3. `kubectl apply -n devconf -f kafka.yaml`
4. `kubectl apply -n devconf -f crypto-app.yaml`
5. `kubectl apply -n devconf -f dbz-server.yaml`
6. `kubectl apply -n devconf -f monitoring/prometheus.yaml`
7. `kubectl apply -n devconf -f monitoring/grafana.yaml`
8. `kubectl apply -n devconf -f monitoring/grafana-data-source.yaml`
9. `kubectl apply -n devconf -f monitoring/grafana-dashboard.yaml`