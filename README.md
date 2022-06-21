
## Q2L
### 环境

```
pip install -r requirments.txt
```


### 数据集处理

data/untitled.ipynb 修改数据集路径，得到.json文件


### 训练

q2l/lib/dataset/get_dataset.py 修改coco_root与img_root
q2l/lib/dataset/heartTUdataset.py 修改编号与分类类别
q2l/train.sh 修改数据类别
运行训练程序

```
sh train_san.sh
```




## DINO
### 预训练模型

```
python -m torch.distributed.launch --nproc_per_node=1 main_dino.py --arch vit_small --patch_size 16 --data_path /user-data/dino/data/  --output_dir /user-data/dino/saved/ 
```




## STEGO
### 环境

```
conda env create -f environment.yml
conda activate stego
```

### 数据集处理
STEGO/data/cut.ipynb 对图像进行切割
STEGO/data/Untitled_san.ipynb 修改数据集路径，得到.json文件
将.json文件移动至对应数据集的文件夹中



### 训练

STEGO/src/configs/train_config.yml 修改参数
STEGO/src/core.py 修改图片路径与预训练网络路径
运行训练程序

```
python train_segmentation.py
```



### 测试

STEGO/src/configs/eval_config.yml 修改参数
STEGO/src/eval_segmentation.py 修改模型路径与数据集名称
运行测试程序

```
python eval_segmentation.py
```




