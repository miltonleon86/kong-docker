# 1. How to use.

- Make sure you are not using this ports in other apps:

```$bash
- "8000:8000"
- "8001:8001"
- "8443:8443"
- "8444:8444"
- "8080:8080"
```

- Start composer, the only error you could get should be related that
the ui and kong containers are going to restart till postgress is
ready to serve. 

```$bash
docker-compose up -d
docker ps
```

- Request a kong response.
```$bash
curl http://0.0.0.0:8001

Response:

{"plugins":{"enabled_in_cluster":[],"available_on_server":{"response-transformer":true,"oauth2":true,"acl":true,"correlation-id":true,"pre-function":true,"jwt":true,"cors":true,"ip-restriction":true,"basic-auth":true,"key-auth":true,"rate-limiting":true,"request-transformer":true,"http-log":true,"file-log":true,"hmac-auth":true,"ldap-auth":true,"datadog":true,"tcp-log":true,"zipkin":true,"post-function":true,"request-size-limiting":true,"bot-detection":true,"syslog":true,"loggly":true,"azure-functions":true,"udp-log":true,"response-ratelimiting":true,"aws-lambda":true,"statsd":true,"prometheus":true,"request-termination":true}},"tagline":"Welcome to kong","configuration":{"plugins":["bundled"],"admin_ssl_enabled":false,"lua_ssl_verify_depth":1,"trusted_ips":{},"prefix":"\/usr\/local\/kong","loaded_plugins":{"response-transformer":true,"request-termination":true,"prometheus":true,"ip-restriction":true,"pre-function":true,"jwt":true,"cors":true,"statsd":true,"basic-auth":true,"key-auth":true,"ldap-auth":true,"aws-lambda":true,"http-log":true,"response-ratelimiting":true,"hmac-auth":true,"request-size-limiting":true,"datadog":true,"tcp-log":true,"zipkin":true,"post-function":true,"bot-detection":true,"acl":true,"loggly":true,"syslog":true,"azure-functions":true,"udp-log":true,"file-log":true,"request-transformer":true,"correlation-id":true,"rate-limiting":true,"oauth2":true},"cassandra_username":"kong","admin_ssl_cert_csr_default":"\/usr\/local\/kong\/ssl\/admin-kong-default.csr","ssl_cert_key":"\/usr\/local\/kong\/ssl\/kong-default.key","dns_resolver":{},"pg_user":"kong","mem_cache_size":"128m","cassandra_data_centers":["dc1:2","dc2:3"],"nginx_admin_directives":{},"custom_plugins":{},"pg_host":"kong-database","nginx_acc_logs":"\/usr\/local\/kong\/logs\/access.log","proxy_listen":["0.0.0.0:8000","0.0.0.0:8443 ssl"],"client_ssl_cert_default":"\/usr\/local\/kong\/ssl\/kong-default.crt","ssl_cert_key_default":"\/usr\/local\/kong\/ssl\/kong-default.key","dns_no_sync":false,"db_update_propagation":0,"nginx_err_logs":"\/usr\/local\/kong\/logs\/error.log","cassandra_port":9042,"dns_order":["LAST","SRV","A","CNAME"],"dns_error_ttl":1,"headers":["server_tokens","latency_tokens"],"dns_stale_ttl":4,"nginx_optimizations":true,"database":"postgres","pg_database":"kong","nginx_worker_processes":"auto","lua_package_cpath":"","admin_acc_logs":"\/usr\/local\/kong\/logs\/admin_access.log","lua_package_path":".\/?.lua;.\/?\/init.lua;","nginx_pid":"\/usr\/local\/kong\/pids\/nginx.pid","upstream_keepalive":60,"admin_access_log":"logs\/admin_access.log","client_ssl_cert_csr_default":"\/usr\/local\/kong\/ssl\/kong-default.csr","proxy_listeners":[{"ssl":false,"ip":"0.0.0.0","proxy_protocol":false,"port":8000,"http2":false,"listener":"0.0.0.0:8000"},{"ssl":true,"ip":"0.0.0.0","proxy_protocol":false,"port":8443,"http2":false,"listener":"0.0.0.0:8443 ssl"}],"proxy_ssl_enabled":true,"cassandra_contact_points":["127.0.0.1"],"enabled_headers":{"latency_tokens":true,"X-Kong-Proxy-Latency":true,"Via":true,"server_tokens":true,"Server":true,"X-Kong-Upstream-Latency":true,"X-Kong-Upstream-Status":false},"ssl_ciphers":"ECDHE-ECDSA-AES256-GCM-SHA384:ECDHE-RSA-AES256-GCM-SHA384:ECDHE-ECDSA-CHACHA20-POLY1305:ECDHE-RSA-CHACHA20-POLY1305:ECDHE-ECDSA-AES128-GCM-SHA256:ECDHE-RSA-AES128-GCM-SHA256:ECDHE-ECDSA-AES256-SHA384:ECDHE-RSA-AES256-SHA384:ECDHE-ECDSA-AES128-SHA256:ECDHE-RSA-AES128-SHA256","cassandra_ssl":false,"db_resurrect_ttl":30,"ssl_cert_csr_default":"\/usr\/local\/kong\/ssl\/kong-default.csr","cassandra_consistency":"ONE","client_max_body_size":"0","admin_error_log":"logs\/error.log","pg_ssl_verify":false,"dns_not_found_ttl":30,"pg_ssl":false,"cassandra_schema_consensus_timeout":10000,"client_ssl":false,"cassandra_repl_strategy":"SimpleStrategy","db_update_frequency":5,"nginx_kong_conf":"\/usr\/local\/kong\/nginx-kong.conf","cassandra_repl_factor":1,"nginx_http_directives":[{"value":"prometheus_metrics 5m","name":"lua_shared_dict"}],"kong_env":"\/usr\/local\/kong\/.kong_env","real_ip_header":"X-Real-IP","dns_hostsfile":"\/etc\/hosts","log_level":"notice","error_default_type":"text\/plain","ssl_cert":"\/usr\/local\/kong\/ssl\/kong-default.crt","cassandra_lb_policy":"RoundRobin","admin_ssl_cert_key_default":"\/usr\/local\/kong\/ssl\/admin-kong-default.key","cassandra_ssl_verify":false,"proxy_access_log":"logs\/access.log","ssl_cipher_suite":"modern","real_ip_recursive":"off","proxy_error_log":"logs\/error.log","client_ssl_cert_key_default":"\/usr\/local\/kong\/ssl\/kong-default.key","nginx_daemon":"off","anonymous_reports":true,"nginx_proxy_directives":{},"cassandra_timeout":5000,"pg_port":5432,"admin_listeners":[{"ssl":false,"ip":"0.0.0.0","proxy_protocol":false,"port":8001,"http2":false,"listener":"0.0.0.0:8001"}],"client_body_buffer_size":"8k","lua_socket_pool_size":30,"admin_ssl_cert_default":"\/usr\/local\/kong\/ssl\/admin-kong-default.crt","db_cache_ttl":0,"cassandra_keyspace":"kong","ssl_cert_default":"\/usr\/local\/kong\/ssl\/kong-default.crt","nginx_conf":"\/usr\/local\/kong\/nginx.conf","admin_listen":["0.0.0.0:8001"]},"version":"0.14.1","node_id":"e7883fc7-8b7a-416b-be8f-bf8514864d8e","lua_version":"LuaJIT 2.1.0-beta3","prng_seeds":{"pid: 48":198192156155,"pid: 47":247021222022,"pid: 49":227225902381,"pid: 50":921752501313},"timers":{"pending":5,"running":0},"hostname":"50b9b7f5a203"}
```

- Check the ui on the browser:
```$bash
http://0.0.0.0:8080

```

- I will send the passwords via Slack.
