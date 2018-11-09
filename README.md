This project is used to help you to set up a wordpress site quickly, and with HTTPS/HTTP2.0 Support.

## File Structure
```
├── .env
├── docker-compose.yml
├── apache2
│   └── sites-enabled
├── _docker
├── mysql: Mysql Data Folder
└── src: Wordpress root path
    ├── wp-admin
    ├── wp-content
    └── wp-includes
```

## Denpendcies
- Docker
- docker-compose
- Lets Encrypt

## Setup
- Use Lets Encrypt to generate certificate/key for SSL
```
certbot certonly --email wangbaiyuan@outlook.com --agree-tos --webroot -w /wordpress/src -d wangbaiyuan.cn
```

- Start docker-compose Service
```
docker-compose up
```
