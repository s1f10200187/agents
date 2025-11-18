# Claude Code プラグイン：オーケストレーションと自動化

> **⚡ Sonnet 4.5 & Haiku 4.5 対応** — 全エージェントが最新モデルとハイブリッドオーケストレーションに最適化されています
>
> **🎯 エージェントスキル有効** — 47の専門スキルがプログレッシブディスクロージャーでClaudeの機能を拡張します

[Claude Code](https://docs.claude.com/en/docs/claude-code/overview)向けの、**85の専門AIエージェント**、**15のマルチエージェントワークフローオーケストレーター**、**47のエージェントスキル**、**44の開発ツール**を**63の集中型単一目的プラグイン**に統合した、包括的な本番環境対応システムです。

## 概要

この統合リポジトリは、現代のソフトウェア開発における知的自動化とマルチエージェントオーケストレーションに必要なすべてを提供します：

- **63の集中型プラグイン** - 最小限のトークン使用量と組み合わせ可能性に最適化された、粒度の細かい単一目的プラグイン
- **85の専門エージェント** - アーキテクチャ、言語、インフラストラクチャ、品質、データ/AI、ドキュメント、ビジネスオペレーション、SEOにわたる深い知識を持つドメインエキスパート
- **47のエージェントスキル** - 専門知識のためのプログレッシブディスクロージャーを備えたモジュール式知識パッケージ
- **15のワークフローオーケストレーター** - フルスタック開発、セキュリティ強化、MLパイプライン、インシデント対応などの複雑な操作のためのマルチエージェント調整システム
- **44の開発ツール** - プロジェクトスキャフォールディング、セキュリティスキャン、テスト自動化、インフラストラクチャセットアップを含む最適化されたユーティリティ

### 主な機能

- **粒度の細かいプラグインアーキテクチャ**: 最小限のトークン使用量に最適化された63の集中型プラグイン
- **包括的なツール**: テスト生成、スキャフォールディング、セキュリティスキャンを含む44の開発ツール
- **100% エージェントカバレッジ**: すべてのプラグインに専門エージェントが含まれています
- **エージェントスキル**: プログレッシブディスクロージャーとトークン効率のための47の専門スキル
- **明確な整理**: 簡単に発見できる1-6個のプラグインを持つ23のカテゴリー
- **効率的な設計**: プラグインあたり平均3.4コンポーネント（Anthropicの2-8パターンに従う）

### 仕組み

各プラグインは、独自のエージェント、コマンド、スキルを持って完全に分離されています：

- **必要なものだけをインストール** - 各プラグインは特定のエージェント、コマンド、スキルのみを読み込みます
- **最小限のトークン使用量** - 不要なリソースはコンテキストに読み込まれません
- **組み合わせ自由** - 複雑なワークフローのために複数のプラグインを組み合わせられます
- **明確な境界** - 各プラグインには単一の集中した目的があります
- **プログレッシブディスクロージャー** - スキルは起動時にのみ知識を読み込みます

**例**: `python-development`をインストールすると、3つのPythonエージェント、1つのスキャフォールディングツールを読み込み、5つのスキルを利用可能にします（約300トークン）。マーケットプレイス全体ではありません。

## クイックスタート

### ステップ 1: マーケットプレイスを追加

Claude Codeにこのマーケットプレイスを追加します：

```bash
/plugin marketplace add wshobson/agents
```

これにより63のすべてのプラグインがインストール可能になりますが、**エージェントやツールはコンテキストに読み込まれません**。

### ステップ 2: プラグインをインストール

利用可能なプラグインを閲覧：

```bash
/plugin
```

必要なプラグインをインストール：

```bash
# 必須の開発プラグイン
/plugin install python-development          # 5つの専門スキルを持つPython
/plugin install javascript-typescript       # 4つの専門スキルを持つJS/TS
/plugin install backend-development         # 3つのアーキテクチャスキルを持つバックエンドAPI

# インフラストラクチャとオペレーション
/plugin install kubernetes-operations       # 4つのデプロイメントスキルを持つK8s
/plugin install cloud-infrastructure        # 4つのクラウドスキルを持つAWS/Azure/GCP

# セキュリティと品質
/plugin install security-scanning           # セキュリティスキルを持つSAST
/plugin install code-review-ai             # AI駆動のコードレビュー

# フルスタックオーケストレーション
/plugin install full-stack-orchestration   # マルチエージェントワークフロー
```

インストールされた各プラグインは、Claudeのコンテキストに**特定のエージェント、コマンド、スキルのみ**を読み込みます。

## ドキュメント

### コアガイド

- **[プラグインリファレンス](docs/plugins.md)** - 全63プラグインの完全なカタログ
- **[エージェントリファレンス](docs/agents.md)** - カテゴリー別に整理された全85エージェント
- **[エージェントスキル](docs/agent-skills.md)** - プログレッシブディスクロージャーを備えた47の専門スキル
- **[使用ガイド](docs/usage.md)** - コマンド、ワークフロー、ベストプラクティス
- **[アーキテクチャ](docs/architecture.md)** - 設計原則とパターン

### クイックリンク

- [インストール](#クイックスタート) - 2ステップで始める
- [必須プラグイン](docs/plugins.md#quick-start---essential-plugins) - すぐに生産性を高めるトッププラグイン
- [コマンドリファレンス](docs/usage.md#command-reference-by-category) - カテゴリー別に整理されたすべてのスラッシュコマンド
- [マルチエージェントワークフロー](docs/usage.md#multi-agent-workflow-examples) - 事前設定されたオーケストレーションの例
- [モデル構成](docs/agents.md#model-configuration) - Haiku/Sonnetハイブリッドオーケストレーション

## 新機能

### エージェントスキル（14プラグインにわたる47スキル）

Anthropicのプログレッシブディスクロージャーアーキテクチャに従った専門知識パッケージ：

**言語開発:**
- **Python** (5スキル): 非同期パターン、テスト、パッケージング、パフォーマンス、UVパッケージマネージャー
- **JavaScript/TypeScript** (4スキル): 高度な型、Node.jsパターン、テスト、最新のES6+

**インフラストラクチャとDevOps:**
- **Kubernetes** (4スキル): マニフェスト、Helmチャート、GitOps、セキュリティポリシー
- **クラウドインフラストラクチャ** (4スキル): Terraform、マルチクラウド、ハイブリッドネットワーキング、コスト最適化
- **CI/CD** (4スキル): パイプライン設計、GitHub Actions、GitLab CI、シークレット管理

**開発とアーキテクチャ:**
- **バックエンド** (3スキル): API設計、アーキテクチャパターン、マイクロサービス
- **LLMアプリケーション** (4スキル): LangChain、プロンプトエンジニアリング、RAG、評価

**ブロックチェーンとWeb3** (4スキル): DeFiプロトコル、NFT規格、Solidityセキュリティ、Web3テスト

**その他:** フレームワーク移行、オブザーバビリティ、決済処理、MLオペレーション、セキュリティスキャン

[→ 完全なスキルドキュメントを見る](docs/agent-skills.md)

### ハイブリッドモデルオーケストレーション

最適なパフォーマンスとコストのための戦略的モデル割り当て：
- **47 Haikuエージェント** - 決定的なタスクのための高速実行
- **97 Sonnetエージェント** - 複雑な推論とアーキテクチャ

オーケストレーションパターンは効率のためにモデルを組み合わせます：
```
Sonnet (計画) → Haiku (実行) → Sonnet (レビュー)
```

[→ モデル構成の詳細を見る](docs/agents.md#model-configuration)

## 人気のユースケース

### フルスタック機能開発

```bash
/full-stack-orchestration:full-stack-feature "OAuth2を使用したユーザー認証"
```

7つ以上のエージェントを調整：backend-architect → database-architect → frontend-developer → test-automator → security-auditor → deployment-engineer → observability-engineer

[→ すべてのワークフロー例を見る](docs/usage.md#multi-agent-workflow-examples)

### セキュリティ強化

```bash
/security-scanning:security-hardening --level comprehensive
```

SAST、依存関係スキャン、コードレビューによるマルチエージェントセキュリティ評価。

### 最新ツールを使用したPython開発

```bash
/python-development:python-scaffold fastapi-microservice
```

非同期パターンを備えた本番環境対応のFastAPIプロジェクトを作成し、スキルを起動：
- `async-python-patterns` - AsyncIOと並行処理
- `python-testing-patterns` - pytestとフィクスチャ
- `uv-package-manager` - 高速依存関係管理

### Kubernetesデプロイメント

```bash
# k8sスキルを自動的に起動
"HelmチャートとGitOpsを使用した本番環境のKubernetesデプロイメントを作成"
```

本番グレードの設定のための4つの専門スキルを持つkubernetes-architectエージェントを使用。

[→ 完全な使用ガイドを見る](docs/usage.md)

## プラグインカテゴリー

**23カテゴリー、63プラグイン:**

- 🎨 **開発** (4) - デバッグ、バックエンド、フロントエンド、マルチプラットフォーム
- 📚 **ドキュメント** (2) - コードドキュメント、API仕様、図表
- 🔄 **ワークフロー** (3) - git、フルスタック、TDD
- ✅ **テスト** (2) - ユニットテスト、TDDワークフロー
- 🔍 **品質** (3) - コードレビュー、包括的レビュー、パフォーマンス
- 🤖 **AI & ML** (4) - LLMアプリ、エージェントオーケストレーション、コンテキスト、MLOps
- 📊 **データ** (2) - データエンジニアリング、データ検証
- 🗄️ **データベース** (2) - データベース設計、マイグレーション
- 🚨 **オペレーション** (4) - インシデント対応、診断、分散デバッグ、オブザーバビリティ
- ⚡ **パフォーマンス** (2) - アプリケーションパフォーマンス、データベース/クラウド最適化
- ☁️ **インフラストラクチャ** (5) - デプロイメント、検証、Kubernetes、クラウド、CI/CD
- 🔒 **セキュリティ** (4) - スキャン、コンプライアンス、バックエンド/API、フロントエンド/モバイル
- 💻 **言語** (7) - Python、JS/TS、システム、JVM、スクリプト、関数型、組込み
- 🔗 **ブロックチェーン** (1) - スマートコントラクト、DeFi、Web3
- 💰 **金融** (1) - クオンツトレーディング、リスク管理
- 💳 **決済** (1) - Stripe、PayPal、請求
- 🎮 **ゲーム** (1) - Unity、Minecraftプラグイン
- 📢 **マーケティング** (4) - SEOコンテンツ、テクニカルSEO、SEO分析、コンテンツマーケティング
- 💼 **ビジネス** (3) - 分析、HR/法務、顧客/営業
- その他...

[→ 完全なプラグインカタログを見る](docs/plugins.md)

## アーキテクチャのハイライト

### 粒度の細かい設計

- **単一責任** - 各プラグインは一つのことをうまくやります
- **最小限のトークン使用量** - プラグインあたり平均3.4コンポーネント
- **組み合わせ可能** - 複雑なワークフローのために組み合わせ可能
- **100% カバレッジ** - すべての85エージェントがプラグイン全体でアクセス可能

### プログレッシブディスクロージャー（スキル）

トークン効率のための3層アーキテクチャ：
1. **メタデータ** - 名前と起動基準（常に読み込まれる）
2. **指示** - コアガイダンス（起動時に読み込まれる）
3. **リソース** - 例とテンプレート（要求時に読み込まれる）

### リポジトリ構造

```
claude-agents/
├── .claude-plugin/
│   └── marketplace.json          # 63プラグイン
├── plugins/
│   ├── python-development/
│   │   ├── agents/               # 3人のPythonエキスパート
│   │   ├── commands/             # スキャフォールディングツール
│   │   └── skills/               # 5つの専門スキル
│   ├── kubernetes-operations/
│   │   ├── agents/               # K8sアーキテクト
│   │   ├── commands/             # デプロイメントツール
│   │   └── skills/               # 4つのK8sスキル
│   └── ... (さらに61プラグイン)
├── docs/                          # 包括的なドキュメント
└── README.md                      # このファイル
```

[→ アーキテクチャの詳細を見る](docs/architecture.md)

## 貢献

新しいエージェント、スキル、またはコマンドを追加するには：

1. `plugins/`内の適切なプラグインディレクトリを特定または作成します
2. 適切なサブディレクトリに`.md`ファイルを作成します：
   - `agents/` - 専門エージェント用
   - `commands/` - ツールとワークフロー用
   - `skills/` - モジュール式知識パッケージ用
3. 命名規則に従います（小文字、ハイフン区切り）
4. 明確な起動基準と包括的なコンテンツを書きます
5. `.claude-plugin/marketplace.json`のプラグイン定義を更新します

詳細なガイドラインについては[アーキテクチャドキュメント](docs/architecture.md)を参照してください。

## リソース

### ドキュメント
- [Claude Code ドキュメント](https://docs.claude.com/en/docs/claude-code/overview)
- [プラグインガイド](https://docs.claude.com/en/docs/claude-code/plugins)
- [サブエージェントガイド](https://docs.claude.com/en/docs/claude-code/sub-agents)
- [エージェントスキルガイド](https://docs.claude.com/en/docs/agents-and-tools/agent-skills/overview)
- [スラッシュコマンドリファレンス](https://docs.claude.com/en/docs/claude-code/slash-commands)

### このリポジトリ
- [プラグインリファレンス](docs/plugins.md)
- [エージェントリファレンス](docs/agents.md)
- [エージェントスキルガイド](docs/agent-skills.md)
- [使用ガイド](docs/usage.md)
- [アーキテクチャ](docs/architecture.md)

## ライセンス

MITライセンス - 詳細は[LICENSE](LICENSE)ファイルを参照してください。

## スター履歴

[![Star History Chart](https://api.star-history.com/svg?repos=wshobson/agents&type=date&legend=top-left)](https://www.star-history.com/#wshobson/agents&type=date&legend=top-left)
