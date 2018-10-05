# ssh
ssh学习
### 什么是ssh?
> https://baike.baidu.com/item/ssh/10407?fr=aladdin
### ssh-keygen生成git ssh密钥
> https://blog.csdn.net/zhuwinmin/article/details/54913468

### ssh配置git clone简易流程

> https://www.cnblogs.com/savokiss/p/5264483.html

### 本地.ssh文件地址

```
  C:\Users\Administrator
```
### github如何建立ssh连接,实现无密码提交

1. 检查是否生成过ssh 密钥

生成ssh 密钥后，会在当前用户的根目录下创建.ssh目录。因此，可以通过以下两种方式检查是否生成过ssh 密钥。

其一，是否可切换到.ssh目录：
```
cd ~/.ssh
```
如果.ssh目录则会切换到对应目录，不存在会有相关提示。

其二，使用ls命令检查：

```
ls -l ~/
```
通过以上两种方式检查后，当存在时，可以继续下面的操作重新生成ssh 密钥，也可以使用已经生成的ssh 密钥。

2. 如果本地没有秘钥，则生成一份

```
ssh-keygen -t rsa -C "981174580@qq.com"

```
//如果只有一对密钥，建议不要修改默认的密钥名称，即一直按回车即可

此命令会在你当前用户的个人目录下（如我当前用户为savokiss,就在/home/savokiss/.ssh，root则为/root)生成一对密钥

默认的名字为id_rsa和id_rsa.pub

3. 复制公钥

复制id_rsa.pub中的内容到你的github指定位置

```
头像> Settings> SSH and GPG keys > New SSH key

```

4. 使用ssh克隆

```
git clone git@github.com:lisong981174580/ssh.git

```
现在因为你本地和远端都有了一份秘钥，所以在此提交就不需要输密码了