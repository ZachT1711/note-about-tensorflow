[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/HenryJHao/note-about-tensorflow)

# note-about-tensorflow
tensorflow-gpu 踩坑实录  基于win10 

安装成功配置: 

cuda_10.0.130_411.31_win10 

cudnn-10.0-windows10-x64-v7.4.2.24 

tensorflow_gpu-1.13.1-cp36-cp36m-win_amd64

安装流程：  CUDA->cudnn->tensorflow-gpu

一开始安装的tensorflow_gpu版本为1.12.0,出现ImportError: DLL load failed: 找不到指定的模块。
                                         Failed to load the native TensorFlow runtime.
                                         
原因为：CUDA版本与CUDNN与tensorflow_gpu版本不对应
          
使用pip install -U tensorflow-gpu==（指定版本号） -i https://pypi.tuna.tsinghua.edu.cn/simple
                                                                                            该操作会删除原有的GPU版本，再通过国内源下载指定的版本

出现EXCEPTION,很可能是网络原因，重新pip安装即可

在python中测试是否为tensorflow_gpu环境：

sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))

另一种测试方法：

tf.test.is_gpu_available()

查看当前tensorflow版本:

进入CMD,输入 conda info -e查看环境

激活并进入某环境 activate tensorflow-gpu

进入编译 python

使用pip指令  pip show tensorflow-gpu
