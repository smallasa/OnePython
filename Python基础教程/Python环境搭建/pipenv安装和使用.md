## pipenv安装和使用
### 1.pipenv安装
```bash
[root@one-python ~]# pip install pipenv

[root@one-python ~]# pip freeze
certifi==2018.11.29
pipenv==2018.11.26
virtualenv==16.3.0
virtualenv-clone==0.5.1
```

### 2.pipenv创建和删除虚拟环境
```bash
//创建虚拟环境项目
[root@one-python ~]# mkdir pipenv-3.6.6 && cd pipenv-3.6.6

//初始化虚拟环境
[root@one-python pipenv-3.6.6]# pipenv install --python 3.6.6

注意：虚拟环境尽量与系统版本保持一致！

//删除虚拟环境
[root@one-python pipenv-3.6.6]# pipenv --rm

//查看初始化虚拟目录文件
[root@one-python pipenv-3.6.6]# tree .
.
├── Pipfile
└── Pipfile.lock

//显示当前项目位置
[root@one-python pipenv-3.6.6]# pipenv --where
/root/pipenv-3.6.6

//显示虚拟环境位置
[root@one-python pipenv-3.6.6]# pipenv --venv
/root/.local/share/virtualenvs/pipenv-3.6.6-WcXYF2Vs

//显示python命令位置
[root@one-python pipenv-3.6.6]# pipenv --py
/root/.local/share/virtualenvs/pipenv-3.6.6-WcXYF2Vs/bin/python

//虚拟环境说明
pipenv默认将虚拟环境的真实文件放在(pipenv --venv)目录下,
而在实际的(pipenv --where)项目路径下只创建了两个文件"Pipfile"和"Pipfile.lock".
"Pipfile"和"Pipfile.lock"两个文件相互配合，共同完成虚拟环境的管理工作.
```

### 3.pipenv虚拟环境配置文件
```bash
[root@one-python pipenv-3.6.6]# cat Pipfile
[[source]]
name = "pypi"
url = "https://pypi.org/simple"
verify_ssl = true

[dev-packages]

[packages]

[requires]
python_version = "3.6"


[root@one-python pipenv-3.6.6]# cat Pipfile.lock
{
    "_meta": {
        "hash": {
            "sha256": "415dfdcb118dd9bdfef17671cb7dcd78dbd69b6ae7d4f39e8b44e71d60ca72e7"
        },
        "pipfile-spec": 6,
        "requires": {
            "python_version": "3.6"
        },
        "sources": [
            {
                "name": "pypi",
                "url": "https://pypi.org/simple",
                "verify_ssl": true
            }
        ]
    },
    "default": {},
    "develop": {}
}
```

### 4.pipenv设置源
```bash
[root@one-python pipenv-3.6.6]# sed -i s#https://pypi.org/simple#https://mirrors.aliyun.com/pypi/simple#g Pipfile
[root@one-python pipenv-3.6.6]# pipenv lock
```

### 5.pipenv常用命令
```bash
//安装软件包
[root@one-python pipenv-3.6.6]# pipenv install mysqlclient==1.4.1

//查看当然软件列表
[root@one-python pipenv-3.6.6]# pipenv graph
mysqlclient==1.4.1

//卸载软件包
[root@one-python pipenv-3.6.6]# pipenv uninstall mysqlclient==1.4.1

//进入和退出虚拟环境
[root@one-python pipenv-3.6.6]# pipenv shell
(pipenv-3.6.6) [root@one-python pipenv-3.6.6]# exit
exit

//运行虚拟环境
[root@one-python pipenv-3.6.6]# pipenv run python -c "import MySQLdb"

//在测试环境下安装包
[root@one-python pipenv-3.6.6]# pipenv install --dev django

注意：使用(pipenv install --dev {package})安装软件包后,
如果你要在生产环境中使用(pipenv install)默认不会安装{package},
但是另外一个开发人员可以使用(pipenv install --dev)安装{package}.

//删除所有软件包
[root@one-python pipenv-3.6.6]# pipenv uninstall --all

注意：此时"Pipfile"和"Pipfile.lock"两个文件还有安装的软件包信息,未被清空

```