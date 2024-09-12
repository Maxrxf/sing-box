
```
bash <(wget -qO- https://raw.githubusercontent.com/Maxrxf/sing-box/main/sing-box.sh)
```

* 再次运行
```
sb
```

  | Option 参数      | Remark 备注 |
  | --------------- | ------ |
  | -c              | Chinese 中文 |
  | -e              | English 英文 |
  | -u              | Uninstall 卸载 |
  | -n              | Export Nodes list 显示节点信息 |
  | -p <start port> | Change the nodes start port 更改节点的起始端口 |
  | -s              | Stop / Start the Sing-box service 停止/开启 Sing-box 服务 |
  | -a              | Stop / Start the Argo Tunnel service 停止/开启 Argo Tunnel 服务 | 
  | -v              | Sync Argo Xray to the newest 同步 Argo Xray 到最新版本 |
  | -b              | Upgrade kernel, turn on BBR, change Linux system 升级内核、安装BBR、DD脚本 |
  | -r              | Add and remove protocols 添加和删除协议 |


```
/etc/sing-box/                               # 项目主体目录
|-- cert                                     # 存放证书文件目录
|   |-- cert.pem                             # SSL/TLS 安全证书文件
|   `-- private.key                          # SSL/TLS 证书的私钥信息
|-- conf                                     # sing-box server 配置文件目录
|   |-- 00_log.json                          # 日志配置文件
|   |-- 01_outbounds.json                    # 服务端出站配置文件，已加了 warp 账户信息
|   |-- 02_route.json                        # 路由配置文件，chatGPT 使用 warp ipv6 链式代理出站
|   |-- 03_experimental.json                 # 缓存配置文件
|   |-- 04_dns.json                          # DNS 规则文件
|   |-- 11_xtls-reality_inbounds.json        # Reality vision 协议配置文件
|   |-- 12_hysteria2_inbounds.json           # Hysteria2 协议配置文件
|   |-- 13_tuic_inbounds.json                # Tuic V5 协议配置文件 # Hysteria2 协议配置文件
|   |-- 14_ShadowTLS_inbounds.json           # ShadowTLS 协议配置文件     # Tuic V5 协议配置文件
|   |-- 15_shadowsocks_inbounds.json         # Shadowsocks 协议配置文件
|   |-- 16_trojan_inbounds.json              # Trojan 协议配置文件
|   |-- 17_vmess-ws_inbounds.json            # vmess + ws 协议配置文件
|   |-- 18_vless-ws-tls_inbounds.json        # vless + ws + tls 协议配置文件
|   |-- 19_h2-reality_inbounds.json          # Reality http2 协议配置文件
|   `-- 20_grpc-reality_inbounds.json        # Reality gRPC 协议配置文件
|-- logs
|   `-- box.log                              # sing-box 运行日志文件
|-- subscribe                                # sing-box server 配置文件目录
|   |-- qr                                   # Nekoray / V2rayN / Shadowrock 订阅二维码
|   |-- shadowrocket                         # Shadowrock 订阅文件
|   |-- proxies                              # Clash proxy provider 订阅文件
|   |-- clash                                # Clash 订阅文件1
|   |-- clash2                               # Clash 订阅文件2
|   |-- sing-box-pc                          # SFM 订阅文件1
|   |-- sing-box-phone                       # SFI / SFA 订阅文件1
|   |-- sing-box2                            # SFI / SFA / SFM 订阅文件2
|   |-- v2rayn                               # V2rayN 订阅文件
|   `-- neko                                 # Nekoray 订阅文件
|-- cache.db                                 # sing-box 缓存文件
|-- nginx.conf                               # 用于订阅服务的 nginx 配置文件
|-- language                                 # 存放脚本语言文件，E 为英文，C 为中文
|-- list                                     # 节点信息列表
|-- sing-box                                 # sing-box 主程序
|-- cloudflared                              # Argo tunnel 主程序
|-- tunnel.json                              # Argo tunnel Json 信息文件
|-- tunnel.yml                               # Argo tunnel 配置文件
|-- sb.sh                                    # 快捷方式脚本文件
|-- jq                                       # 命令行 json 处理器二进制文件
`-- qrencode                                 # QR 码编码二进制文件
```
