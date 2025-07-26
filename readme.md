# YOLOv12 Object Detection Project

## 專案簡介
這個專案旨在教導學生如何使用 YOLOv12 進行物件偵測，並應用於 IC 缺陷檢測的場景。YOLOv12 是 YOLO 系列的最新版本，結合了高效的注意力機制與殘差層聚合網路，能夠在保持即時性能的同時提升檢測準確率。

## 專案目標
1. 學習 YOLOv12 的基本概念與架構。
2. 使用 Roboflow 平台下載並準備自訂數據集。
3. 訓練 YOLOv12 模型以進行 IC 缺陷檢測。
4. 評估模型性能並進行推論。

## 環境設置
1. 確保已安裝 Python 3.8 或以上版本。
2. 安裝必要的套件：
   ```bash
   pip install -r requirements.txt
   ```
3. 設定 Roboflow API 金鑰：
   ```python
   import os
   os.environ["ROBOFLOW_API_KEY"] = "你的 API 金鑰"
   ```

## 使用步驟
### 1. 資料準備
- 使用 Roboflow 平台下載數據集，並確保數據集的結構符合 YOLO 格式。
- 修改 `data.yaml` 文件以指向正確的 `train`、`valid` 和 `test` 資料夾。

### 2. 模型訓練
- 使用以下指令開始訓練模型：
  ```python
  from ultralytics import YOLO

  model = YOLO('yolov12s.yaml')
  results = model.train(data='data.yaml', epochs=100, imgsz=256, batch=16, device='0')
  ```

### 3. 模型評估
- 使用混淆矩陣與 mAP 指標評估模型性能。

### 4. 模型推論
- 使用訓練好的模型進行推論，並可視化結果：
  ```python
  results = model(image, verbose=False)[0]
  ```

## 注意事項
- 確保 GPU 環境可用以加速訓練與推論。
- 若遇到任何問題，請參考 YOLOv12 官方文件或聯繫助教。

## 資源
- [YOLOv12 官方文件](https://github.com/sunsmarterjie/yolov12)
- [Roboflow 平台](https://roboflow.com)

## 聯絡方式
若有任何問題，請聯繫助教或教授。
