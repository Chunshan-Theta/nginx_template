# Nginx

透過Nginx

## VM Setup

```commandline
sudo apt update
sudo apt install -y docker docker-compose
```


## 取得SSL驗證
```bash
# 調整設定檔案
# 將 `<DOMAIN>.cf` 改成自己的網域
vim docker-compose_certbot.yml
```

```bash
# 進行網域認證
sudo docker-compose -f docker-compose_certbot.yml up
```

```bash
# 關閉網域認證用的機器
sudo docker-compose -f docker-compose_certbot.yml down
```

```bash
# 調整設定檔案
# 將 `<DOMAIN>.cf` 改成自己的網域
vim nginx-conf-https/nginx.conf 
```

### 開啟Nginx服務
```bash
# 開啟NGINX
sudo docker-compose -f docker-compose.yml.https up -d
```

## 成功畫面
連上自己網域後發現前面是一個有鎖的標記和https即表示成功
![image](https://user-images.githubusercontent.com/47293699/133546821-dad05aeb-7746-4aa5-b8de-b189f8f6707b.png)
