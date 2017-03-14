# ansible-spark

Ansible roles for installing [Apache Spark](https://spark.apache.org) in standalone or clustered modes

## Role Variables

- `spark_version` - Spark version.
- `spark_cloudera_distribution` - Cloudera distribution version (default: `cdh5.4`)
- `spark_env_extras` - An optional dictionary with key and value attributes to add to `spark-env.sh` (e.g. `MESOS_NATIVE_LIBRARY: "/usr/local/lib/libmesos.so"`)
- `spark_defaults_extras` - An optional dictionary with key and value attributes
  to add to `spark-defaults.conf` (e.g. `"spark.eventLog.enabled": true`)
- `spark_user_groups` - an optional list of (OS)groups the spark user should belong to
- `spark_user_shell` - the spark user's default shell (default: `/bin/false`)

## Quick Start

- Edit the `group_vars/all` file to provide the Zookeeper's hostname and port
- Edit the `hosts` file to provide the host names for the masters and nodes
- Edit the `site.yml` file to run the desired role
- Call `site.yml` via `ansible-playbook -i hosts site.yml`