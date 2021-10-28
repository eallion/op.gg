# An OP.GG mirror

<https://opgg.eallion.com/l=zh_CN>

这是一个 [OP.GG](https://www.op.gg/) 的国内镜像，部署在阿里云上海服务器，解决访问`Cloudflare`、`Akamai`比较慢的问题。
> ❔ 你是不是经常英雄都选好了，想看看职业选手的天赋符文出装，结果网站还没打开，游戏已经开始了？

### 前置镜像



域名：

- <https://opgg.eallion.com>

因为限制可手动添加参数访问中文页面：`l=zh_CN`

> <https://opgg.eallion.com/l=zh_CN>

<details>
<summary>其他可选参数：</summary>

> - <https://opgg.eallion.com/l=en_US>
> - <https://opgg.eallion.com/l=ko_KR>
> - <https://opgg.eallion.com/l=ja>
> - <https://opgg.eallion.com/l=pl>
> - <https://opgg.eallion.com/l=fr>
> - <https://opgg.eallion.com/l=de>
> - <https://opgg.eallion.com/l=es>
> - <https://opgg.eallion.com/l=nl>
> - <https://opgg.eallion.com/l=da>
> - <https://opgg.eallion.com/l=sv>
> - <https://opgg.eallion.com/l=no>
> - <https://opgg.eallion.com/l=ru>
> - <https://opgg.eallion.com/l=hu>
> - <https://opgg.eallion.com/l=fi>
> - <https://opgg.eallion.com/l=tr>
> - <https://opgg.eallion.com/l=ro>
> - <https://opgg.eallion.com/l=pt>
> - <https://opgg.eallion.com/l=zh_CN>
> - <https://opgg.eallion.com/l=zh_TW>
> - <https://opgg.eallion.com/l=sr>
> - <https://opgg.eallion.com/l=it>
> - <https://opgg.eallion.com/l=th_TH>
> - <https://opgg.eallion.com/l=vi_VN>
</details>

### 中转资源

通过 [Vercel](https://vercel.com) 中转网站资源

中转内容：

- `opgg.eallion.com` -> `op-gg-mirror.vercel.app` -> `www.op.gg`
- `op-gg-cdn.vercel.app` -> `opgg-cdn.akamaized.net`
- `op-gg-static.vercel.app` -> `opgg-static.akamaized.net`
- `op-gg-gnb.vercel.app` -> `opgg-gnb.akamaized.net`

### Vercel 部署脚本

Vercel CLI 手动部署

```
npm i vercel -g
```
```
vercel login
```
```
vercel -A vercel.json --prod
```

### 备注

```
.
├── README.md           # 说明
├── cdn                 # Vercel 反代 opgg-cdn.akamaized.net 脚本
│   ├── README.md
│   └── vercel.json
├── gnb                 # Vercel 反代 opgg-gnb.akamaized.net 脚本
│   ├── README.md
│   └── vercel.json
├── main                # Vercel 反代 op.gg 主站脚本
│   ├── README.md
│   └── vercel.json
├── nginx.conf          # nginx 反代配置
└── static              # Vercel 反代 opgg-static.akamaized.net 脚本
    ├── README.md
    └── vercel.json
```