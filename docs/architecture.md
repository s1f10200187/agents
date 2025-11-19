# アーキテクチャと設計原則

このマーケットプレイスは、粒度、組み合わせ可能性、最小限のトークン使用に焦点を当てた業界のベストプラクティスに従っています。

## コア哲学

### 単一責任の原則

- 各プラグインは**一つのことをうまく実行**（Unix哲学）
- 明確で焦点を絞った目的（5〜10語で説明可能）
- 平均プラグインサイズ：**3.4コンポーネント**（Anthropicの2-8パターンに従う）
- **肥大化したプラグインはゼロ** - すべてのプラグインが焦点を絞り、目的を持っている

### バンドルよりも組み合わせ可能性

- ニーズに基づいてプラグインを組み合わせて使用
- ワークフローオーケストレーターが焦点を絞ったプラグインを構成
- 強制的な機能バンドルなし
- プラグイン間の明確な境界

### コンテキスト効率

- 小さなツール = 高速処理
- LLMコンテキストウィンドウにより適合
- より正確で焦点を絞った応答
- 必要なものだけをインストール

### 保守性

- 単一目的 = 更新が容易
- 明確な境界 = 分離された変更
- 重複の削減 = シンプルなメンテナンス
- 分離された依存関係

## 粒度の細かいプラグインアーキテクチャ

### プラグインの分布

- 特定のユースケースに最適化された**63の焦点を絞ったプラグイン**
- 簡単に発見できるように、各カテゴリに1〜6個のプラグインがある**23の明確なカテゴリ**
- ドメインごとに整理：
  - **Development**: 4プラグイン（デバッグ、バックエンド、フロントエンド、マルチプラットフォーム）
  - **Security**: 4プラグイン（スキャン、コンプライアンス、バックエンドAPI、フロントエンドモバイル）
  - **Operations**: 4プラグイン（インシデント、診断、分散、オブザーバビリティ）
  - **Languages**: 7プラグイン（Python、JS/TS、システム、JVM、スクリプト、関数型、組み込み）
  - **Infrastructure**: 5プラグイン（デプロイメント、検証、K8s、クラウド、CI/CD）
  - その他18の専門カテゴリ

### コンポーネントの内訳

**85の専門エージェント**
- 深い知識を持つドメインエキスパート
- アーキテクチャ、言語、インフラストラクチャ、品質、データ/AI、ドキュメント、ビジネス、SEOにわたって整理
- パフォーマンスとコストのためにモデル最適化（47 Haiku、97 Sonnet）

**15のワークフローオーケストレーター**
- マルチエージェント調整システム
- フルスタック開発、セキュリティ強化、MLパイプライン、インシデント対応などの複雑な操作
- 事前設定されたエージェントワークフロー

**44の開発ツール**
- 最適化されたユーティリティ：
  - プロジェクトスキャフォールディング（Python、TypeScript、Rust）
  - セキュリティスキャン（SAST、依存関係監査、XSS）
  - テスト生成（pytest、Jest）
  - コンポーネントスキャフォールディング（React、React Native）
  - インフラストラクチャセットアップ（Terraform、Kubernetes）

**47のエージェントスキル**
- モジュール式知識パッケージ
- プログレッシブディスクロージャアーキテクチャ
- 14プラグインにわたるドメイン固有の専門知識
- 仕様準拠（Anthropic Agent Skills Specification）

## リポジトリ構造

```
claude-agents/
├── .claude-plugin/
│   └── marketplace.json          # Marketplace catalog (63 plugins)
├── plugins/                       # Isolated plugin directories
│   ├── python-development/
│   │   ├── agents/               # Python language agents
│   │   │   ├── python-pro.md
│   │   │   ├── django-pro.md
│   │   │   └── fastapi-pro.md
│   │   ├── commands/             # Python tooling
│   │   │   └── python-scaffold.md
│   │   └── skills/               # Python skills (5 total)
│   │       ├── async-python-patterns/
│   │       ├── python-testing-patterns/
│   │       ├── python-packaging/
│   │       ├── python-performance-optimization/
│   │       └── uv-package-manager/
│   ├── backend-development/
│   │   ├── agents/
│   │   │   ├── backend-architect.md
│   │   │   ├── graphql-architect.md
│   │   │   └── tdd-orchestrator.md
│   │   ├── commands/
│   │   │   └── feature-development.md
│   │   └── skills/               # Backend skills (3 total)
│   │       ├── api-design-principles/
│   │       ├── architecture-patterns/
│   │       └── microservices-patterns/
│   ├── security-scanning/
│   │   ├── agents/
│   │   │   └── security-auditor.md
│   │   ├── commands/
│   │   │   ├── security-hardening.md
│   │   │   ├── security-sast.md
│   │   │   └── security-dependencies.md
│   │   └── skills/               # Security skills (1 total)
│   │       └── sast-configuration/
│   └── ... (60 more isolated plugins)
├── docs/                          # Documentation
│   ├── agent-skills.md           # Agent Skills guide
│   ├── agents.md                 # Agent reference
│   ├── plugins.md                # Plugin catalog
│   ├── usage.md                  # Usage guide
│   └── architecture.md           # This file
└── README.md                      # Quick start
```

## プラグイン構造

各プラグインには以下が含まれます：

- **agents/** - そのドメインの専門エージェント（オプション）
- **commands/** - そのプラグインに固有のツールとワークフロー（オプション）
- **skills/** - プログレッシブディスクロージャを備えたモジュール式知識パッケージ（オプション）

### 最小要件

- 少なくとも1つのエージェントまたは1つのコマンド
- 明確で焦点を絞った目的
- すべてのファイルに適切なフロントマター
- marketplace.jsonへのエントリ

### プラグインの例

```
plugins/kubernetes-operations/
├── agents/
│   └── kubernetes-architect.md   # K8s architecture and design
├── commands/
│   └── k8s-deploy.md            # Deployment automation
└── skills/
    ├── k8s-manifest-generator/   # Manifest creation skill
    ├── helm-chart-scaffolding/   # Helm chart skill
    ├── gitops-workflow/          # GitOps automation skill
    └── k8s-security-policies/    # Security policy skill
```

## エージェントスキルアーキテクチャ

### プログレッシブディスクロージャ

スキルは、トークン効率のために3層アーキテクチャを使用します：

1. **メタデータ**（フロントマター）：名前とアクティベーション基準（常に読み込まれる）
2. **指示**：コアガイダンスとパターン（アクティベート時に読み込まれる）
3. **リソース**：例とテンプレート（オンデマンドで読み込まれる）

### 仕様準拠

すべてのスキルは[Agent Skills Specification](https://github.com/anthropics/skills/blob/main/agent_skills_spec.md)に従います：

```yaml
---
name: skill-name                  # Required: hyphen-case
description: What the skill does. Use when [trigger]. # Required: < 1024 chars
---

# Skill content with progressive disclosure
```

### メリット

- **トークン効率**：必要な時にのみ関連する知識を読み込む
- **専門知識**：肥大化することなく深いドメイン知識
- **明確なアクティベーション**：明示的なトリガーが望ましくない呼び出しを防ぐ
- **組み合わせ可能性**：ワークフロー全体でスキルを組み合わせて使用
- **保守性**：分離された更新が他のスキルに影響しない

47のスキルの完全な詳細については、[Agent Skills](./agent-skills.md)を参照してください。

## モデル構成戦略

### 2層アーキテクチャ

システムは戦略的にClaude OpusとSonnetモデルを使用します：

| Model | Count | Use Case |
|-------|-------|----------|
| Haiku | 47 agents | 高速実行、決定論的タスク |
| Sonnet | 97 agents | 複雑な推論、アーキテクチャの決定 |

### 選択基準

**Haiku - 高速実行と決定論的タスク**
- 明確に定義された仕様からのコード生成
- 確立されたパターンに従ったテストの作成
- 明確なテンプレートを使用したドキュメント作成
- インフラストラクチャ操作の実行
- データベースクエリの最適化
- カスタマーサポート応答の処理
- SEO最適化タスクの処理
- デプロイメントパイプラインの管理

**Sonnet - 複雑な推論とアーキテクチャ**
- システムアーキテクチャの設計
- テクノロジー選択の決定
- セキュリティ監査の実行
- アーキテクチャパターンのコードレビュー
- 複雑なAI/MLパイプラインの作成
- 言語固有の専門知識の提供
- マルチエージェントワークフローのオーケストレーション
- ビジネスクリティカルな法務/人事問題の処理

### ハイブリッドオーケストレーション

最適なパフォーマンスとコストのためにモデルを組み合わせます：

```
Planning Phase (Sonnet) → Execution Phase (Haiku) → Review Phase (Sonnet)

Example:
backend-architect (Sonnet) designs API
  ↓
Generate endpoints (Haiku) implements spec
  ↓
test-automator (Haiku) creates tests
  ↓
code-reviewer (Sonnet) validates architecture
```

## パフォーマンスと品質

### 最適化されたトークン使用

- **分離されたプラグイン**は必要なものだけを読み込む
- **粒度の細かいアーキテクチャ**が不要なコンテキストを削減
- **プログレッシブディスクロージャ**（スキル）がオンデマンドで知識を読み込む
- **明確な境界**がコンテキストの汚染を防ぐ

### コンポーネントカバレッジ

- **100%のエージェントカバレッジ** - すべてのプラグインに少なくとも1つのエージェントが含まれる
- **100%のコンポーネント可用性** - 85のエージェントすべてがプラグイン全体でアクセス可能
- **効率的な分布** - プラグインあたり平均3.4コンポーネント

### 発見可能性

- **明確なプラグイン名**が目的を即座に伝える
- 23の明確に定義されたカテゴリによる**論理的な分類**
- 相互参照付きの**検索可能なドキュメント**
- **簡単に見つけられる**適切なツール

## 設計パターン

### パターン1：単一目的プラグイン

各プラグインは1つのドメインに焦点を当てています：

```
python-development/
├── agents/           # Python language experts
├── commands/         # Python project scaffolding
└── skills/           # Python-specific knowledge
```

**メリット：**
- 明確な責任
- メンテナンスが容易
- 最小限のトークン使用
- 他のプラグインと組み合わせ可能

### パターン2：ワークフローオーケストレーション

オーケストレータープラグインは複数のエージェントを調整します：

```
full-stack-orchestration/
└── commands/
    └── full-stack-feature.md    # Coordinates 7+ agents
```

**オーケストレーション：**
1. backend-architect（API設計）
2. database-architect（スキーマ設計）
3. frontend-developer（UI構築）
4. test-automator（テスト作成）
5. security-auditor（セキュリティレビュー）
6. deployment-engineer（CI/CD）
7. observability-engineer（モニタリング）

### パターン3：エージェント + スキル統合

エージェントは推論を提供し、スキルは知識を提供します：

```
User: "Build FastAPI project with async patterns"
  ↓
fastapi-pro agent (orchestrates)
  ↓
fastapi-templates skill (provides patterns)
  ↓
python-scaffold command (generates project)
```

### パターン4：マルチプラグイン構成

複雑なワークフローは複数のプラグインを使用します：

```
Feature Development Workflow:
1. backend-development:feature-development
2. security-scanning:security-hardening
3. unit-testing:test-generate
4. code-review-ai:ai-review
5. cicd-automation:workflow-automate
6. observability-monitoring:monitor-setup
```

## バージョニングと更新

### マーケットプレイスの更新

- `.claude-plugin/marketplace.json`のマーケットプレイスカタログ
- プラグインのセマンティックバージョニング
- 後方互換性の維持
- 破壊的変更のための明確な移行ガイド

### プラグインの更新

- 個々のプラグインの更新は他のプラグインに影響しない
- スキルは独立して更新可能
- エージェントはワークフローを壊すことなく追加/削除可能
- コマンドは安定したインターフェースを維持

## コントリビューションガイドライン

### プラグインの追加

1. プラグインディレクトリを作成：`plugins/{plugin-name}/`
2. エージェントまたはコマンドを追加
3. オプションでスキルを追加
4. marketplace.jsonを更新
5. 適切なカテゴリでドキュメント化

### エージェントの追加

1. `plugins/{plugin-name}/agents/{agent-name}.md`を作成
2. フロントマターを追加（名前、説明、モデル）
3. 包括的なシステムプロンプトを記述
4. プラグイン定義を更新

### スキルの追加

1. `plugins/{plugin-name}/skills/{skill-name}/SKILL.md`を作成
2. YAMLフロントマターを追加（名前、「Use when」付きの説明）
3. プログレッシブディスクロージャを使用してスキルコンテンツを記述
4. marketplace.jsonのプラグインのスキル配列に追加

### 品質基準

- **明確な命名** - ハイフンケース、説明的
- **焦点を絞ったスコープ** - 単一責任
- **完全なドキュメント** - 何を、いつ、どのように
- **テストされた機能** - コミット前に検証
- **仕様準拠** - Anthropicのガイドラインに従う

## 関連項目

- [Agent Skills](./agent-skills.md) - モジュール式知識パッケージ
- [Agent Reference](./agents.md) - 完全なエージェントカタログ
- [Plugin Reference](./plugins.md) - 全63プラグイン
- [Usage Guide](./usage.md) - コマンドとワークフロー
