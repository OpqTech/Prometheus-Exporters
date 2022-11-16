# Ansible Role: Prometheus Exporters

An ansible role which contains multiple exporters of prometheus for scrapping data and for enhancing your monitoring stack. Here are the list of exporters which we are supporting in this role:-
- **[Elasticsearch Exporter](https://github.com/justwatchcom/elasticsearch_exporter)**


## Role Variables
### Mandatory Variables
**Needs to be change depending upon environment**

|**Variables**| **Default Values**| **Description**|
|----------|---------|---------------|
|**es_url** | localhost | Server IP of Elasticsearch|
|**es_port** | 9200 | Port on which elasticsearch is listening|


### Optional Variables

|**Variables**| **Default Values**| **Description**|
|--------------|-------------|-------------------|
|**node_exporter_version** | 0.17.0 | Version of Node Exporter|
|**es_exporter** | 1.0.2 | Version of Elasticsearch Exporter|

Values of **exporter_name** could be:-

|**Values** | **Description** |
|-----------|----------|
|**node** | For Node Exporter |
|**elasticsearch** | For Elasticsearch Exporter |

## Example Playbook
Here is an example playbook:-
```yml
---
- hosts: exporter
  user: ubuntu
  become: yes
  roles:
    - exporters
```

## Usage
For using this role you have to pass one variable to role which is **exporter_name**
```shell
ansible-playbook -i hosts  -e exporter_name="node"
```

