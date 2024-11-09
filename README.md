# MSE-logs-collector
logs collector for mse logs BEAD proj

## Setting up Crontab for auto-renewal of SSL Cert

If you are using a domain for obtaining logs, set this on crontab so that you can always have a valid SSL certificate from Lets-encrypt
````
0 0 * * * /usr/bin/docker compose -f /home/CHANGE_TO_YOUR_USERNAME/MSE-logs-collector/docker-compose.yml run --rm certbot renew --webroot --webroot-path=/usr/share/nginx/html && /usr/bin/docker compose -f /home/CHANGE_TO_YOUR_USERNAME/MSE-logs-collector/docker-compose.yml kill -s SIGHUP nginx
````
