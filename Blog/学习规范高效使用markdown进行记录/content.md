# 这是我的第一篇文章
## 所需要进行安装的vscode拓展
```dotnetcli
markdown all in one 有各种快捷键和自动补全功能 非常方便
Markdown Preview Enhanced 边写markdown 边看
paste image 很方便的进行粘贴图片
LimfxCodeEx   渲染成文章
code spell check  错别字
```
虽然经过实测 最后又把code spell check删掉了  
有些时候在自定义名字的地方会爆黄 会很难受
## 这是二级标题
嘿嘿  
要记得末尾空两格是下一行 或者直接回车两次也行

## 记得加粗
ctrl + b是可以**加粗**文字的  
## 图片插入方面
在这个文件夹下面 进行ctrl + alt+v才行  
比如说  就是很好的例子  
![](2023-03-29-20-51-02.png)  

## 另外的话就是latex相关的功能也是有的 
只需4个美元符号
$$
\lim_{x\to\infin}
$$
如果是要在段中打入的话就需要$\lim_{x\to\infin}$好像也不是很难嘛  
反正改天是要好好学学latex打公式的
## 表格方面
第二行最关键 主要是规范数据如何对齐
小明|小红|小刚
:---:|:---:|:---:
3.2|1.1|3.0
4|5|6

## 链接
添加链接方面对着需要链接的文字选中粘贴url即可
比如说我要前往我的[个人网站](https://tobewca.com/)  
## 代码块
记得指定语言
```python
model_name = 'RNN'  # RNN GRU LSTM     TCN GCN_LSTM
device = 'cuda'  # 'cpu' or 'cuda'    在cuda_test.py 可测试CUDA的可用性和版本
input_size = 12    #属性的个数
hidden_size = 32
output_size = 1
num_layers = 1
levels = 4
kernel_size = 4
dropout = 0.25
in_channels = 18

```
## 最后的最后 是导出和其他模式的渲染
右上角有一个MPE从左向右第二个  会出来一个 白底预览
然后 点击chrome 然后pdf 可以导出pdf方便看

