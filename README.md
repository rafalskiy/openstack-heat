# openstack-heat

```bash
docker run -d\
  --link controller:controller \
  --link mysql:mysql \
  --link keystone:keystone \
  --link rabbitmq:rabbitmq \
  -v /var/log/heat:/var/log/heat \
  -e KEYSTONE_HOST_IP=keystone\
  -e HOST_IP=heat \
  -e MYSQL_HOST_IP=mysql \
  -e MYSQL_USER=root \
  -e MYSQL_PASSWORD=MYSQL_DBPASS \
  -e ADMIN_PASS=ADMIN_PASS \
  -e NOVA_HOST_IP=controller \
  -e RABBIT_HOST_IP=rabbitmq \
  -e RABBIT_PASS=guest \
  -e HEAT_PASS=ADMIN_PASS \
  -e HEAT_DBPASS=MYSQL_DBPASS \
  -e HEAT_DOMAIN_PASS=ADMIN_PASS \
  -e OS_USERNAME=admin \
  -e OS_PASSWORD=ADMIN_PASS \
  -e OS_AUTH_URL=http://keystone:5000/v2.0 \
  -e OS_TENANT_NAME=admin \
  --privileged \
  --name heat \
  -h heat \
  shaddock/heat:latest
  ```
