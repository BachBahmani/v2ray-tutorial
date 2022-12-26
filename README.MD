# آموزش نصب وی تو ری به همراه ابر آروان و یا سرور ایران
## Install v2ray + ArvanCloud or Edge server (Iran Server)


-----------


## نمای کلی:

[![Semantic](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/1-semantic.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/1-semantic.png)

روش های نصب: 
- [پیش نیازها](https://github.com/masterking32/v2ray-tutorial#%D9%BE%DB%8C%D8%B4-%D9%86%DB%8C%D8%A7%D8%B2%D9%87%D8%A7)
- [از طریق ابرآروان](https://github.com/masterking32/v2ray-tutorial#%D8%B1%D9%88%D8%B4-%D8%A7%D9%88%D9%84-%D8%A8%D9%87-%DA%A9%D9%85%DA%A9-%D8%A7%D8%A8%D8%B1%D8%A2%D8%B1%D9%88%D8%A7%D9%86)
- [از طریق سرور مجازی ایران](https://github.com/masterking32/v2ray-tutorial#%D8%B1%D9%88%D8%B4-%D8%AF%D9%88%D9%85-%D8%A8%D9%87-%DA%A9%D9%85%DA%A9-%D8%B3%D8%B1%D9%88%D8%B1-%D9%85%D8%AC%D8%A7%D8%B2%DB%8C-%D8%A7%DB%8C%D8%B1%D8%A7%D9%86)

-----------

## پیش نیازها
- یک عدد سرور مجازی خارج از ایران
- یک عدد آدرس دامنه (در صورتی که روش ابرآروان را انجام میدهید امکان استفاده از دامنه رایگان را ندارید.)
- در صورتی که میخواهید سرور ایران خودتان را داشته باشید، یک عدد سرور ایران نیاز دارید!
- کمی دانش درباره لینوکس (Debian/Ubuntu Server)

-----------

## روش اول) به کمک ابرآروان
- نکته: در صورتی که میتوانید با شماره و ایمیل خارجی و آی پی خارج در ابرآروان ثبت نام کنید و از دامنه آی ار استفاده نکنید و در هنگام استفاده از ابرآروان از فیلترشکن استفاده کنید.
- ابتدا در سایت [ابرآروان](https://arvancloud.ir) ثبت نام کنید.
- دامنه خود رو در بخش CDN ثبت کنید.
- وارد پنل دامنه خود شده و از منوی سمت چپ وارد بخش تنظیمات HTTPS شوید و گزینه "فعال سازی HTTPS" را فعال کنید.

[![ActiveHTTPS](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/2-arvan-https-active.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/2-arvan-https-active.png)

- حالا به بخش رکوردهای DNS بروید و روی رکورد جدید بزنید.
- در این بخش در قسمت subdomain یک نام بدهید ما از MyTest استفاده میکنیم.
- گزینه استفاده از سرویس ابری را خاموش کنید.
- قسمت نشانی IP، آی پی سرور خارجتان را وارد کنید و در نهایت روی گزینه ذخیره بزنید.

[![Active New Record](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/3-arvan-newdnsrecord.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/3-arvan-newdnsrecord.png)

- حال به بخش [آموزش نصب X-UI](https://github.com/masterking32/v2ray-tutorial#%D8%A2%D9%85%D9%88%D8%B2%D8%B4-%D9%86%D8%B5%D8%A8-x-ui) بروید و پس از انجام مراحل به این بخش بگردید و ادامه این آموزش را انجام دهید.
- [یک VMESS و کاربر جدید بسازید.](https://github.com/masterking32/v2ray-tutorial#%D8%B3%D8%A7%D8%AE%D8%AA-%DA%A9%D8%A7%D8%B1%D8%A8%D8%B1-%D8%AC%D8%AF%DB%8C%D8%AF)
- [تنظیمات NGINX را انجام دهید](https://github.com/masterking32/v2ray-tutorial#%D9%BE%DB%8C%DA%A9%D8%B1%D8%A8%D9%86%D8%AF%DB%8C-%D9%88-%D8%AA%D9%86%D8%B8%DB%8C%D9%85-Nginx-%D8%AF%D8%B1-%D8%B3%D8%B1%D9%88%D8%B1-%D9%85%D8%AC%D8%A7%D8%B2%DB%8C-%D8%AE%D8%A7%D8%B1%D8%AC)
- پس از نصب X-UI و سپس ساخت کاربر جدید و تنظیم Nginx ادامه این آموزش را دنبال کنید.
- به پنل ابرآروانتان رفته و سپس در بخش دامنه مربوطه روی گزینه رکوردهای DNS بزنید.
- سپس زیردامنه ای که ساختید را پیدا کنید و مقدار استفاده از سرویس ابری را فعال کنید.

[![Enable Cloud ArvanCloud](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/6-arvan-enablecloud.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/6-arvan-enablecloud.png)

- کمی صبر کنید بین 5 تا 30 دقیقه تا تغییرات اعمال شود.
- در v2ray client های خود مثل ویندوز و ... بعد از وارد کردن QRCode آنها را ویرایش کنید و Port را به 443 تغییر دهید.
- توجه داشته باشید، پیش از اشتراک v2rayها یکبار آنها را در V2ray ویندوز خود Import کنید و پورت را تغییر دهید و سپس مجدد آنها رو کپی کنید و به کاربران خود بدهید.
- برای Import یک v2ray در نسخه ویندوز v2ray از کلید CTRL + V استفاده کنید، سپس روی آن دوبار کلیک کنید و پورت را ویرایش کنید و سپس روی OK بزنید. حال v2ray مربوطه را انتخاب کنید و روی CTRL + C بزنید و آنرا برای دوستان خود بفرستید.  
-----------

## روش دوم) به کمک سرور مجازی ایران

-----------
-----------
-----------
-----------

## آموزش نصب X-UI

- در سرور خود ابتدا دستورات زیر را به ترتیب وارد کنید.
```bash
apt update
apt upgrade -y
reboot
```
- پس از راه اندازی مجدد سرور دستورات زیر را وارد کنید.

```bash
apt install curl sudo wget socat nano -y
```

---

- حالا به مراحل نصب x-ui میرویم، یکی از موارد زیر را نصب کنید.
- نسخه انگلیسی با قابلیتهای بیشتر (پیشنهادی)

```bash
bash <(curl -Ls https://raw.githubusercontent.com/hossinasaadi/x-ui/master/install.sh)
```

- نسخه اصلی با زبان چینی

```bash
bash <(curl -Ls https://raw.githubusercontent.com/vaxilu/x-ui/master/install.sh)
```

- سوال اول را y زده
- سوال دوم را نام کاربری پنل مدیریت را وارد کنید
- سوال سوم رمزعبور پنل مدیریت را وارد کنید.
- سوال چهارم پورت دسترسی به پنل مدیریت را وارد کنید (ما 9950 را استفاده کردیم)

---
- نرم افزار Nginx را نصب و فعال کنید.

```bash
apt install nginx
systemctl enable nginx
```

- حالا میرویم تا سرتیفیکیت بسازیم، دستورات زیر را به ترتیب وارد کنید.
- در دستورات زیر بجای DOMAIN آدرس زیردامنه خود را وارد کنید. مثلا: MyTest.Site.CoM

```bash
curl https://get.acme.sh | sh
~/.acme.sh/acme.sh --set-default-ca --server letsencrypt
~/.acme.sh/acme.sh --register-account -m admin@DOMAIN
service nginx stop
~/.acme.sh/acme.sh --issue -d DOMAIN --standalone
~/.acme.sh/acme.sh --installcert -d DOMAIN --key-file /root/private.key --fullchain-file /root/cert.crt
service nginx start
```

- حالا در مرورگر آدرس آی پی سرور و پورتی که برای x-ui وارد کردید را بزنید مانند: http://99.99.99.99:9950
- نام کاربری و رمزعبوری که هنگام نصب وارد کردید را بزنید و روی دکمه Login کلیک کنید و سپس به بخش تنظیمات بروید.

[![XUI SETTINGS](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/4-xui-settings.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/4-xui-settings.png)

- در بخش تنظیمات مقادیر را به شکل زیر وارد کنید:

Panel certificate public key file path: `/root/cert.crt`

Panel certificate key file path: `/root/private.key`

panel url root path: `/mypanel/` هر چیزی میتوانید وارد کنید فقط ابتدا و انتهای آن / بزنید.

- در نهایت روی Save بزنید و دستور زیر را وارد کنید.

```sh
x-ui restart
```

- حالا میتوانید از طریق کلیک ورود به آدرس: https://99.99.99.99:9950/mypanel به پنل مدیریتتان دسترسی داشته باشید، مقدار پورت و mypanel را به چیزی که ثبت کردید تغییر دهید.

-----

### ساخت کاربر جدید

- در پنل XUI خود روی گزینه Inbounds کلید کرده و روی دکمه + بزنید.

[![XUI New User](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/5-xui-newuser.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/5-xui-newuser.png)

- مقادیر زیر را انتخاب کنید.

remark: یک نام انتخاب کنید.

protocol: `vmess`

transmission: `ws`

path: `/myuserurl` برای هرکاربر یه مقدار مخصوص و غیرتکراری وارد کنید.

tls: فعال کنید.

domain name: `mytest.site.com` نام دامنه شما

public key file path: `/root/cert.crt`

key file path : `/root/private.key`

- روی گزینه Add To بزنید.
- روی operate بزنید و QR Code را بزنید سپس روی Copy بزنید حال میتوانید V2ray را در ویندوز باز کرده و CTRL+V بزنید تا در نرم افزار اضافه شود.

در نسخه انگلیسی با گزینه Add Client میتوانید برای یک path و port چندین کاربر اضافه کنید، پس این مورد بهترین گزینه میباشد که یک vmess کلی تعریف کنید و داخل آن کاربران خود را اضافه کنید.
مقادیر path و port در ادامه آموزش هر بخش در Nginx مورد استفاده میباشد مقادیری که برای هر vmess ساختید را بخاطر بسپارید، در اینجا ما پورت 56010 و path به مقدار myuserurl داریم.

حال به ادامه آموزش نصب خود بازگردید.

### پیکربندی و تنظیم Nginx در سرور مجازی خارج

- دستور زیر را وارد کنید و بجای Domain آدرس زیردامنه مربوط به خود را بدهید. مثلا: `mytest.site.com`
```bash
nano /etc/nginx/sites-available/DOMAIN
```
- فایل با ویرایشگر متن باز میشود در آن مقدایر زیر را وارد کنید و در مقادیر زیر بجای DOMAIN آدرس زیر دامنه خود را بنویسید.

```nginx
server {
    server_name DOMAIN;
    root /var/www/html;
    index index.html;
    location / {
        try_files $uri $uri/ =404;
    }
    
    listen [::]:443 ssl ipv6only=on;
    listen 443 ssl;
    ssl_certificate /root/cert.crt;
    ssl_certificate_key /root/private.key;
}
server {
    if ($host = DOMAIN) {
        return 301 https://$host$request_uri;
    }
    listen 80;
    listen [::]:80;
    server_name DOMAIN;
    return 404;
}
```
- سپس فایل را ذخیره 
- حالا دستورات زیر را وارد کنید و بجای DOMAIN اسم زیردامنه خودتان را بزنید.

```bash
ln /etc/nginx/sites-available/DOMAIN /etc/nginx/sites-enabled/DOMAIN
cp /var/www/html/index.nginx-debian.html /var/www/html/index.html
service nginx restart
```

---

- حال به ازای هر VMESSی که میسازید نیاز دارید کد زیر را ویرایش کرده و در فایل کانفیگ Nginxتان قرار دهید.

```nginx
location /PATH {
  proxy_set_header X-Real-IP $remote_addr;
  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  proxy_set_header Host $http_host;
  proxy_set_header X-NginX-Proxy false;

  proxy_pass https://127.0.0.1:PORT;
  proxy_redirect off;

  proxy_http_version 1.1;
  proxy_set_header Upgrade $http_upgrade;
  proxy_set_header Connection "upgrade";
}
```

بجای PATH مقداری pathی که در هنگام ساخت vmess دادید وارد کنید و بجای PORT مقدار پورتی که هنگام ساخت وارد شده را وارد کنید.
- سپس مقدار مربوطه را بالای `listen [::]:443 ssl ipv6only=on;` در فایل کانفیگ nginx قرار دهید.

نمونه کامل فایل Nginx ما مطابق با مقادیر آموزشی:
```nginx
server {
    server_name mytest.site.com;
    root /var/www/html;
    index index.html;
    location / {
        try_files $uri $uri/ =404;
    }
    
	location /myuserurl {
	  proxy_set_header X-Real-IP $remote_addr;
	  proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
	  proxy_set_header Host $http_host;
	  proxy_set_header X-NginX-Proxy false;

	  proxy_pass https://127.0.0.1:56010;
	  proxy_redirect off;

	  proxy_http_version 1.1;
	  proxy_set_header Upgrade $http_upgrade;
	  proxy_set_header Connection "upgrade";
	}

    listen [::]:443 ssl ipv6only=on;
    listen 443 ssl;
    ssl_certificate /root/cert.crt;
    ssl_certificate_key /root/private.key;
}
server {
    if ($host = mytest.site.com) {
        return 301 https://$host$request_uri;
    }
    listen 80;
    listen [::]:80;
    server_name mytest.site.com;
    return 404;
}
```




