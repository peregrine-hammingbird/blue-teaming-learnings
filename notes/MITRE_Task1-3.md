# MITRE ATT&CK（Task 1–3 メモ）

## TL;DR
- ATT&CKは「攻撃者の行動（TTP）」を共通言語で整理するためのナレッジベース。SOC/脅威分析/検知設計で使う。
- Matrixは「Tactic（目的）」→「Technique（やり方）」→「(Sub-technique)」の順で追うと迷子になりにくい。
- “グループ（脅威アクター）”を起点にすると、該当TechniqueやSoftwareまで一気に辿れる。  

---

## Task 1：Learning Objectives（要点）
- MITRE ATT&CKの目的と構造（Tactics/Techniques/Sub-techniques/Software/Groups）を理解する。
- 実務（SOC/Threat Intel/Detection）でATT&CKがどう使われるかを知る。  
- CTI（Cyber Threat Intelligence）とATT&CK Matrixを使って脅威をプロファイルする。 
- MITREの他フレームワーク（CAR、D3FENDなど）があることを把握する（今回は存在認知が目的）。

---

## Task 2：ATT&CK Matrixの見方（迷子にならない手順）
### 基本の追い方（おすすめ）
1. **Tactic（攻撃者の目的）**を決める  
2. そのTactic配下の**Technique（具体的手法）**を探す  
3. 必要なら**Sub-technique**まで降りる  
4. そこから **Mitigations / Detections / Procedure Examples** を読む（防御側に直結）
### もう一つの追い方（CTI/SOC向け）
- **Groups（脅威アクター）** → **Techniques** → **Software** の順  
  「このアクターが何をやるか」「何を使うか」がまとまって見える。 

---

## Task 3：Mustang Panda（G0129）を例に調査（やったこと）
### 目的
- 拠点（所属/背景）の確認  
- ReconnaissanceのTactic IDを特定  
- Access Token Manipulationに関連する情報（Technique/Software）を辿る

### 手順（今回の作業ログ）
- ATT&CK Matrixを見ながら、Taskの質問に対応する **ID** や **拠点** を探した。  
- Access Token ManipulationのSoftwareはMatrix上で見つけづらく、最終的に **Groupページの一覧**から辿って見つけた（例：Cobalt Strike）。

### 参照できる公式ページ（調査の起点）
- **Mustang Panda（G0129）**：中国系のサイバー諜報アクターとして整理されている。 
- **Reconnaissance（TA0043）**：Tacticの一つで、情報収集フェーズ。 
- **Access Token Manipulation（T1134）**：権限/コンテキストを変えるためにアクセストークンを操作するTechnique。 
- **Cobalt Strike（S0154）**：商用RAT/フレームワークとしてSoftwareページがある（Groupページからも辿れる）。

---

## つまずきメモ（重要：これ、実務でも起きる）
### 症状
- 「Technique（Access Token Manipulation）」からSoftwareを探そうとして、Matrix上で見つけられなかった。

### 解決パターン（次から迷わない）
- Softwareを探したいときは、**Technique起点より Group起点の方が早い**ことが多い。  
  - **Groupページ**には「このアクターが使うSoftware/Techniques」が整理されている。  
- Techniqueページでは、まず **Procedure Examples** を見る  
  - そこに“どういうツール/手順で実行されるか”のヒントが出ることがある。

---

## SOC L1的に「仕事に直結する」使い方（最小）
- 目の前のアラートを **Tactic/Technique** に紐づける（共通言語化） 
- そのTechniqueページの **Detections / Mitigations** を拾って  
  - 「次に見るログ」  
  - 「エスカレーション条件」  
  - 「抑止（設定/対策）」  
  をメモに落とす。 

---

## 次にやる（最小アクション）
- Task4以降に進む前に、今回のメモに1行だけ追記：
  - 「Group起点で Software を辿る」  
  - 「Techniqueページは Detections / Mitigations / Procedure Examples を先に見る」
