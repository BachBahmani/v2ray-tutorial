# آموزش نصب وی تو ری به همراه ابر آروان و یا سرور ایران
## Install v2ray + ArvanCloud or Edge server (Iran Server)


-----------


## نمای کلی:

[![Semantic](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/1-semantic.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/1-semantic.png)

روش های نصب: 
- [پیش نیازها](https://github.com/masterking32/v2ray-tutorial#%D9%BE%DB%8C%D8%B4-%D9%86%DB%8C%D8%A7%D8%B2%D9%87%D8%A7)
- [کمک ابرآروان](https://github.com/masterking32/v2ray-tutorial#%D8%B1%D9%88%D8%B4-%D8%A7%D9%88%D9%84-%D8%A8%D9%87-%DA%A9%D9%85%DA%A9-%D8%A7%D8%A8%D8%B1%D8%A2%D8%B1%D9%88%D8%A7%D9%86)
- [به کمک سرور مجازی ایران](https://github.com/masterking32/v2ray-tutorial#%D8%B1%D9%88%D8%B4-%D8%AF%D9%88%D9%85-%D8%A8%D9%87-%DA%A9%D9%85%DA%A9-%D8%B3%D8%B1%D9%88%D8%B1-%D9%85%D8%AC%D8%A7%D8%B2%DB%8C-%D8%A7%DB%8C%D8%B1%D8%A7%D9%86)

-----------

## پیش نیازها
- یک عدد سرور مجازی خارج از ایران
- یک عدد آدرس دامنه (در صورتی که روش ابرآروان را انجام میدهید امکان استفاده از دامنه رایگان را ندارید.)
- در صورتی که میخواهید سرور ایران خودتان را داشته باشید، یک عدد سرور ایران نیاز دارید!
- کمی دانش درباره لینوکس (Debian/Ubuntu Server)

-----------

## روش اول) به کمک ابرآروان
- نکته: در صورتی که میتوانید با شماره و ایمیل خارجی و آی پی خارج در ابرآروان ثبت نام کنید و از دامنه آی ار استفاده نکنید و در هنگام استفاده از ابرآروان از فیلترشکن استفاده کنیدhttps://github.com/masterking32/v2ray-tutorial#آموزش-نصب-x-ui.
- ابتدا در سایت [ابرآروان](https://arvancloud.ir) ثبت نام کنید.
- دامنه خود رو در بخش CDN ثبت کنید.
- وارد پنل دامنه خود شده و از منوی سمت چپ وارد بخش تنظیمات HTTPS شوید و گزینه "فعال سازی HTTPS" را فعال کنید.

[![ActiveHTTPS](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/2-arvan-https-active.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/2-arvan-https-active.png)

- حالا به بخش رکوردهای DNS بروید و روی رکورد جدید بزنید.
- در این بخش در قسمت subdomain یک نام بدهید ما از MyTest استفاده میکنیم.
- گزینه استفاده از سرویس ابری را خاموش کنید.
- قسمت نشانی IP، آی پی سرور خارجتان را وارد کنید و در نهایت روی گزینه ذخیره بزنید.

[![Active New Record](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/3-arvan-newdnsrecord.png)](https://raw.githubusercontent.com/masterking32/v2ray-tutorial/main/images/3-arvan-newdnsrecord.png)

- حال به بخش [آموزش نصب X-UI](https://github.com/masterking32/v2ray-tutorial#آموزش-نصب-x-ui) بروید و پس از انجام مراحل به این بخش بگردید و ادامه این آموزش را انجام دهید.
 
### این بخش را پس از نصب X-UI انجام دهید.

-----------

## روش دوم) به کمک سرور مجازی ایران

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
apt install curl sudo wget socat -y
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
