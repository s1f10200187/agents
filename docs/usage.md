# 使用ガイド

エージェント、スラッシュコマンド、マルチエージェントワークフローの使用に関する完全ガイド。

## 概要

プラグインエコシステムは2つの主要なインターフェースを提供します：

1. **スラッシュコマンド** - ツールとワークフローの直接呼び出し
2. **自然言語** - Claudeがどのエージェントを使用するかを判断

## スラッシュコマンド

スラッシュコマンドは、エージェントとワークフローを操作するための主要なインターフェースです。各プラグインは、直接実行できる名前空間付きコマンドを提供します。

### コマンド形式

```bash
/plugin-name:command-name [arguments]
```

### コマンドの検出

インストール済みプラグインから利用可能なすべてのスラッシュコマンドを一覧表示：

```bash
/plugin
```

### スラッシュコマンドの利点

- **直接呼び出し** - 自然言語で説明する必要がありません
- **構造化された引数** - パラメータを明示的に渡して正確な制御が可能
- **組み合わせ可能性** - コマンドを連結して複雑なワークフローを構築
- **発見可能性** - `/plugin`を使用して利用可能なすべてのコマンドを確認

## 自然言語

Claudeにどのスペシャリストを使用するかを判断させる必要がある場合、エージェントは自然言語を通じて呼び出すこともできます：

```
"Use backend-architect to design the authentication API"
"Have security-auditor scan for OWASP vulnerabilities"
"Get performance-engineer to optimize this database query"
```

Claude Codeは、あなたのリクエストに基づいて適切なエージェントを自動的に選択して調整します。

## カテゴリ別コマンドリファレンス

### 開発・機能

| コマンド | 説明 |
|---------|-------------|
| `/backend-development:feature-development` | エンドツーエンドのバックエンド機能開発 |
| `/full-stack-orchestration:full-stack-feature` | 完全なフルスタック機能の実装 |
| `/multi-platform-apps:multi-platform` | クロスプラットフォームアプリ開発の調整 |

### テスト・品質

| コマンド | 説明 |
|---------|-------------|
| `/unit-testing:test-generate` | 包括的なユニットテストの生成 |
| `/tdd-workflows:tdd-cycle` | 完全なTDD レッド・グリーン・リファクタサイクル |
| `/tdd-workflows:tdd-red` | 最初に失敗するテストを作成 |
| `/tdd-workflows:tdd-green` | テストをパスするコードを実装 |
| `/tdd-workflows:tdd-refactor` | パスしたテストでリファクタリング |

### コード品質・レビュー

| コマンド | 説明 |
|---------|-------------|
| `/code-review-ai:ai-review` | AI駆動のコードレビュー |
| `/comprehensive-review:full-review` | 多角的な分析 |
| `/comprehensive-review:pr-enhance` | プルリクエストの強化 |

### デバッグ・トラブルシューティング

| コマンド | 説明 |
|---------|-------------|
| `/debugging-toolkit:smart-debug` | インタラクティブなスマートデバッグ |
| `/incident-response:incident-response` | 本番環境のインシデント管理 |
| `/incident-response:smart-fix` | 自動インシデント解決 |
| `/error-debugging:error-analysis` | 詳細なエラー分析 |
| `/error-debugging:error-trace` | スタックトレースのデバッグ |
| `/error-diagnostics:smart-debug` | スマート診断デバッグ |
| `/distributed-debugging:debug-trace` | 分散システムのトレース |

### セキュリティ

| コマンド | 説明 |
|---------|-------------|
| `/security-scanning:security-hardening` | 包括的なセキュリティ強化 |
| `/security-scanning:security-sast` | 静的アプリケーションセキュリティテスト |
| `/security-scanning:security-dependencies` | 依存関係の脆弱性スキャン |
| `/security-compliance:compliance-check` | SOC2/HIPAA/GDPR コンプライアンス |
| `/frontend-mobile-security:xss-scan` | XSS脆弱性スキャン |

### インフラストラクチャ・デプロイメント

| コマンド | 説明 |
|---------|-------------|
| `/observability-monitoring:monitor-setup` | 監視インフラストラクチャのセットアップ |
| `/observability-monitoring:slo-implement` | SLO/SLIメトリクスの実装 |
| `/deployment-validation:config-validate` | デプロイ前の検証 |
| `/cicd-automation:workflow-automate` | CI/CDパイプラインの自動化 |

### データ・機械学習

| コマンド | 説明 |
|---------|-------------|
| `/machine-learning-ops:ml-pipeline` | ML学習パイプラインのオーケストレーション |
| `/data-engineering:data-pipeline` | ETL/ELTパイプラインの構築 |
| `/data-engineering:data-driven-feature` | データ駆動型機能開発 |

### ドキュメント

| コマンド | 説明 |
|---------|-------------|
| `/code-documentation:doc-generate` | 包括的なドキュメントの生成 |
| `/code-documentation:code-explain` | コード機能の説明 |
| `/documentation-generation:doc-generate` | OpenAPI仕様、図、チュートリアル |

### リファクタリング・メンテナンス

| コマンド | 説明 |
|---------|-------------|
| `/code-refactoring:refactor-clean` | コードのクリーンアップとリファクタリング |
| `/code-refactoring:tech-debt` | 技術的負債の管理 |
| `/codebase-cleanup:deps-audit` | 依存関係の監査 |
| `/codebase-cleanup:tech-debt` | 技術的負債の削減 |
| `/framework-migration:legacy-modernize` | レガシーコードの近代化 |
| `/framework-migration:code-migrate` | フレームワークの移行 |
| `/framework-migration:deps-upgrade` | 依存関係のアップグレード |

### データベース

| コマンド | 説明 |
|---------|-------------|
| `/database-migrations:sql-migrations` | SQLマイグレーションの自動化 |
| `/database-migrations:migration-observability` | マイグレーションの監視 |
| `/database-cloud-optimization:cost-optimize` | データベースとクラウドの最適化 |

### Git・PRワークフロー

| コマンド | 説明 |
|---------|-------------|
| `/git-pr-workflows:pr-enhance` | プルリクエスト品質の向上 |
| `/git-pr-workflows:onboard` | チームオンボーディングの自動化 |
| `/git-pr-workflows:git-workflow` | Gitワークフローの自動化 |

### プロジェクトスキャフォールディング

| コマンド | 説明 |
|---------|-------------|
| `/python-development:python-scaffold` | FastAPI/Djangoプロジェクトのセットアップ |
| `/javascript-typescript:typescript-scaffold` | Next.js/React + Viteのセットアップ |
| `/systems-programming:rust-project` | Rustプロジェクトのスキャフォールディング |

### AI・LLM開発

| コマンド | 説明 |
|---------|-------------|
| `/llm-application-dev:langchain-agent` | LangChainエージェント開発 |
| `/llm-application-dev:ai-assistant` | AIアシスタントの実装 |
| `/llm-application-dev:prompt-optimize` | プロンプトエンジニアリングの最適化 |
| `/agent-orchestration:multi-agent-optimize` | マルチエージェントの最適化 |
| `/agent-orchestration:improve-agent` | エージェント改善ワークフロー |

### テスト・パフォーマンス

| コマンド | 説明 |
|---------|-------------|
| `/performance-testing-review:ai-review` | パフォーマンス分析 |
| `/application-performance:performance-optimization` | アプリの最適化 |

### チームコラボレーション

| コマンド | 説明 |
|---------|-------------|
| `/team-collaboration:issue` | 課題管理の自動化 |
| `/team-collaboration:standup-notes` | スタンドアップノートの生成 |

### アクセシビリティ

| コマンド | 説明 |
|---------|-------------|
| `/accessibility-compliance:accessibility-audit` | WCAGコンプライアンス監査 |

### API開発

| コマンド | 説明 |
|---------|-------------|
| `/api-testing-observability:api-mock` | APIモックとテスト |

### コンテキスト管理

| コマンド | 説明 |
|---------|-------------|
| `/context-management:context-save` | 会話コンテキストの保存 |
| `/context-management:context-restore` | 以前のコンテキストの復元 |

## マルチエージェントワークフローの例

プラグインは、スラッシュコマンドでアクセス可能な事前設定されたマルチエージェントワークフローを提供します。

### フルスタック開発

```bash
# コマンドベースのワークフロー呼び出し
/full-stack-orchestration:full-stack-feature "user dashboard with real-time analytics"

# 自然言語による代替方法
"Implement user dashboard with real-time analytics"
```

**オーケストレーション:** backend-architect → database-architect → frontend-developer → test-automator → security-auditor → deployment-engineer → observability-engineer

**実行内容:**

1. マイグレーション付きデータベーススキーマ設計
2. バックエンドAPI実装（REST/GraphQL）
3. 状態管理を備えたフロントエンドコンポーネント
4. 包括的なテストスイート（ユニット/統合/E2E）
5. セキュリティ監査と強化
6. フィーチャーフラグ付きCI/CDパイプラインのセットアップ
7. 可観測性と監視の設定

### セキュリティ強化

```bash
# 包括的なセキュリティ評価と修復
/security-scanning:security-hardening --level comprehensive

# 自然言語による代替方法
"Perform security audit and implement OWASP best practices"
```

**オーケストレーション:** security-auditor → backend-security-coder → frontend-security-coder → mobile-security-coder → test-automator

### データ/MLパイプライン

```bash
# 本番デプロイメント付きML機能開発
/machine-learning-ops:ml-pipeline "customer churn prediction model"

# 自然言語による代替方法
"Build customer churn prediction model with deployment"
```

**オーケストレーション:** data-scientist → data-engineer → ml-engineer → mlops-engineer → performance-engineer

### インシデント対応

```bash
# 根本原因分析を伴うスマートデバッグ
/incident-response:smart-fix "production memory leak in payment service"

# 自然言語による代替方法
"Debug production memory leak and create runbook"
```

**オーケストレーション:** incident-responder → devops-troubleshooter → debugger → error-detective → observability-engineer

## コマンド引数とオプション

多くのスラッシュコマンドは、正確な制御のための引数をサポートしています：

```bash
# 特定ファイルのテスト生成
/unit-testing:test-generate src/api/users.py

# 方法論指定付き機能開発
/backend-development:feature-development OAuth2 integration with social login

# セキュリティ依存関係スキャン
/security-scanning:security-dependencies

# コンポーネントのスキャフォールディング
/frontend-mobile-development:component-scaffold UserProfile component with hooks

# TDDワークフローサイクル
/tdd-workflows:tdd-red User can reset password
/tdd-workflows:tdd-green
/tdd-workflows:tdd-refactor

# スマートデバッグ
/debugging-toolkit:smart-debug memory leak in checkout flow

# Pythonプロジェクトのスキャフォールディング
/python-development:python-scaffold fastapi-microservice
```

## 自然言語とコマンドの組み合わせ

最適な柔軟性のために、両方のアプローチを組み合わせることができます：

```
# 構造化されたワークフローのためにコマンドで開始
/full-stack-orchestration:full-stack-feature "payment processing"

# 次に自然言語でガイダンスを提供
"Ensure PCI-DSS compliance and integrate with Stripe"
"Add retry logic for failed transactions"
"Set up fraud detection rules"
```

## ベストプラクティス

### スラッシュコマンドを使用する場合

- **構造化されたワークフロー** - 明確なフェーズを持つ複数ステップのプロセス
- **反復タスク** - 頻繁に実行する操作
- **正確な制御** - 特定のパラメータが必要な場合
- **発見** - 利用可能な機能を探索する場合

### 自然言語を使用する場合

- **探索的作業** - どのツールを使用すべきかわからない場合
- **複雑な推論** - Claudeが複数のエージェントを調整する必要がある場合
- **文脈に基づく決定** - 適切なアプローチが状況に依存する場合
- **アドホックタスク** - コマンドに適合しない一回限りの操作

### ワークフローの構成

複雑なシナリオのために複数のプラグインを組み合わせる：

```bash
# 1. 機能開発から始める
/backend-development:feature-development payment processing API

# 2. セキュリティ強化を追加
/security-scanning:security-hardening

# 3. 包括的なテストを生成
/unit-testing:test-generate

# 4. 実装をレビュー
/code-review-ai:ai-review

# 5. CI/CDをセットアップ
/cicd-automation:workflow-automate

# 6. 監視を追加
/observability-monitoring:monitor-setup
```

## エージェントスキルの統合

エージェントスキルはコマンドと連携して深い専門知識を提供します：

```
User: "Set up FastAPI project with async patterns"
→ 有効化: fastapi-templates skill
→ 呼び出し: /python-development:python-scaffold
→ 結果: ベストプラクティスを備えた本番環境対応のFastAPIプロジェクト

User: "Implement Kubernetes deployment with Helm"
→ 有効化: helm-chart-scaffolding, k8s-manifest-generator skills
→ ガイド: kubernetes-architect agent
→ 結果: Helmチャート付きの本番グレードK8sマニフェスト
```

47の専門スキルの詳細については、[Agent Skills](./agent-skills.md)を参照してください。

## 関連項目

- [Agent Skills](./agent-skills.md) - 専門知識パッケージ
- [Agent Reference](./agents.md) - 完全なエージェントカタログ
- [Plugin Reference](./plugins.md) - 全63プラグイン
- [Architecture](./architecture.md) - 設計原則
