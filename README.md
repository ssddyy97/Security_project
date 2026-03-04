Security Attack Detection API (Machine Learning)
概要

本プロジェクトは、機械学習を用いてWeb攻撃を検知するセキュリティ分析システムです。
入力されたリクエストや文字列データを分析し、SQL InjectionやXSSなどの攻撃パターンを検知します。

PythonとScikit-learnを利用して機械学習モデルを構築し、APIサーバーとして公開することで、外部システムからリアルタイムで攻撃判定を行うことができます。

技術スタック

Python

Scikit-learn

Pandas / NumPy

TF-IDF Vectorizer

Linear SVM

Flask (API Server)

システム構成

システムは以下の流れで動作します。

入力データ
   ↓
TF-IDF ベクトル化
   ↓
機械学習モデル (Linear SVM)
   ↓
攻撃判定
   ↓
APIレスポンス

テキストデータを数値ベクトルに変換し、学習済みモデルによって攻撃か正常かを分類します。

検知可能な攻撃

本システムでは以下のようなWeb攻撃を検知します。

SQL Injection

Cross Site Scripting (XSS)

Command Injection

Normal Request

API 使用例
Request
POST /predict
{
  "text": "<script>alert('XSS')</script>"
}
Response
{
  "result": "XSS attack detected"
}
プロジェクトの目的

本プロジェクトの目的は、Webアプリケーションに対する攻撃パターンを機械学習によって検知するセキュリティシステムを構築することです。

将来的には以下のような機能拡張を予定しています。

リアルタイムログ分析

深層学習モデルの導入

異常検知アルゴリズムの追加

セキュリティ監視システムとの連携
