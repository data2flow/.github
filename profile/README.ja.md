<div align="center">

🌐 **[한국어](./README.md)** | **[English](./README.en.md)** | **日本語** | **[简体中文](./README.zh.md)**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./logo-dark.svg">
  <img alt="data2flow" src="./logo-light.svg" width="300">
</picture>

**見守るだけの運用は、もう終わり。これからは、自ら解決します。**

建物内のセンサーデータを設定だけで接続・整理・分析し、<br>その結果に応じて設備まで動かす AIoT プラットフォーム

</div>

---

## data2flow とは

> 実習室の CO2 が 1,000ppm を超えた状態が 5 分続きます。<br>
> → data2flow が検知して換気装置をオンにします。<br>
> → 15 分以内に下がらなければ、担当者に「制御効果なし」の通知を送ります。<br>
> → 1 か月後、基準超過時間がどれだけ減ったかをレポートで示します。

この流れ全体を、コードをデプロイせずに **画面の設定とフロー(図)** で作ります。名前のとおり、**data** が **flow** に沿って整形 → 分析 → 行動へとつながります。

## 5 つのステップ

| ステップ | 内容 |
|---|---|
| **接続** | LoRaWAN(ChirpStack)・MQTT・Webhook・エッジゲートウェイのセンサーを画面設定だけで接続。受信データから新しい機器を見つけ、管理者の承認で登録 |
| **整形** | メーカーごとに異なるデータを同じ形に。サンドボックス JavaScript スクリプト、品質コード、原本保管と再処理 |
| **理解** | 選ぶだけで実行できる分析テンプレート(快適性・空間利用・異常検知・エネルギー)と AI による解説 |
| **行動** | フローエディターとルールで検知し、メーカーを問わず同じ制御窓口で設備を動かし、Telegram で通知 |
| **再現** | 実機がなくても仮想空間・仮想センサー・シナリオで自動化を先に検証 |

## 何が違うのか

- **測定 → 基準 → 行動 → 証跡** が一つの製品でつながります。室内空気質の基準判定と準拠レポートまで。
- **データ損失ゼロ、無停止デプロイ。** 再デプロイ中も受信メッセージを 1 件も失いません。
- **ライブ編集。** フローを変更してもエンジンを止めずにすぐ反映します。
- **ベンダー中立の制御。** Capability + Driver + Control Facade で、画面・フロー・AI が同じ窓口を使います。
- **オープンソースライセンス方針。** Apache・MIT・BSD などの許容ライセンスのみを製品に含めます。

## リポジトリ

| リポジトリ | 役割 | 技術 |
|---|---|---|
| [data2flow-docs](https://github.com/data2flow/data2flow-docs) | 仕様・設計・決定記録・ストーリーボード | Markdown |
| data2flow-web | 画面 + BFF(サーバーレンダリング、セッション) | React Router v7, TypeScript |
| data2flow-api-gateway | ルーティング、トークン確認、ID 伝達 | Spring Cloud Gateway |
| data2flow-auth | ログイン、トークン発行・失効 | Spring Boot 4 |
| data2flow-core-api | 会員・機器・空間・ソース・フロー定義・ルール・ダッシュボード | Spring Boot 4 |
| data2flow-ingress | MQTT 購読、Webhook・エッジ受信 | Spring Boot 4 |
| data2flow-pipeline | デコード、スクリプト、保存、集計 | Spring Boot 4, GraalJS |
| data2flow-flow-engine | フロー・ルール実行、ライブリロード | Spring Boot 4, GraalJS |
| data2flow-action | 設備制御、通知、外部出力 | Spring Boot 4 |
| data2flow-simulator | 仮想空間・センサー・設備、シナリオ | Spring Boot 4 |
| data2flow-ai | 結果解説、レポート、チャットボット、MCP サーバー | Spring AI |
| data2flow-analytics | 分析テンプレート、リアルタイム推論 | Python, FastAPI |
| data2flow-contracts | メッセージスキーマ、共通レスポンス・エラー形式 | Java, JSON Schema |
| data2flow-manifests | Kubernetes デプロイ(GitOps) | Kustomize, Argo CD |

## 技術スタック

`React Router v7` `TypeScript` `Spring Boot 4` `Java 21` `Spring AI` `Python FastAPI` `PostgreSQL 18 + pgvector` `RabbitMQ Streams` `Redis` `GraalJS` `Kubernetes` `Argo CD`

## リリース

バージョンごとにリリースノートを 4 言語(한국어・English・日本語・简体中文)で公開し、すべてのサービスリポジトリに同じ git タグ(`vX.Y`)を付けます。まだ最初のリリース前です。

## 現在の段階

ドキュメント先行で進めています。仕様 763 件、受け入れテスト 1,096 件、画面ストーリーボード 155 シーン、ERD、OpenAPI・AsyncAPI 仕様が完成し、最初の実装マイルストーン(M0)を準備しています。

<div align="center"><sub>Made at NHN Academy · data → flow</sub></div>
