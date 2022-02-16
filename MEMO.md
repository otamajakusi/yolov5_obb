# memo

## annotation data

https://drive.google.com/drive/folders/1bWVFu0Va1RXfTd5JeHjJO_TnhiTd6fm0

## class.txt

https://drive.google.com/file/d/1mc9oAqm7ZNN98ih9YcrGHJbk8NctnuQY/view?usp=sharing

## convert xml to txt

```
unzip <annotation data>
python voc2yolo.py --data <annotation unzip dir> --class-file <class.txt>
```

make sure .txt files are generated under <annotation unzip dir>

## data split

```
python path/to/yolov5/split_data.py --datapath <annotation unzip dir> --outpath <train data dir>
(cd <train data dir>; ln -s labels labelTxt)
```

## train

```
python train.py --data data/analog-meter.yaml --cfg models/yolov5m.yaml --weight runs/train/exp9/weights/best.pt --batch-size 4 --device 0 --epochs 10000
```

## predic

```
python detect.py --weights runs/train/exp??/weights/best.pt --source 201904300930-70861.png --device cpu --line-thickness=1 --conf-thres=0.5 --hide-conf
```
