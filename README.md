# 脚本二进制部署kubernetes

## 前提

1. 写好配置文件
conf目录下的三个文件

```bash
for i in `cat conf/master_hosts`

awk -F "=" 
```

2. 做好ssh的免密登陆

    ```bash
    # 创建ssh密钥对
    # 更安全 Ed25519 算法
    ssh-keygen -t ed25519 -N '' -f ~/.ssh/id_ed25519
    # 或者传统 RSA 算法
    ssh-keygen -t rsa -b 2048 -N '' -f ~/.ssh/id_rsa

    # 分发密钥
    for i in ${node01ip} ${node02ip} ${node03ip}
    do
    ssh-copy-id -o stricthostkeychecking=no $i
    done
    ```



