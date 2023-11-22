# [Elasticsearch](https://hub.docker.com/_/elasticsearch)

## Ports

- `9200` Elasticsearch
- `5601` Kibana

## Useful commands (Elasticsearch)

```bash
# Get into the container
docker compose exec elasticsearch bash

# Create enrollment token
elasticsearch-create-enrollment-token --scope kibana

# Add a new user with all the available roles
elasticsearch-users useradd $username -r watcher_admin,apm_system,viewer,logstash_system,rollup_user,kibana_user,beats_admin,remote_monitoring_agent,rollup_admin,snapshot_user,data_frame_transforms_admin,monitoring_user,enrich_user,kibana_admin,logstash_admin,editor,data_frame_transforms_user,machine_learning_user,machine_learning_admin,watcher_user,apm_user,beats_system,transform_user,reporting_user,kibana_system,transform_admin,remote_monitoring_collector,transport_client,ingest_admin,superuser

# Reset kibana_system password
elasticsearch-reset-password -u $username
```

## [Kibana](https://hub.docker.com/_/kibana)

### Important links

- [Kibana](http://localhost:5601)

### Useful commands (Kibana)

```bash
# Get into the Kibana container
docker compose exec kibana bash

# Get verification code
kibana-verification-code
```
