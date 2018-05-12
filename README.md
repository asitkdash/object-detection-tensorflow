# object-detection-tensorflow(webapp)

Object Detection using Tensorflow existing model in Python 3.6, Flask and Ubuntu OS.

- Need to install tensorflow and it's corresponding dependencies (Available in Tensorflow website)
- Need to install Flask, Flask_WTF and Werkzeug.
- Open a terminal in Ubuntu and change the directory to Root using below command.
$ sudo -i
- Create a folder and Download pre-trained model to this folder using below commands.
    - mkdir -p /opt/graph_def
    - cp -a $model /opt/graph_def/
    - ln -sf /opt/graph_def/faster_rcnn_resnet101_coco_11_06_2017/frozen_inference_graph.pb /opt/graph_def/frozen_inference_graph.pb
- Add the object detection service file to system so that it will work on root level and establish a path to the program
    - cd $HOME
    - git clone https://github.com/asitkdash/object-detection-tensorflow
    - cp -a object-detection-tensorflow/object_detection_app /opt/
    - cp /opt/object_detection_app/object-detection.service /etc/systemd/system/
- This application provides a simple user authentication mechanism. You can change the username and password by modifying the following part in /opt/object_detection_app/decorator.py.

USERNAME = 'username'
PASSWORD = 'passw0rd'

- Launch the demo using the systemctl file.
    - systemctl daemon-reload
    - systemctl enable object-detection
    - systemctl start object-detection
    - systemctl status object-detection

- You can open the demo at http://0.0.0.0:80/.

