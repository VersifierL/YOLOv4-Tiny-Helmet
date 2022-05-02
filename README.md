# YOLOv4-Tiny-Helmet

## 1.代码结构
  本代码一共包括3个文件夹，分别是：  
  darknet-helmet：YOLOv4-Tiny模型优化实验  
  yolov4-tiny-prune：YOLOv4-Tiny模型剪枝实验  
  TensorRT：YOLOv4-Tiny实现TensorRT加速  
## 2.简介
#### 2.1.darknet-helmet
  运行安全帽佩戴优化实验，通过./darknet train .data文件路径 .cfg文件路径进行模型训练   
  具体的cfg网络模型配置文件见experiment文件夹  
    例如：yolov4-tiny.cfg -> 608×608输入分辨率下的模型实验  
         yolov4-tiny-3-layer.cfg -> 新增一个检测层的模型实验  
         yolov4-tiny-3-layer-spp.cfg-> 新增一个检测层和spp的模型实验  
#### 2.2.yolov4-tiny-prune
  实现了基于局部稀疏因子衰减的模型稀疏化训练和模型剪枝  
  使用slim_prune.py脚本  
  环境是pytorch的环境  
#### 2.3.TensorRT
  实现YOLOv4-Tiny的TensorRT推理加速引擎，实现模型网络的水平和垂直融合，消除拼接层  
  yolo_to_onnx.py 文件实现weights格式转化成onnx格式  
  onnx_to_tensorrt.py 文件实现onnx格式转化成tensorRT格式  
