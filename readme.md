<h2>environment</h2>
<ul>
<li>
Linux
</li>
<li>
pytorch >= 1.4 python>=3.6.5 and corresponding torchvision,numpy,tqdm,etc.
</li>
<li>
NVIDIA GPU 3090ti *8 &nbsp &nbsp CUDA V9.2
</li>
</ul>

---

<h2>dataset</h2>
<table>
<tr>
<td >dataset</td><td>class_num</td><td>label type</td><td>source</td>
</tr>
<tr>
<td>ImageNet</td><td>100</td><td>single</td><td><a href="https://drive.google.com/drive/folders/0B7IzDz-4yH_HOXdoaDU4dk40RFE?resourcekey=0-yXVCpvfmjTx-OBW6PsSMiA">source</a>#</td>
</tr>
<tr>
<td>COCO</td><td>80</td><td>multi</td><td><a href="https://drive.google.com/drive/folders/0B7IzDz-4yH_HOXdoaDU4dk40RFE?resourcekey=0-yXVCpvfmjTx-OBW6PsSMiA">source</a>#</td>
</tr>
<tr>
<td>NUS-WIDE</td><td>21</td><td>multi</td><td><a href="https://drive.google.com/drive/folders/0B7IzDz-4yH_HOXdoaDU4dk40RFE?resourcekey=0-yXVCpvfmjTx-OBW6PsSMiA">source</a>#</td>
</tr>
<tr>
<td>VOC2012</td><td>20</td><td>multi</td><td><a href="http://host.robots.ox.ac.uk/pascal/VOC/voc2012/index.html">source</a></td>
</tr>
<tr>
<td>CIFAR-10</td><td>10</td><td>single</td><td><a href="http://www.cs.toronto.edu/~kriz/cifar.html">source</a></td>
</tr>

</table>

* Note that '#' means it is not the official source, for fair comparision, we obtain the data from [HashNet](https://github.com/thuml/HashNet/tree/master/pytorch) ,which is the same as [CSQ](https://github.com/yuanli2333/Hadamard-Matrix-for-hashing)

---

<h2>train</h2>
<h3>coco/nuswide/voc2012</h3>
<code>python train.py --data_path xxxx --data_name coco --word2vec_file ../data/coco/coco_bert768_word2vec.pkl --epochs 90 --center_update --R 5000 --batch_size 32 --hash_bit 64</code>
<h3>ImageNet/cifar-10</h3>
<code>python train.py --data_path xxxx --data_name imagenet --word2vec_file ../data/imagenet/imagenet_bert768_word2vec.pkl --epochs 90 --fixed_weight --center_update --R 1000 --batch_size 32 --hash_bit 64</code>

&nbsp;
<h5>data_path settings</h5>
> <p style="font-size: small;">ImageNet: image_path: <code>xx/xxx/imagenet/image/xxxx.JPEG</code> so that the data_path : <code>xx/xxx/imagenet</code></p>
> <p style="font-size: small;">COCO: image_path: <code>xx/xxx/coco/data/train2014/xxxx.JPEG</code> so that the data_path : <code>xx/xxx/coco</code></p>

* you can modify the dataloader/data_list.py to adapt to your file path as well.
