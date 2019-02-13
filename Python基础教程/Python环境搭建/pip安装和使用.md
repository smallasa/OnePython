## pip安装和使用
### 1.pip源设置
```bash
[root@one-python ~]# mkdir -p ~/.pip


[root@one-python ~]# cat > ~/.pip/pip.conf <<EOF
[global]
trusted-host=mirrors.aliyun.com
index-url=http://mirrors.aliyun.com/pypi/simple/
[list]
format=columns
EOF
```

### 2.pip常用命令
```bash
//查看当然安装的软件包列表
[root@one-python ~]# pip list
Package    Version
---------- -------
pip        10.0.1
setuptools 39.0.1

//更新pip软件包
[root@one-python ~]# pip install --upgrade pip

//安装软件包
[root@one-python ~]# pip install mysqlclient==1.4.1

//查看软件包
[root@one-python ~]# pip freeze
mysqlclient==1.4.1

//删除软件包
[root@one-python ~]# pip uninstall mysqlclient
```