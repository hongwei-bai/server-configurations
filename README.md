# server-configurations

## nginx
### conf.d-https-images

- Reference tutorial:
https://monicalent.com/blog/2019/01/06/responsive-images-with-nginx/

- Install before using configurations
On CentOS 7+

> sudo yum install nginx-module-image-filter

- Warnings:
> load_module modules/ngx_http_image_filter_module.so;

is not a command, but a line to be put onto ```default.conf```