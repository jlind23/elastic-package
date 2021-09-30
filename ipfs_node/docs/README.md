# IPFS Node

This is a new integration created using the [elastic-package](https://github.com/elastic/elastic-package) tool.

## Application logs

An example event for `application` looks as following:

```json
{
    "@timestamp": "2021-09-29T09:20:33.777Z",
    "agent": {
        "ephemeral_id": "32cb6eb3-8df8-47ca-9cf4-2f13e86a3b95",
        "hostname": "docker-fleet-agent",
        "id": "438ddfc4-bb88-48a2-957d-2bf82b18a734",
        "name": "docker-fleet-agent",
        "type": "filebeat",
        "version": "7.15.0"
    },
    "data_stream": {
        "dataset": "ipfs_node.application",
        "namespace": "ep",
        "type": "logs"
    },
    "ecs": {
        "version": "1.11.0"
    },
    "elastic_agent": {
        "id": "438ddfc4-bb88-48a2-957d-2bf82b18a734",
        "snapshot": true,
        "version": "7.15.0"
    },
    "event": {
        "agent_id_status": "verified",
        "dataset": "ipfs_node.application",
        "ingested": "2021-09-29T09:20:37Z",
        "timezone": "+00:00"
    },
    "host": {
        "architecture": "x86_64",
        "containerized": true,
        "hostname": "docker-fleet-agent",
        "id": "6505f7ca36739e7eb909bdb52bf3ec18",
        "ip": [
            "172.18.0.4"
        ],
        "mac": [
            "02:42:ac:12:00:04"
        ],
        "name": "docker-fleet-agent",
        "os": {
            "codename": "Core",
            "family": "redhat",
            "kernel": "5.10.47-linuxkit",
            "name": "CentOS Linux",
            "platform": "centos",
            "type": "linux",
            "version": "7 (Core)"
        }
    },
    "input": {
        "type": "log"
    },
    "log": {
        "file": {
            "path": "/tmp/service_logs/ipfs-node-0.log"
        },
        "offset": 0
    },
    "message": "Changing user to ipfs"
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| ecs.version | ECS version this event conforms to. `ecs.version` is a required field and must exist in all events. When querying across multiple indices -- which may conform to slightly different ECS versions -- this field lets integrations adjust to the schema version of the events. | keyword |
| input.type | Input type | keyword |
| log.file.path | Full path to the log file this event came from, including the file name. It should include the drive letter, when appropriate. If the event wasn't read from a log file, do not populate this field. | keyword |
| log.offset | Logfile offset | long |
| message | For log events the message field contains the log message, optimized for viewing in a log viewer. For structured logs without an original message field, other fields can be concatenated to form a human-readable summary of the event. If multiple messages exist, they can be combined into one message. | text |


## Repository metrics

An example event for `repository` looks as following:

```json
{
    "@timestamp": "2021-09-29T09:21:20.710Z",
    "agent": {
        "ephemeral_id": "35914885-68d8-4096-9952-17bc2b6ccfb3",
        "hostname": "docker-fleet-agent",
        "id": "438ddfc4-bb88-48a2-957d-2bf82b18a734",
        "name": "docker-fleet-agent",
        "type": "metricbeat",
        "version": "7.15.0"
    },
    "data_stream": {
        "dataset": "ipfs_node.repository",
        "namespace": "ep",
        "type": "metrics"
    },
    "ecs": {
        "version": "1.11.0"
    },
    "elastic_agent": {
        "id": "438ddfc4-bb88-48a2-957d-2bf82b18a734",
        "snapshot": true,
        "version": "7.15.0"
    },
    "event": {
        "agent_id_status": "verified",
        "dataset": "ipfs_node.repository",
        "duration": 1676376,
        "ingested": "2021-09-29T09:21:24Z",
        "module": "http"
    },
    "host": {
        "architecture": "x86_64",
        "containerized": true,
        "hostname": "docker-fleet-agent",
        "id": "6505f7ca36739e7eb909bdb52bf3ec18",
        "ip": [
            "172.18.0.4"
        ],
        "mac": [
            "02:42:ac:12:00:04"
        ],
        "name": "docker-fleet-agent",
        "os": {
            "codename": "Core",
            "family": "redhat",
            "kernel": "5.10.47-linuxkit",
            "name": "CentOS Linux",
            "platform": "centos",
            "type": "linux",
            "version": "7 (Core)"
        }
    },
    "http": {
        "repository": {
            "NumObjects": 22,
            "RepoPath": "/data/ipfs",
            "RepoSize": 118340,
            "StorageMax": 10000000000,
            "Version": "fs-repo@11"
        }
    },
    "metricset": {
        "name": "json",
        "period": 10000
    },
    "service": {
        "address": "http://elastic-package-service_ipfs_node_1:5001/api/v0/repo/stat",
        "type": "http"
    }
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| ecs.version | ECS version this event conforms to. `ecs.version` is a required field and must exist in all events. When querying across multiple indices -- which may conform to slightly different ECS versions -- this field lets integrations adjust to the schema version of the events. | keyword |
| error.message | Error message. | text |
| http.repository.NumObjects | Number of objects in the repository | long |
| http.repository.RepoPath | Path to the repository | keyword |
| http.repository.RepoSize | Size of the repository | long |
| http.repository.StorageMax | Max size of the storage | long |
| http.repository.Version | Storage version | keyword |
| service.address | Service address | keyword |
| service.type | The type of the service data is collected from. The type can be used to group and correlate logs and metrics from one service type. Example: If logs or metrics are collected from Elasticsearch, `service.type` would be `elasticsearch`. | keyword |


## Traffic metrics

An example event for `traffic` looks as following:

```json
{
    "@timestamp": "2021-09-29T09:22:05.725Z",
    "agent": {
        "ephemeral_id": "9ff54e20-0fef-4844-820c-d8c06dd8d613",
        "hostname": "docker-fleet-agent",
        "id": "438ddfc4-bb88-48a2-957d-2bf82b18a734",
        "name": "docker-fleet-agent",
        "type": "metricbeat",
        "version": "7.15.0"
    },
    "data_stream": {
        "dataset": "ipfs_node.traffic",
        "namespace": "ep",
        "type": "metrics"
    },
    "ecs": {
        "version": "1.11.0"
    },
    "elastic_agent": {
        "id": "438ddfc4-bb88-48a2-957d-2bf82b18a734",
        "snapshot": true,
        "version": "7.15.0"
    },
    "event": {
        "agent_id_status": "verified",
        "dataset": "ipfs_node.traffic",
        "duration": 1604634,
        "ingested": "2021-09-29T09:22:09Z",
        "module": "http"
    },
    "host": {
        "architecture": "x86_64",
        "containerized": true,
        "hostname": "docker-fleet-agent",
        "id": "6505f7ca36739e7eb909bdb52bf3ec18",
        "ip": [
            "172.18.0.4"
        ],
        "mac": [
            "02:42:ac:12:00:04"
        ],
        "name": "docker-fleet-agent",
        "os": {
            "codename": "Core",
            "family": "redhat",
            "kernel": "5.10.47-linuxkit",
            "name": "CentOS Linux",
            "platform": "centos",
            "type": "linux",
            "version": "7 (Core)"
        }
    },
    "http": {
        "traffic": {
            "RateIn": 1155.4079954492045,
            "RateOut": 3.202044009523675,
            "TotalIn": 201352,
            "TotalOut": 39255
        }
    },
    "metricset": {
        "name": "json",
        "period": 10000
    },
    "service": {
        "address": "http://elastic-package-service_ipfs_node_1:5001/api/v0/stats/bw",
        "type": "http"
    }
}
```

**Exported fields**

| Field | Description | Type |
|---|---|---|
| @timestamp | Event timestamp. | date |
| data_stream.dataset | Data stream dataset. | constant_keyword |
| data_stream.namespace | Data stream namespace. | constant_keyword |
| data_stream.type | Data stream type. | constant_keyword |
| ecs.version | ECS version this event conforms to. `ecs.version` is a required field and must exist in all events. When querying across multiple indices -- which may conform to slightly different ECS versions -- this field lets integrations adjust to the schema version of the events. | keyword |
| error.message | Error message. | text |
| http.traffic.RateIn | In network rate | scaled_float |
| http.traffic.RateOut | On network rate | scaled_float |
| http.traffic.TotalIn | Total in traffic | long |
| http.traffic.TotalOut | Total out traffic | long |
| service.address | Service address | keyword |
| service.type | The type of the service data is collected from. The type can be used to group and correlate logs and metrics from one service type. Example: If logs or metrics are collected from Elasticsearch, `service.type` would be `elasticsearch`. | keyword |


