# 時間序列特徵工程與會員流失預測模型

**團隊成員：蔣宗勳、林苡嘉、柯劭潔**

## 簡介

本專案為數據視覺化期末專案報告成果。  
專案針對 2020-2022 年的會員銷售數據與通話紀錄進行合併與 RFM 分析，旨在解決客戶流失預測中的數據極度不平衡問題，並預測客戶的流失狀態（忠誠、部分流失、完全流失）。  
我們透過 2D 時間序列特徵工程提取了長達 36 個月的行為軌跡與統計摘要指標，並實驗比較了兩套預測策略：經自定義機率門檻優化的單一 XGBoost 模型，以及 XGBoost + LSTM 軟投票加權融合模型。
經實驗證實，單一 XGBoost 模型配合手工時序特徵在此結構化寬表數據上表現最佳。  

## 系統介面

### 1. 資料不平衡處理前後比例 (SMOTE)
<img width="500" alt="SMOTE 比例圖" src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&w=800&q=80" />

> **圖說**：原始數據中忠誠客戶（Class 0）佔絕大比例（約 58.7%），經 SMOTE 重採樣後，三類的比例均衡調整為各佔 33.3%。

### 2. 最終採納模型 XGBoost 混淆矩陣 (Confusion Matrix)
<img width="500" alt="XGBoost Confusion Matrix" src="https://images.unsplash.com/photo-1543286386-7a39e65f0b84?auto=format&fit=crop&w=800&q=80" />

> **圖說**：最佳機率門檻下（$t_1=0.38, t_2=0.42$）的混淆矩陣預測結果 ，成功大幅提升少數類別的召回率與預測精準度。


## 環境

Python 3.11
Jupyter Notebook
scikit-learn
xgboost
tensorflow (keras)
imbalanced-learn


## 技術

+ 2D 時間序列特徵工程 (2D Time-Series Feature Engineering)
+ RFM 客戶價值分析模型 
+ SMOTE 不平衡資料過採樣技術
+ 網格搜尋機率門檻優化 
+ 雙模型軟投票融合 (XGBoost + LSTM Ensemble)


不平衡數據重採樣 (SMOTE)：自動將訓練集資料依目標標籤進行 1:1:1 的合成採樣平衡，避免模型產生多數類別偏誤
多模型融合對比分析：實現並對比了單一樹模型與雙模型融合（XGBoost + LSTM）的成效，深入分析並總結了結構化寬表在樹模型上的天然優勢 

