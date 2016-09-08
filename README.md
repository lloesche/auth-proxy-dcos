# DC/OS Auth Proxy
A authentication proxy for services running on [Mesosphere DC/OS](https://dcos.io/)

## Intro
This adds basic auth in front of any http(s) service running inside DC/OS. Requires DC/OS 1.7+

## Usage
Works best in combination with [marathon-lb](https://github.com/mesosphere/marathon-lb)

Adjust the HAPROXY_VHOST value in auth-proxy.json.

Install using
```
$ dcos marathon app add auth-proxy.json
```

## Environment Variables
| Variable | Function | Example |
|----------|----------|-------|
|`USER` | Basic auth login user | `USER=lukas`|
|`PASSWORD` | Basic auth login password | `PASSWORD={PLAIN}letmein`|
|`SERVER_NAME` | Vhost to react on | `SERVER_NAME=_`|
|`LOCATION` | Path to react on | `LOCATION=/` |
|`PROXY_PASS` | Hostname or IP (plus optionally port) to proxy to | `PROXY_PASS=http://10.177.90:9090`|
