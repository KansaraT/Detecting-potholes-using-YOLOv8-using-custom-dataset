# Detecting-potholes-using-YOLOv8-using-custom-dataset

**Download the Dataset**
* If you plan to execute the training commands on terminal, you can download the dataset by executing the following command.
```
!wget https://www.dropbox.com/s/qvglw8pqo16769f/pothole_dataset_v8.zip?dl=1 -O pothole_dataset_v8.zip
```

* unzip it in the current directory.
```
!unzip pothole_dataset_v8.zip
```

* Go inside the directory.
```
cd pothole_dataset_v8
```

**Setting Up YOLOv8 to Train on Custom Dataset**
* Install the ultralytics package using pip.
```
!pip install ultralytics
```

* Setting Up ClearML
```
!pip install clearml
```

**Commands for Training YOLOv8 on Custom Dataset**
```
!yolo task=detect mode=train model=yolov8n.pt imgsz=640 data=pothole.yaml epochs=10 batch=8 name=yolov8n_custom
```

* We can also evaluate the best model using the following command.
```
!yolo task=detect mode=val model=runs/detect/yolov8n_custom2/weights/best.pt name=yolov8n_eval data=pothole.yaml imgsz=1280
```

* Run inference on a video using the trained YOLOv8 Nano model.
```
!yolo task=detect mode=predict model=runs/detect/yolov8n_custom2/weights/best.pt source=sample.mp4 show=True imgsz=1280 name=yolov8n_v8_50e_infer1280 hide_labels=True
```

https://github.com/KansaraT/Detecting-potholes-using-YOLOv8-using-custom-dataset/assets/91043060/36fe5bf1-c053-4053-aa28-77faf590ddc1

