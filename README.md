Rabbitmq Role
=========


Role Variables
--------------

```
# Any Vars?

rabbitmq_plugins:
  - rabbitmq_management
  - rabbitmq_peer_discovery_aws

rabbitmq_config:
  cluster_formation.peer_discovery_backend: rabbit_peer_discovery_aws
  cluster_formation.aws.region: us-west-2
  cluster_formation.aws.use_autoscaling_group: "true"


rabbitmq_users:
  - user: admin
    password: admin
    vhost: /
    configure_priv: .*
    read_priv: .*
    write_priv: .*
    tags: administrator

rabbitmq_erlang_cookie: abc123

rabbitmq_clustering_enabled: true

# Required if clustering is enabled
rabbitmq_master_node:
rabbitmq_master_hostname:
```

----------------

```
#   requirements.yml
#
#   Example
# - src: https://github.com/ergontech-ansible-roles/rabbitmq
#   version: master
#   name: rabbitmq
```

License
-------

[MIT](LICENSE)