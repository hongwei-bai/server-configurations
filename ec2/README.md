# server-configurations

## EC2 guide
### An important step might be missing

本文对应从阿里云万网购买域名。

使用AWS的EC2实例，并且通过AWS申请免费证书。

1. 先从AWS证书这设置页中复制以下内容，用于稍后填写到阿里云的域名解析CNAME记录中。
<img src="images/aws_cert.jpg" width="800" height="335" />

2. 按照以下图示，添加CNAME的记录，主机记录对应上图的CNAME name, 记录值对应上图中的CNAME value。

3. 此外，还需添加默认的两个记录@和www。

<img src="images/阿里云域名解析设置.jpg" width="800" height="215" />

如下：

云解析DNS/域名解析/解析设置
| 主机记录 | 记录类型 | 解析请求来源(isp) | 记录值 | TTL | 状态 | 备注 | 操作 |
|---|---|---|---|---|---|---|---|
| www | A | 境外 | 54.206.109.xxx | 10 分钟 | 正常 | | (略) |
| @ | A | 境外 | 54.206.109.xxx | 10 分钟 | 正常 | | (略) |
| _d661475918778d74815304845fb06xxx | CNAME | 境外 | _07206290c3840a469ecf4621f5427xxx.wrpxpmnjfs.acm-validations.aws | 10 分钟 | 正常 | | (略) |