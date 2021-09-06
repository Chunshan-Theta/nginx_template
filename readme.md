# Nginx

##VW Setup

```commandline
sudo apt update
sudo apt install -y docker docker-compose
```


### SSL
```commandline

# 調整設定檔案
# 將 `<DOMAIN>.cf` 改成自己的網域
vim docker-compose_certbot.yml

# 進行網域認證
sudo docker-compose -f docker-compose_certbot.yml up
```

```commandline
# 關閉網域認證用的機器
sudo docker-compose -f docker-compose_certbot.yml down

# 調整設定檔案
# 將 `<DOMAIN>.cf` 改成自己的網域
vim nginx-conf-https/nginx.conf 

# 開啟NGINX
sudo docker-compose -f docker-compose.yml.https up -d
```