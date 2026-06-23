# 時間序列特徵工程與會員流失預測模型

**團隊成員：蔣宗勳、林苡嘉、柯劭潔**

## 簡介
 
專案針對 2020-2022 年的會員銷售數據與通話紀錄進行合併與 RFM 分析，旨在解決客戶流失預測中的數據極度不平衡問題，並預測客戶的流失狀態（忠誠、部分流失、完全流失）。    

## 系統介面

### 1. 資料不平衡處理前後比例 (SMOTE)
<img width="1339" height="626" alt="截圖 2026-06-23 下午3 41 29" src="https://github.com/user-attachments/assets/9cf213cb-517d-4094-8875-c7b9a00e9b78" />


> **說明**：原始數據中忠誠客戶（Class 0）佔絕大比例（約 58.7%），經 SMOTE 重採樣後，三類的比例均衡調整為各佔 33.3%。

### 2. XGBoost 預測結果與混淆矩陣
<img width="1304" height="581" alt="截圖 2026-06-23 下午3 41 40" src="https://github.com/user-attachments/assets/0be398de-dded-4ef4-9b74-2c75fc329a09" />



> **說明**：混淆矩陣預測結果，成功大幅提升少數類別的召回率與預測精準度。


## 環境
```
Python 3.11
Jupyter Notebook
scikit-learn
xgboost
tensorflow (keras)
imbalanced-learn
```

## 技術

+ 2D 時間序列特徵工程 (2D Time-Series Feature Engineering)
+ RFM 客戶價值分析模型 
+ SMOTE 不平衡資料過採樣技術
+ 網格搜尋機率門檻優化 
+ 雙模型軟投票融合 (XGBoost + LSTM Ensemble)
