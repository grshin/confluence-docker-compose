# Certbot-auto Install

[root@wiki-vm]# wget https://dl.eff.org/certbot-auto

[root@wiki-vm]# mv certbot-auto /usr/local/bin/certbot-auto

[root@wiki-vm]# chown root /usr/local/bin/certbot-auto

[root@wiki-vm]# chmod 0755 /usr/local/bin/certbot-auto

# SSL Certification Create

[root@wiki-vm confluence-docker-compose]# docker-compose down

[root@wiki-vm confluence-docker-compose]# certbot-auto certonly --cert-name wiki.learnk8s.net -d wiki.learnk8s.net

# SSL Certification Restore

[root@wiki-vm confluence-docker-compose]# docker-compose down

[root@wiki-vm confluence-docker-compose]# certbot-auto renew --force-renewal --cert-name wiki.learnk8s.net

[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wiki.learnk8s.net/fullchain.pem /root/workspace/confluence-docker-compose/ssl

[root@wiki-vm confluence-docker-compose]# cp /etc/letsencrypt/live/wiki.learnk8s.net/privkey.pem /root/workspace/confluence-docker-compose/ssl

[root@wiki-vm confluence-docker-compose]# docker-compose up -d
