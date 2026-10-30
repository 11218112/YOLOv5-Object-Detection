# YOLOv5 Object Detection

## Project Description
YOLOv5 object detection project using COCO128 dataset.

## Environment
- Google Colab
- Python
- PyTorch 2.11
- CUDA GPU (Tesla T4)
- YOLOv5

## Training
```bash
python train.py --data coco128.yaml --weights yolov5s.pt --epochs 1 --batch-size 8
# YOLOv5-Object-Detection
# YOLOv5-Object-Detection
# YOLOv5-Object-Detection

115 人工智慧期中作業：使用 Google Colab 執行 YOLOv5 v5.0 物件偵測
組員名單
- 組員一：11218109 薛妤芸
- 組員二：11218112 俞思帆
專案目的
本專案以 Google Colab 作為雲端運算環境，示範 GPU 硬體加速器設定、Google Drive 掛載、工作資料夾建立、YOLOv5 v5.0 原始碼下載與套件安裝，並使用 COCO128 範例資料集進行模型訓練、結果視覺化及物件偵測。
參考資料
- YOLOv5 v5.0 官方原始碼：https://github.com/ultralytics/yolov5/tree/v5.0
- Colab 跑項目：Colab 運行自己的項目：https://blog.csdn.net/qq_51070956/article/details/134503497
- 組員程式專案：https://github.com/11218112/YOLOv5-Object-Detection
實驗環境
請以實際執行結果填寫，不要直接照抄預設值。
- 平台：Google Colab
- Python 版本：執行 Notebook 後填寫
- PyTorch 版本：執行 Notebook 後填寫
- CUDA 版本：依 nvidia-smi 顯示結果填寫
- GPU 型號：依實際取得結果填寫（例如 T4；不保證每次都能取得）
- YOLOv5 版本：v5.0
- 範例資料集：COCO128
實驗流程與成果
1. 變更執行階段類型（啟用 GPU）
在 Colab 上方選單選擇「執行階段 → 變更執行階段類型」，將硬體加速器設為 GPU。若有提供 T4，可選擇 T4；若沒有，請記錄實際使用的 GPU。

<img width="944" height="628" alt="截圖 2026-10-30 下午4 36 20" src="https://github.com/user-attachments/assets/bafc12b7-a5aa-47a2-a3c9-f957a31342d2" />

2. 檢查 GPU、掛載 Google Drive 與建立資料夾
執行 !nvidia-smi 確認 GPU；使用 drive.mount('/content/drive') 掛載雲端硬碟；建立 /content/test 工作資料夾，並使用 %pwd 確認工作路徑。

<img width="757" height="572" alt="截圖 2026-10-30 下午5 20 09" src="https://github.com/user-attachments/assets/bdc617d5-8154-478c-8e5a-c562525b0768" />

3. 下載 YOLOv5 v5.0 並安裝套件
Notebook 會從 Ultralytics 官方 GitHub 下載 v5.0 標籤的原始碼，接著安裝 requirements.txt 所列套件。由於 v5.0 是較舊版本，Colab 執行環境更新時可能出現相依套件相容性問題；請以本次實際安裝結果及錯誤紀錄為準。
4. 設定參數並訓練模型
預設參數如下，請依實際執行狀況更新：
- 資料集：`data/coco128.yaml`
- 預訓練權重：`yolov5s.pt`
- 影像尺寸：640
- Epochs：3
- Batch size：16
這是用於確認流程的短時間示範訓練，不應將 3 epochs 的結果描述為完整訓練或最佳模型效能。

5. 使用 best.pt 進行物件偵測
訓練完成後，使用 runs/train/colab_run/weights/best.pt 對 data/images/bus.jpg 執行偵測，並顯示標註結果。

<img width="745" height="89" alt="截圖 2026-10-30 下午5 21 49" src="https://github.com/user-attachments/assets/bef36904-c4d8-4ed5-9f0c-a33ab05b2238" />

<img width="745" height="240" alt="截圖 2026-10-30 下午5 22 23" src="https://github.com/user-attachments/assets/4a2dfd42-efdf-4601-9afe-7a462f3454cc" />

<img width="745" height="570" alt="截圖 2026-10-30 下午5 23 20" src="https://github.com/user-attachments/assets/66100163-466f-4a0d-8833-8a939aefa9dd" />

6. 備份訓練結果至 Google Drive
將訓練資料夾及模型權重複製到 Google Drive 的 yolov5_colab 資料夾，避免 Colab 執行階段結束後遺失成果。

<img width="745" height="474" alt="截圖 2026-10-30 下午5 24 36" src="https://github.com/user-attachments/assets/5c35ffef-9081-4a24-be13-b8bdf7b85b93" />
