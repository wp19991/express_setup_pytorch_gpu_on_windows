> pytorch 1.13.0 windows GPU torch 离线安装

> 使用的是python37，因为可以在windows10及以后的电脑上使用

> 链接：`https://pan.baidu.com/s/1Q6tOoknZX32mY5SDLnZHoA?pwd=give `提取码：`give `

如果你不需要python的新特性，或者你不知道python37，python38，python39，python310的区别，建议就按照教程进行每一步的安装。
> PS：这里提供使用其他python版本的方法
> 1.去`https://download.pytorch.org/whl`找到与下面名称相近的版本
> 2.需要联网，并且跳过安装依赖安装依赖的步骤，因为依赖也是基于python37的

## 准备
1. 下载文件夹中所有的文件
```bash
文件夹：third以及里面11项
文件夹：torch以及里面4项
文件：cuda_11.7.1_516.94_windows.exe
文件：cudnn-windows-x86_64-8.6.0.163_cuda11-archive.zip
文件：Miniconda3-py37_4.12.0-Windows-x86_64.exe
文件：pytorch_1.13.0_windows_GPU离线安装.txt
文件：VC_redist.x64.exe
```
## 安装cuda
1. 安装 `cuda_11.7.1_516.94_windows.exe`
2. 解压 `cudnn-windows-x86_64-8.6.0.163_cuda11-archive.zip`
3. 打开路径 `C:\ProgramData\NVIDIA GPU Computing Toolkit\v11.7`
    - 将cuDNN压缩包内对应的文件复制到该目录下
4. 安装 `Miniconda3-py37_4.12.0-Windows-x86_64.exe`
5. 安装 `VC_redist.x64.exe`
6. 重启电脑

## 安装torch
```bash
1.打开Anaconda Prompt (Miniconda3)终端
cd到这个目录下面，按照下面的顺序来
2.安装依赖Pillow和numpy
pip install ./third/Pillow-9.3.0-1-cp37-cp37m-win_amd64.whl
pip install ./third/numpy-1.21.6-cp37-cp37m-win_amd64.whl
3.安装torch_gpu_cuda
pip install ./torch/torch-1.13.0+cu117-cp37-cp37m-win_amd64.whl
pip install ./torch/torchvision-0.14.0+cu117-cp37-cp37m-win_amd64.whl
pip install ./torch/torchaudio-0.13.0+cu117-cp37-cp37m-win_amd64.whl
pip install ./torch/torchtext-0.14.0-cp37-cp37m-win_amd64.whl

PS：如果需要安装pandas和matplotlib，需要安装下面的，不需要就不用安装，直接跳到下面一步
pip install ./third/cycler-0.11.0-py3-none-any.whl
pip install ./third/fonttools-4.38.0-py3-none-any.whl
pip install ./third/kiwisolver-1.4.4-cp37-cp37m-win_amd64.whl
pip install ./third/packaging-21.3-py3-none-any.whl
pip install ./third/pyparsing-3.0.9-py3-none-any.whl
pip install ./third/python_dateutil-2.8.2-py2.py3-none-any.whl
pip install ./third/pytz-2022.6-py2.py3-none-any.whl
pip install ./third/pandas-1.3.5-cp37-cp37m-win_amd64.whl
pip install ./third/matplotlib-3.5.3-cp37-cp37m-win_amd64.whl
```
## 进行测试
1. 检查安装
    - 打开Anaconda Prompt (Miniconda3)终端输入：`python`
```bash
>>>
import torch
# 检查cuda是否可以使用
torch.cuda.is_available()
# 查看有多少个GPU设备
torch.cuda.device_count()
# 查看gpu的容量
torch.cuda.get_device_capability(device=0)
```
