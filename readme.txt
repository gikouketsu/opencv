import cv2 
import numpy as np

cv2.namedWindow("video", cv2.WINDOW_NORMAL)
cap = cv2.VideoCapture(0)

if not cap.isOpened():
    print("Cannot open camera")
    exit()

while True:
    ret, frame = cap.read()

    # 如果正确读取帧,ret为True
    if not ret:
        print("Can't receive frame (stream end?). Exiting ...")
        break

    # 灰度模式
    # frame = cv2.cvtColor(frame, cv2.COLOR_BGR2G)
    
    cv2.imshow("video", frame)
    key = cv2.waitKey(1)
    if key == ord("q"):
        exit()
cap.release()
cv2.destroyAllWindows()
