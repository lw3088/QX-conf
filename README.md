# QX-conf
quanx的一些配置

[rewrite_local]

```shell
# 解锁Tiktok
(?<=_region=)CN(?=&) url 307 JP
(?<=&mcc_mnc=)4 url 307 2
^(https?:\/\/(tnc|dm)[\w-]+\.\w+\.com\/.+)(\?)(.+) url 302 $1$3
(?<=\d\/\?\w{7}_\w{4}=)1[6-9]..(?=.?.?&) url 307 17

# 皮皮虾去广告水印
^https?://.*\.snssdk\.com/bds/(feed/stream|comment/cell_reply|cell/cell_comment|cell/detail|ward/list|user/favorite|user/cell_coment|user/cell_userfeed|user/publish_list) url script-response-body https://raw.githubusercontent.com/NobyDa/Script/master/Surge/JS/Super.js
```

[filter_local]

```shell
# 皮皮虾分流
host-suffix, snssdk.com, direct
```

[filter_remote]

```
#Tiktok 分流
https://raw.githubusercontent.com/Semporia/Quantumult-X/master/Filter/TikTok.list, tag=TikTok, force-policy=TikTok, update-interval=86400, opt-parser=true, enabled=true
```
