# trained for real-time via webcam
# train for images

# train on py touch
yolo task=detect mode=train model=yolo11n.pt data=#pathto yaml epochs=20 imgsz=640

# run test on pt
yolo task=detect mode=predict model=runs/detect/train10/weights/best.pt source=g.jpg

# convert pt to onnx
yolo export model=best.pt format=onnx  # creates 'yolo11n.onnx'

best.onnx => 
# Export a YOLO11n PyTorch model to ONNX format
yolo export model=yolo11n.pt format=onnx  # creates 'yolo11n.onnx'

# Run inference with the exported model
yolo predict model=yolo11n.onnx source='https://ultralytics.com/images/bus.jpg'
