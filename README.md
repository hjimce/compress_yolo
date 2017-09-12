# compress_yolo 对yolo模型进行网络压缩、修剪等实验

 1.git clone https://github.com/hjimce/compress_yolo
 
 2.```cd compress_yolo```
 
 3.vim Makefile and  set``` PRUNE=1```
 
 4.start prune  tiny-yolo:
 
 ```./darknet detector train cfg/coco.data cfg/tiny-yolo.cfg  pretrain/tiny-yolo.weights  -gpus 0```
 
 5、copy backup file trained weights and test:
 
``` ./darknet detector test cfg/coco.data cfg/tiny-yolo-test.cfg pretrain/tiny-yolo_prune.weights data/dog.jpg```

6、test mAP:

```./darknet detector valid cfg/coco.data cfg/tiny-yolo-test.cfg pretrain/tiny-yolo_prune.weights```

compress the coco_results.json in results file and commit to https://competitions.codalab.org/competitions/5181#participate-submit_results

实验结果：64M compress to 18M
