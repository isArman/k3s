
۱. اعمال DNS شکن روی هاست.

۲. نصب K3s با اسکریپت سفارشی:

```bash
curl -sfL https://files.anaiis.ir/files/k3s/install.sh | sh -s -
```

۳. تنظیم رجیستری آروان:

```bash
mkdir -p /etc/rancher/k3s
cat >> /etc/rancher/k3s/registries.yaml <<EOF
mirrors:
  docker.io:
    endpoint:
      - "https://docker.arvancloud.ir"
EOF
```

۴. ری‌استارت سرویس K3s:

```bash
systemctl restart k3s
