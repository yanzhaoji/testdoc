---
name: 简介
---

# YZJ 

这是一个测试文档
似乎这个目录不能少 少了就显示不出来


```sh
setenforce 0
sed -i_bak 's/SELINUX=enforcing/SELINUX=disabled/g' /etc/selinux/config
sed -i 's/SELINUXTYPE=targeted/#SELINUXTYPE=targeted/g' /etc/selinux/config


或
sed -i_bak '/SELINUX/s/enforcing/disabled/' /etc/selinux/config
```


