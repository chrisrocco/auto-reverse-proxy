1. Before running `docker compose up -d`, you should run `docker network create nginx-proxy` to create the external proxy network that other containers can access

2. Run `docker-compose up -d` in this repo's directory to start the reverse proxy server

3. To add a service to this proxy network, these three conditions must be met:
	a. Your domain name is aimed at your host machine
	b. Your service is connected to the 'nginx-proxy' network
	c. Your service is launched with the following ENV variables:
		i. VIRTUAL_HOST
		ii. LETSENCRYPT_HOST
		iii. LETSENCRYPT_EMAIL


For more detailed instructions and explaination, check out this article: https://blog.ssdnodes.com/blog/tutorial-extending-docker-nginx-host-multiple-websites-ssl/
