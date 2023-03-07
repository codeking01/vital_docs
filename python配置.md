## pip的配置

```pip
临时使用：

pip install -i https://pypi.tuna.tsinghua.edu.cn/simple some-package
```

```pip
# 全局配置
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
# 查看配置
pip config list
```

## conda的配置

```conda
# 查看自己的配置
conda config

# 配置
conda config --set show_channel_urls yes
# 生成的.condarc文件（在用户的下面）
```

然后再文本编辑器去替换下面的

```
channels:
  - defaults
show_channel_urls: true
channel_alias: https://mirrors.tuna.tsinghua.edu.cn/anaconda
default_channels:
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/pro
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
custom_channels:
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
```

## 如何进入虚拟环境

找到虚拟环境所在文件夹，找到**Scripts**文件夹，用cmd进入，然后输入

```cmd
activate
```

出现  `（环境名字）`，则代表激活成功
