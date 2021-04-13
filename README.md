# server-configurations

## nginx
### conf.d-https-images

- Reference tutorial:
https://monicalent.com/blog/2019/01/06/responsive-images-with-nginx/

- Install before using configurations
On CentOS 7+

> sudo yum install nginx-module-image-filter

- Important notes a):
> load_module modules/ngx_http_image_filter_module.so;

is not a command, but a line to be put onto ```default.conf```

- Important notes b):
In your nginx configurations:
> location ~ "^/media/(?<width>(320|240))/(?<image>.+)$" {
>		alias /usr/share/nginx/html/img/$image;

```img``` would not be included in your visit url:
Correct url:
> https://{domain name}/media/1080/app/nba_v1/banner_lal.jpg