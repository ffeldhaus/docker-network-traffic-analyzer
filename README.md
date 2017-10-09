# Docker Network Traffic Analyzer

Docker application to analyze network traffic using Wireshark accessed via a Webbrowser.

Checkout Repository from GitHub and create a haproxy config file based on the template

```bash
git clone https://github.com/ffeldhaus/docker-network-traffic-analyzer.git
cd docker-network-traffic-analyzer
cp haproxy.cfg.template haproxy.cfg
```

Review the `haproxy.cfg` file and configure which ports should accept traffic and to which servers the traffic should be forwarded. The file includes examples for proxying HTTP to HTTPS, HTTP, NFS and SMB, but it is possible to configure arbitrary TCP based services. Uncomment the lines of the services you want to expose and change the name and address of the service endpoint (e.g. HTTPS server, NFS server or SMB server).

Review the `docker-compose.yml` file and add or uncomment the port mapping for all ports you want to expose.

Start the docker application with

```bash
docker-compose up
```

Access Wireshark via

    https://<hostname>:14500/?username=wireshark=password=wireshark

The application can be stopped with

```bash
docker-compose down
```

To stop the application and delete the docker containers use
```bash
docker-compose down -v
```
