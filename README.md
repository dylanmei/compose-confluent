compose-confluent
-----------------

An exercise in composing [docker containers](https://github.com/confluentinc/cp-docker-images) from [the Confluent platform](https://www.confluent.io/).

# metrics

To view the JMX metrics of each component, query the [Jolokia proxy](https://jolokia.org/features/proxy.html)

- broker: `curl -XPOST http://localhost:8080/jolokia/read -d '{"target": {"url": "service:jmx:rmi:///jndi/rmi://broker:9010/jmxrmi"}, "type": "search", "mbean": "*:*"}'`
- schema-registry: `curl -XPOST http://localhost:8080/jolokia/read -d '{"target": {"url": "service:jmx:rmi:///jndi/rmi://schema-registry:9010/jmxrmi"}, "type": "search", "mbean": "*:*"}'`
- rest: `curl -XPOST http://localhost:8080/jolokia/read -d '{"target": {"url": "service:jmx:rmi:///jndi/rmi://rest:9010/jmxrmi"}, "type": "search", "mbean": "*:*"}'`
- connect: `curl -XPOST http://localhost:8080/jolokia/read -d '{"target": {"url": "service:jmx:rmi:///jndi/rmi://connect:9010/jmxrmi"}, "type": "search", "mbean": "*:*"}'`
