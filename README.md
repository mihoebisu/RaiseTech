# RaiseTech課題提出用リポジトリ

## 概要

- 第5回課題で使用したサンプルアプリケーションはCRUD 処理が出来る簡単な Rails アプリケーションです。

## 動作環境

### ruby

```bash
3.1.2
```

### Bundler
```bash
2.3.14
```

### Rails

```bash
7.0.4
```

### Node

```bash
v17.9.1
```

### yarn

```bash
1.22.19
```

### DB エンジン

- MySQLを採用しています。


## CloudFormationで構築した環境の構成図
![AWS構成図05 drawio](https://github.com/mihoebisu/RaiseTech/assets/130433491/8a40300d-eff7-45db-b48b-6e27ab7564ff)

## AWS 環境構成説明

### 概要

このリポジトリに掲載されているAWS構成図は、AWS CloudFormationを使用して設計・構築したRailsアプリケーションのインフラストラクチャを示しています。

### 主要コンポーネント

#### EC2 (Elastic Compute Cloud)

- **シングル構成**: 今回は簡単なRailsアプリケーションを実行するため、1台のEC2インスタンスを使用しています。

#### RDS (Relational Database Service)

- **MySQL**: アプリケーションのデータベースとしてAWS RDS MySQLを採用しています。

#### ALB (Application Load Balancer)

- **ロードバランサー**: EC2インスタンスの前に配置して、受信するHTTP/HTTPSトラフィックをEC2にルーティングします。

#### S3 (Simple Storage Service)

- **ファイルストレージ**: アプリケーションで使用するファイルはS3バケットに保存しています。

### 設計の背後にある理論的根拠

1. **EC2のシングル構成**: コストと複雑性を抑えるため、今回は1台のEC2インスタンスのみを使用しています。
  
2. **RDSの採用**: 管理が容易で、スケーラビリティと高可用性が求められるデータベース要件に適しています。

3. **ALBの配置**: アプリケーションの拡張性と可用性を考慮し、ALBを使用しています。

4. **S3の利用**: データの耐久性と可用性を確保するため、そしてスケーラビリティがあるため、ファイルの保存先としてS3を採用しています。

