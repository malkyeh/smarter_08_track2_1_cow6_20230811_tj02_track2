# 俯拍牛隻移動軌跡模型
此模型基於深度學習技術，使用俯拍牛隻移動軌跡影像資料集進行訓練，能夠預測牛隻在未來一段時間內的移動軌跡。
模型下載:https://drive.google.com/file/d/1F_DWWZnBDenVY-_13V-YlvbFsDMd47UN/view?usp=drive_link
資料集部分：
1.影像原始檔：影像來自國立中興大學動物科學系，以每秒一張進行影像擷取，擷取時間自2022年10月03日至2022年11月19日，共有2652張影像，每張影像檔案類型皆為jpg格式

2.影像標註檔：標註檔是透過人工的方式進行標註，如下圖所示，每張影像均標註完成，可直接使用，每個標註檔檔案名稱都對應到影像原始檔檔案名稱，共有2652檔標註檔，檔案類型為xml格式。
![](https://hackmd.io/_uploads/Bkb93Dwfp.jpg)

AI模型的部分：
該模型目的是辨識每頭牛隻的身分，硬體需求需NVIDIA顯卡，軟體需求方面，操作系統Window10，程式語言Python3.8或以上，需安裝anaconda與cuda，且須安裝pytorch(https://pytorch.org/)

輸入檔案：影像原始檔，如下圖：
![](https://hackmd.io/_uploads/BJwaBIPM6.jpg)

輸入檔案：影像標註檔，如下圖：
![](https://hackmd.io/_uploads/BJ2HVIDz6.jpg)

輸出檔案：框選出物件之影像，如下圖：
![](https://hackmd.io/_uploads/BJU5_IPMa.png)

使用步驟：
1. 使用anaconda建立一個虛擬環境
2. 下載影像原始檔與影像標註檔，並解壓縮
3. 在cmd處執行pip install -r requirement.txt下載模型套件
4. 將要辨識的影像放至pythonProject\yolov7-main\temp路徑底下
5. 透過cmd執行python detect_cow_shed.py –weights exp42/weights/best.pt –source temp/
6. 辨識結果之影像將存在”runs/detect/imgs-track”路徑底下