# 実写画像・二次元画像 自動分類ツール（Windows / 無料環境）

## 概要
このプロジェクトは、  **AI（深層学習）を用いてフォルダ内の画像を自動判別し、  「実写画像」と「二次元画像（アニメ・イラスト・スクリーンショット）」に分類するツール**です。

- 学習：Google Colab（無料・GPU使用）
- 実行：Windows ローカル環境（Anaconda + Python）
- モデル保存形式：`.keras`（Keras 推奨形式）

---

## 使用技術
- Python 3.x
- TensorFlow / Keras
- NumPy
- Pillow
- OpenCV
- scikit-learn
- matplotlib
- Anaconda（仮想環境管理）
- Google Colab（学習用）

---

## 全体構成と役割分担
| 作業 | 環境 |
|----|----|
| データセット準備 | Google Drive |
| モデル学習 | Google Colab |
| モデル保存 | Google Drive |
| 画像分類 | Windows（ローカル） |

---

## ① Anaconda のインストール（Windows）
Anaconda は **Python の実行環境を安全に分離して管理できるツール**です。

以下の公式サイトからダウンロード  
https://www.anaconda.com/products/distribution

手順は以下を参照  
https://envader.plus/article/530

---

## ② Anaconda Prompt を使う理由
本プロジェクトでは **仮想環境** を使用します。

- Python のバージョン衝突を防ぐ
- ライブラリ管理を明確にする

---

## ③ 仮想環境を作成・有効化
Anaconda Prompt を起動して以下を実行します。

```sh
conda activate myenv
```
(myenv) C:\Users\...
となれば、今はmyenvという箱（仮想環境）の中で作業していることを意味します。

---

## ④ 必要ライブラリのインストール（Windows）
仮想環境myenvが有効な状態で以下を実行します。
```sh
pip install numpy tensorflow pillow opencv-python scikit-learn matplotlib
```

## ⑤ 分類スクリプトの作成
作業フォルダで VS Code を起動しclassify.pyを作成するため以下を実行します。
```sh
code classify.py　（メモ帳を使う場合はnotepad classify.pyでもよい）
```
（コードはアップロードされているものを参照）

## ⑥ スクリプトの実行
classify.pyと同じディレクトリ内にとanime_real_model.kerasを置き、以下を実行します。
```sh
python classify.py
```
以上により、任意のフォルダ内の画像がrealとanimeファイルに分かれます。

# 分類をカスタムしたい場合(anime_real_model.kerasの変更）

## ①データセット構成
Google Driveを以下の構成にし、realとanime内に分類したいパターンに分けて写真を入れます。（最低10枚は必要）
```sh
MyDrive/
 └─ dataset/
     ├─ real/
     └─ anime/
```
## ②KERASファイルを作成
任意の場所で新しいGoogle Colabノートを作成し、以下のコードを実行します。
```sh
from google.colab import drive
drive.mount('/content/drive')
```
これはGoogle Drive をマウントするためのコードです。
```sh
data_dir = "/content/drive/MyDrive/dataset"
```
これは①でのdatasetにアクセスするためのコードです。
```sh
```
```sh
```
