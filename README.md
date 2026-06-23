# 時間序列特徵工程與會員流失預測模型

[cite_start]**團隊成員：蔣宗勳、林苡嘉、柯劭潔** [cite: 4, 5, 6]

## 簡介

[cite_start]本專案為數據視覺化（Data Visualization）期末專案報告成果 [cite: 1, 2, 3]。  
[cite_start]專案針對 2020-2022 年的會員銷售數據與通話紀錄進行合併與 RFM 分析 [cite: 9][cite_start]，旨在解決客戶流失預測中的數據極度不平衡問題 [cite: 35][cite_start]，並預測客戶的流失狀態（忠誠、部分流失、完全流失）[cite: 12]。  
[cite_start]我們透過 2D 時間序列特徵工程提取了長達 36 個月的行為軌跡與統計摘要指標 [cite: 27][cite_start]，並實驗比較了兩套預測策略：經自定義機率門檻優化的單一 XGBoost 模型 [cite: 62][cite_start]，以及 XGBoost + LSTM 軟投票加權融合模型 (Ensemble) [cite: 85, 86][cite_start]。經實驗證實，單一 XGBoost 模型配合手工時序特徵在此結構化寬表數據上表現最佳 [cite: 93]。  

## 系統介面

### 1. 資料不平衡處理前後比例 (SMOTE)
<img width="500" alt="SMOTE 比例圖" src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&w=800&q=80" />

> [cite_start]**圖說**：原始數據中忠誠客戶（Class 0）佔絕大比例（約 58.7%）[cite: 38, 39][cite_start]，經 SMOTE 重採樣後，三類的比例均衡調整為各佔 33.3% [cite: 47, 52, 53]。

### 2. 最終採納模型 XGBoost 混淆矩陣 (Confusion Matrix)
<img width="500" alt="XGBoost Confusion Matrix" src="https://images.unsplash.com/photo-1543286386-7a39e65f0b84?auto=format&fit=crop&w=800&q=80" />

> [cite_start]**圖說**：最佳機率門檻下（$t_1=0.38, t_2=0.42$）的混淆矩陣預測結果 [cite: 97][cite_start]，成功大幅提升少數類別的召回率與預測精準度 [cite: 110, 111, 115, 116]。

## 環境

Python 3.11
Jupyter Notebook
scikit-learn
xgboost
tensorflow (keras)
imbalanced-learn

以下是完全依照您提供的格式與排版，將本專案（數據視覺化期末專案）的內容重新梳理並撰寫而成的 `README.md` 原始碼：

```markdown
# 📊 2D 時間序列特徵工程與會員流失預測模型 (XGBoost vs. LSTM)

[cite_start]**團隊成員：蔣宗勳、林苡嘉、柯劭潔** [cite: 4, 5, 6]

## 簡介

[cite_start]本專案為數據視覺化（Data Visualization）期末專案報告成果 [cite: 1, 2, 3]。  
[cite_start]專案針對 2020-2022 年的會員銷售數據與通話紀錄進行合併與 RFM 分析 [cite: 9][cite_start]，旨在解決客戶流失預測中的數據極度不平衡問題 [cite: 35][cite_start]，並預測客戶的流失狀態（忠誠、部分流失、完全流失）[cite: 12]。  
[cite_start]我們透過 2D 時間序列特徵工程提取了長達 36 個月的行為軌跡與統計摘要指標 [cite: 27][cite_start]，並實驗比較了兩套預測策略：經自定義機率門檻優化的單一 XGBoost 模型 [cite: 62][cite_start]，以及 XGBoost + LSTM 軟投票加權融合模型 (Ensemble) [cite: 85, 86][cite_start]。經實驗證實，單一 XGBoost 模型配合手工時序特徵在此結構化寬表數據上表現最佳 [cite: 93]。  

## 系統介面

### 1. 資料不平衡處理前後比例 (SMOTE)
<img width="500" alt="SMOTE 比例圖" src="https://images.unsplash.com/photo-1551288049-bebda4e38f71?auto=format&fit=crop&w=800&q=80" />

> [cite_start]**圖說**：原始數據中忠誠客戶（Class 0）佔絕大比例（約 58.7%）[cite: 38, 39][cite_start]，經 SMOTE 重採樣後，三類的比例均衡調整為各佔 33.3% [cite: 47, 52, 53]。

### 2. 最終採納模型 XGBoost 混淆矩陣 (Confusion Matrix)
<img width="500" alt="XGBoost Confusion Matrix" src="https://images.unsplash.com/photo-1543286386-7a39e65f0b84?auto=format&fit=crop&w=800&q=80" />

> [cite_start]**圖說**：最佳機率門檻下（$t_1=0.38, t_2=0.42$）的混淆矩陣預測結果 [cite: 97][cite_start]，成功大幅提升少數類別的召回率與預測精準度 [cite: 110, 111, 115, 116]。

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

+ [cite_start]2D 時間序列特徵工程 (2D Time-Series Feature Engineering) [cite: 21, 27]
+ [cite_start]RFM 客戶價值分析模型 [cite: 9]
+ [cite_start]SMOTE 不平衡資料過採樣技術 [cite: 35, 58]
+ [cite_start]網格搜尋機率門檻優化 (Probability Threshold Grid Search) [cite: 68, 69]
+ [cite_start]雙模型軟投票融合 (XGBoost + LSTM Ensemble) [cite: 85, 86]

## 功能

+ [cite_start]雙維度時序特徵工程：將 36 個月的縱向時序數據完全攤平，形成高維度 2D 基礎特徵寬表（共 694 欄） [cite: 11, 22]。
+ [cite_start]衍生滾動時序特徵：針對 6 種基礎行為指標，分別計算 3 個月與 6 個月的移動平均版本（共 432 欄），捕捉近期行為衰退趨勢 [cite: 22]。
+ [cite_start]濃縮摘要特徵提取：針對時間序列個別抽取 Trend Slope（趨勢斜率）、ROC3（近3期變化率）、Std（波動度）、EMA Last（指數移動平均最後值）、Active Months（活躍月份數）與 Months Since Active（距最後活躍月數）等 6 種長期統計指標（共 36 欄） [cite: 27, 28, 29, 30, 31, 32, 33]。
+ [cite_start]不平衡數據重採樣 (SMOTE)：自動將訓練集資料依目標標籤進行 1:1:1 的合成採樣平衡，避免模型產生多數類別偏誤 [cite: 47, 58]。
+ [cite_start]多分類機率門檻優化：拋棄傳統 `argmax` 機制，透過網格搜尋尋找能最大化 Macro F1-score 的 Class 1 與 Class 2 自定義劃分門檻（最終設定 $t_1=0.38, t_2=0.42$） [cite: 62, 68, 69, 97]。
+ [cite_start]多模型融合對比分析：實現並對比了單一樹模型與雙模型融合（XGBoost + LSTM）的成效，深入分析並總結了結構化寬表在樹模型上的天然優勢 [cite: 85, 87, 93]。

```
