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

There are a few files that needs to be prepared first

1. `group_vars/all` 
  - Provide the Zookeeper's hostname and port
  - Provide the ssh user that ansible should log in as
2. `hosts` 
  - Provide the host names for the masters and nodes
3. `site.yml` 
  - Provide the name of the role(s) to be executed

Then call `site.yml` via `ansible-playbook -i hosts site.yml`. You may be prompted to update your known_hosts file, if you have yet to `ssh` into the target hosts previously.