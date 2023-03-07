## 1.基本配置

- **用户名和邮箱**：这是用来标识不同开发者身份的配置，与代码托管中心的账号没有关系。你可以使用以下命令来设置用户名和邮箱：
  - `git config --global user.name "your name"`
  - `git config --global user.email "your email"`

## 2.配置ssh

 `-C 任意内容`

```
ssh-keygen -t rsa -C "codekingbear@gamil.com"
```

找到`.ssh`文件夹，一般在 C:\Users\user\.ssh

找到 `id_rsa.pub`，将里面的内容复制，

然后登陆github,在setting中找到`SSH and GPG keys选项`，点击`New SSH key`;

Title可以不写；复制的内容粘入下面的key框中；

点击Add SSH key完成配置；

## 3.git配置ssh,测试链接是否成功时候，一直报错

> 测试方法：ssh -T  git@github.com
> 
> ssh: connect to host github.com port 22: Connection timed out
> 
> 解决方法：
> 
> 在用户下的./ssh下新建`config文件`,在里面加入下面的内容
> 
> ```
> Host github.com
> Hostname ssh.github.com
> Port 443
> ```
