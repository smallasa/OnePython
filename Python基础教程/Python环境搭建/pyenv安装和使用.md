## 通过pyenv安装python版本
### 1.安装pyenv
```bash
[root@one-python ~]# yum install epel-release
[root@one-python ~]# yum -y groupinstall "Development Tools"
[root@one-python ~]# yum -y install zlib zlib-devel openssl openssl-devel readline readline-devel bzip2 bzip2-devel sqlite-devel

[root@one-python ~]# git clone https://github.com/yyuu/pyenv.git /usr/local/pyenv

[root@one-python ~]# cat > /etc/profile.d/pyenv.sh <<EOF
export PYENV_ROOT=/usr/local/pyenv
export PATH=\$PYENV_ROOT/bin:\$PATH
eval "\$(pyenv init -)"
EOF
[root@one-python ~]# source /etc/profile

[root@one-python ~]# git clone https://github.com/yyuu/pyenv-virtualenv.git $(pyenv root)/plugins/pyenv-virtualenv
[root@one-python ~]# echo 'eval "$(pyenv virtualenv-init -)"' | tee -a /etc/profile.d/pyenv.sh
[root@one-python ~]# source /etc/profile
```

### 2.安装python
```bash
方式一：
[root@one-python ~]# pyenv install 3.6.6

方式二：
[root@one-python ~]# mkdir /usr/local/pyenv/cache
[root@one-python ~]# wget -O /usr/local/pyenv/cache/Python-3.6.6.tar.xz https://www.python.org/ftp/python/3.6.6/Python-3.6.6.tar.xz
[root@one-python ~]# pyenv install 3.6.6
```

### 3.pyenv常用命令
```bash
//查看当然版本
[root@one-python ~]# pyenv versions
* system (set by /usr/local/pyenv/version)
  3.6.6

//切换版本
[root@one-python ~]# pyenv global 3.6.6
[root@one-python ~]# pyenv versions
  system
* 3.6.6 (set by /usr/local/pyenv/version)

//刷新缓存
[root@one-python ~]# pyenv rehash

//删除版本
[root@one-python ~]# pyenv uninstall 3.6.6


//创建虚拟环境
[root@one-python ~]# pyenv virtualenv 3.6.6 python-dev-3.6.6

//切换到虚拟环境
[root@one-python ~]# pyenv activate python-dev-3.6.6

//离开虚拟环境
(python-dev-3.6.6) [root@one-python ~]# source deactivate

//删除虚拟环境
[root@one-python ~]# pyenv virtualenv-delete python-dev-3.6.6
```