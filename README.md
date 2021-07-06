# hydro-model-xaj

## 项目介绍

根据中国水利水电出版社出版的，由武汉大学叶守泽老师和河海大学詹道江老师等合编的《工程水文学》第三版教材中新安江模型的原理，结合河海大学芮孝芳老师《水文学原理》中的相关知识，并重点参考了河海大学包为民老师的《水文预报》第5版， 编写的**
三水源新安江模型**的 python 版本。**非官方版本，仅供学习参考**。

## 环境配置

We try to use [JAX](https://github.com/google/jax) to extend the ability of hydrologic models to Neural networks.
而JAX目前在windows上的安装需从源码直接编译，稍微麻烦一些，因此目前推荐在Ubuntu或者win10下的Ubuntu来运行本项目代码， 考虑到多数人仍然以Windows使用为主，因此项目说明均以win10下的Ubuntu为例。

Win10下安装Ubuntu，并在Win10-Ubuntu中安装python请参考[这里](https://github.com/OuyangWenyu/elks)。

Win10-Ubuntu中编辑运行代码的工具可使用VSCode，安装可以参考[这里](https://github.com/OuyangWenyu/hydrocpp/blob/main/1-basic-env/1.1-c_cpp-env.md#%E6%96%87%E6%9C%AC%E7%BC%96%E8%BE%91%E5%99%A8)，python相关配置请参考[这里](https://code.visualstudio.com/docs/python/python-tutorial)。

推荐使用Windows Ternimal工具，安装参考[这里](https://www.zhihu.com/question/323284458)。

fork本项目后，使用git clone命令下载。打开windows ternimal工具，输入：

```Shell
# bash进入Win10-Ubuntu，进入默认的home文件夹
bash
# 可以自己随便指定把本项目放入哪个文件夹，比如我创建一个Code文件夹并进入：
mkdir Code
cd Code
# clone项目
git clone <本项目在你的github中的地址>
# 进入本项目
cd hydro-model-xaj
# we'll use geopandas for shpfile, so at first we need to install libgdal-dev as it is a dependency of geopandas
sudo apt-get install libgdal-dev
# 用pip安装virtualenv（前提是按照前面的说明安装好了python）
pip install virtualenv
# virtualenv创建一个独立的Python运行环境，环境命名为venv，如下所示：
virtualenv venv
# 新建的Python环境被放到当前目录下的venv目录，激活该环境：
source venv/bin/activate
# 安装本项目程序依赖包
pip install --upgrade pip
pip install -r requirements.txt
# GPU-version (you must first install CUDA and CuDNN)
# pip install --upgrade jax jaxlib==0.1.65+cuda110 -f https://storage.googleapis.com/jax-releases/jax_releases.html
# 打开vscode:
code
```

然后在vscode中打开本项目，VSCode左下角配置好刚刚创建的python虚拟环境即可，可以参考[这里](https://marketplace.visualstudio.com/items?itemName=ms-python.python)。

## 使用说明

运行 python scripts in the "test" directory 即可。

目前测试函数包括直接调用模型的测试函数，以及率定的测试函数，简单修改程序即可测试任意一个。测试使用的数据较少，并不符合实际预报规范，目前项目只是为了梳理新安江模型原理及其运算过程，实际应用还在本项目代码基础上进一步开发。

如果觉得项目中文字和代码对原理的理解有误，或者出现代码运行错误，请在[issues](https://github.com/OuyangWenyu/hydro-model-xaj/issues)中留言。

## Acknowledgement

Thanks to the following repos besides with the [JAX document](https://jax.readthedocs.io/en/latest/):

- [ckrapu/gr4j_theano](https://github.com/ckrapu/gr4j_theano)
- [RobertTLange/code-and-blog](https://github.com/RobertTLange/code-and-blog)