1. 安装git
```
sudo apt-get install git
```
2. 配置用户名和邮箱
```
git config --global user.name "用户名" //这里--global是配置全局变量
git config --global user.email "邮箱" 
```
3. 生成ssh公匙、私匙
```
ssh-keygen -t rsa -C "邮箱“
```
三次回车确认，不要输入密码
4. 查看公匙
```
cd ～/.ssh
```
打开公匙文件
```
gedit id_rsa.pub
```
vim 复制内容的方法
在命令模式，光标覆盖在要复制的内容上，输入：”+y，三个字符。
5. 复制公匙到github
登录github—>Accounting settings图标->SSH key->Add SSH key->填写SSH key的名称，然后将复制的～/.ssh/id_rsa.pub文件内容粘贴->add key按钮添加。
6. 测试git
```
ssh -T git@github.com
```

# liunx git pull/push时避免频繁输入账号密码
1.先cd到根目录，执行
```
git config --global credential.helper store
```
2.执行后会在git config 文件中多加内容
```
[user]
	name = XXX
	email = xxx@xxx.com
[credential]
	helper = store
```
3. 接着cd到项目目录，执行git push命令，会提示输入账号密码。输完这一次以后就不再需要，并且会在根目录生成一个.git-credentials文件。
4. pull/push代码都不再需要输入账号密码了。

# 创建git文件
```
touch xxx
```
