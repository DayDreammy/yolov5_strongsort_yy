# README

仓库地址：[GitHub - mikel-brostrom/Yolov5_StrongSORT_OSNet: Real-time multi-camera multi-object tracker using YOLOv5 and StrongSORT with OSNet](https://github.com/mikel-brostrom/Yolov5_StrongSORT_OSNet)



操作指南：

1. 安装anaconda 

Anaconda官网：https/www.anaconda.com/

安装合适的安装包，下载完成后打开一路Yes即可，只需要注意这里要将 conda 添加到PATH:

打开cmd，输入``conda-V``，出现版本号则说明安装成功

```powershell
C:\Users\xx>conda -V
conda 4.13.0
```



2. 创建虚拟环境，并按照提示激活

```powershell
conda create -n your-env-name python=3.7
```

激活

```powershell
activate your-env-name

```

前面括号里的名字由 `base`变成`your-env-name`就说明激活成功了，同时也进入了这个虚拟环境。

3. 安装pytorch

yolov5最新版本需要pytorch1.6版本以上，因此我们安装pytorch1.7版本。我安装的是cuda11.3 ，关于cuda安装请自行百度。	

**注意**此处有很多坑，尝试多次，才发现能用的版本搭配：

```
torch==1.7.1+cu110
torchvision==0.8.2+cu110
```

在虚拟环境中，用以下语句安装。注意一不要挂梯子可能会报错，二清华源搜不到所以在官网下，三如果网速很慢可以用迅雷下载（包找到后会输出地址）

```bash
pip install torch==1.7.1+cu110 -f https://download.pytorch.org/whl/torch_stable.html
pip install torchvision==0.8.2+cu110 -f https://download.pytorch.org/whl/torch_stable.html
```

安装完成后，查看cuda是否可用，

```
(yolo) C:\Users\xxx\Yolov5_StrongSORT_OSNet>python
Python 3.7.13 (default, Mar 28 2022, 08:03:21) [MSC v.1916 64 bit (AMD64)] :: Anaconda, Inc. on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> import torch
>>> torch.cuda.is_available()
True

```

这里显示True表明正常安装。

4. 下载源码，安装依赖

仓库地址： [GitHub - mikel-brostrom/Yolov5_StrongSORT_OSNet: Real-time multi-camera multi-object tracker using YOLOv5 and StrongSORT with OSNet](https://github.com/mikel-brostrom/Yolov5_StrongSORT_OSNet)

下载源码：

```bash
git clone --recurse-submodules https://github.com/mikel-brostrom/Yolov5_StrongSORT_OSNet.git
```

安装依赖

```bash
pip install -r requirements.txt
```

详细可参考仓库readme

5. 尝试运行

由于网络原因模型直接下载可能不太行，所以手动下载了一部分，目前只能运行特定下载好的模型。

可用的命令，

```
python track.py  --strong-sort-weights osnet_x0_25_msmt17.pt --source test02.mp4 --show-vid --save-vid 
```

参数的意义可以参考``track.py``源码。

执行结果如下



参考资料：

1. [(96条消息) yolov5+Deepsort实现目标跟踪_花花少年的博客-CSDN博客_yolov5deepsort跟踪效果](https://blog.csdn.net/m0_37605642/article/details/122590352)





