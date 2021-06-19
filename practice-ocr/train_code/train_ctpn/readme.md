## Train CTPN
> Modified codes from [pytorch_ctpn](https://github.com/opconty/pytorch_ctpn)  
Add OHEM  

## 数据集
* Support ICDAR17MLT dataset https://rrc.cvc.uab.es/?ch=8&com=downloads
  
* 数据集下载： [检测 百度云保存网盘](https://pan.baidu.com/s/1MT5BD--4zrQ3fUzwDt7UeQ)
  提取码：zwbf
* [识别数据集]   https://pan.baidu.com/s/1_fFOhV-rhaAN283rL3sBFQ  提取码：0god


To train your own model, put your images into one directory [images], 
and labels into another directory [labels].  
Replace the value of icdar17_mlt_img_dir and icdar17_mlt_gt_dir in config.py by your own path.  
Then run
>python3 ctpn_train.py  

If you want to train on ICDAR datasets, please visit [here](https://rrc.cvc.uab.es) and download datasets you like.


