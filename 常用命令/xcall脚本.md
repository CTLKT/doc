
cd /usr/local/bin

vi xcall

脚本内容
```shell
#!/bin/bash
if [ $# -lt 1 ]
then
    echo 至少一个参数
    exit;
fi

for i in kc001 kc002 kc003
do
    echo --------- $i ----------
    ssh $i "source /etc/profile;$*"
done
```

chmod +x xcall