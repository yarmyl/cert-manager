# Docker-compose 

## Примеры получения сертификата и ренью

`docker-compose -f docker-compose.yaml run certbot certonly --dns-cloudflare --dns-cloudflare-credentials /secrets/cloudflare2.ini -d blabla.ru,*.blabla.ru --preferred-challenges dns-01 --register-unsafely-without-email --force-renewal`

`docker-compose -f docker-compose.yaml run certbot renew -q`

## Registry:

image: "certbot/dns-cloudflare" - официальный

# Ansible playbook examples

## Доставка сертификатов на хост или группу хостов

`ansible-playbook deploy.yml -i inventory/hosts -e HOST=localhost -e domain=blabla.ru -v`

## Получение сертификата для домена

`ansible-playbook get_cert.yaml -i inventory/hosts -e domain=blabla.ru -v`

## Обновление текущих сертификатов и доставка

`ansible-playbook renew.yml -i inventory/hosts -v`

