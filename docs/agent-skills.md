# Agent Skills

Agent Skillsは、Anthropicの[Agent Skills Specification](https://github.com/anthropics/skills/blob/main/agent_skills_spec.md)に従い、特化したドメイン知識でClaudeの機能を拡張するモジュール式パッケージです。このプラグインエコシステムには、15のプラグインにわたって**57の専門スキル**が含まれており、段階的な開示と効率的なトークン使用を可能にします。

## 概要

Skillsは、すべてを事前にコンテキストにロードすることなく、特定のドメインにおける深い専門知識をClaudeに提供します。各スキルには以下が含まれます：

- **YAML Frontmatter**: 名前とアクティベーション条件
- **Progressive Disclosure**: メタデータ → 指示 → リソース
- **Activation Triggers**: 自動呼び出しのための明確な「Use when」句

## プラグイン別スキル

### Kubernetes Operations (4 skills)

| Skill | Description |
|-------|-------------|
| **k8s-manifest-generator** | ベストプラクティスに従い、Deployments、Services、ConfigMaps、Secretsのための本番環境対応Kubernetesマニフェストを作成 |
| **helm-chart-scaffolding** | Kubernetesアプリケーションのテンプレート化とパッケージ化のためのHelmチャートを設計、整理、管理 |
| **gitops-workflow** | ArgoCDとFluxを使用した自動化された宣言的デプロイメントのためのGitOpsワークフローを実装 |
| **k8s-security-policies** | NetworkPolicy、PodSecurityPolicy、RBACを含むKubernetesセキュリティポリシーを実装 |

### LLM Application Development (4 skills)

| Skill | Description |
|-------|-------------|
| **langchain-architecture** | エージェント、メモリ、ツール統合を備えたLangChainフレームワークを使用してLLMアプリケーションを設計 |
| **prompt-engineering-patterns** | LLMのパフォーマンスと信頼性のための高度なプロンプトエンジニアリング技術を習得 |
| **rag-implementation** | ベクトルデータベースとセマンティック検索を使用したRetrieval-Augmented Generationシステムを構築 |
| **llm-evaluation** | 自動化されたメトリクスとベンチマークによる包括的な評価戦略を実装 |

### Backend Development (5 skills)

| Skill | Description |
|-------|-------------|
| **api-design-principles** | 直感的でスケーラブル、保守可能なAPIのためのRESTおよびGraphQL API設計を習得 |
| **architecture-patterns** | Clean Architecture、Hexagonal Architecture、Domain-Driven Designを実装 |
| **microservices-patterns** | サービス境界、イベント駆動型通信、レジリエンスを持つマイクロサービスを設計 |
| **workflow-orchestration-patterns** | 分散システム、Sagaパターン、状態管理のためのTemporalを使用した永続的なワークフローを設計 |
| **temporal-python-testing** | pytest、time-skipping、モッキング戦略を使用してTemporalワークフローを包括的にテスト |

### Developer Essentials (8 skills)

| Skill | Description |
|-------|-------------|
| **git-advanced-workflows** | リベース、チェリーピック、bisect、worktrees、reflogを含む高度なGitワークフローを習得 |
| **sql-optimization-patterns** | データベースパフォーマンスのためのSQLクエリ、インデックス戦略、EXPLAIN分析を最適化 |
| **error-handling-patterns** | 例外、Result型、graceful degradationによる堅牢なエラーハンドリングを実装 |
| **code-review-excellence** | 建設的なフィードバックと体系的な分析による効果的なコードレビューを提供 |
| **e2e-testing-patterns** | 重要なユーザーワークフローのためにPlaywrightとCypressを使用した信頼性の高いE2Eテストスイートを構築 |
| **auth-implementation-patterns** | JWT、OAuth2、セッション、RBACを使用した認証・認可を実装 |
| **debugging-strategies** | 体系的なデバッグ技術、プロファイリングツール、根本原因分析を習得 |
| **monorepo-management** | スケーラブルなマルチパッケージプロジェクトのためにTurborepo、Nx、pnpm workspacesを使用してモノレポを管理 |

### Blockchain & Web3 (4 skills)

| Skill | Description |
|-------|-------------|
| **defi-protocol-templates** | ステーキング、AMMs、ガバナンス、レンディングのためのテンプレートを使用してDeFiプロトコルを実装 |
| **nft-standards** | メタデータとマーケットプレイス統合を備えたNFT標準（ERC-721、ERC-1155）を実装 |
| **solidity-security** | 脆弱性を防ぎ、安全なパターンを実装するためのスマートコントラクトセキュリティを習得 |
| **web3-testing** | ユニットテストとメインネットフォーキングを使用してHardhatとFoundryでスマートコントラクトをテスト |

### CI/CD Automation (4 skills)

| Skill | Description |
|-------|-------------|
| **deployment-pipeline-design** | 承認ゲートとセキュリティチェックを備えたマルチステージCI/CDパイプラインを設計 |
| **github-actions-templates** | テスト、ビルド、デプロイのための本番環境対応GitHub Actionsワークフローを作成 |
| **gitlab-ci-patterns** | マルチステージワークフローと分散ランナーを使用してGitLab CI/CDパイプラインを構築 |
| **secrets-management** | Vault、AWS Secrets Manager、またはネイティブソリューションを使用した安全なシークレット管理を実装 |

### Cloud Infrastructure (4 skills)

| Skill | Description |
|-------|-------------|
| **terraform-module-library** | AWS、Azure、GCPインフラストラクチャのための再利用可能なTerraformモジュールを構築 |
| **multi-cloud-architecture** | ベンダーロックインを避けるマルチクラウドアーキテクチャを設計 |
| **hybrid-cloud-networking** | オンプレミスとクラウドプラットフォーム間の安全な接続を構成 |
| **cost-optimization** | 適正サイジング、タグ付け、リザーブドインスタンスによるクラウドコストを最適化 |

### Framework Migration (4 skills)

| Skill | Description |
|-------|-------------|
| **react-modernization** | Reactアプリをアップグレードし、hooksに移行し、並行機能を採用 |
| **angular-migration** | ハイブリッドモードと段階的な書き換えを使用してAngularJSからAngularに移行 |
| **database-migration** | ゼロダウンタイム戦略と変換を使用してデータベース移行を実行 |
| **dependency-upgrade** | 互換性分析とテストを使用してメジャー依存関係アップグレードを管理 |

### Observability & Monitoring (4 skills)

| Skill | Description |
|-------|-------------|
| **prometheus-configuration** | 包括的なメトリクス収集と監視のためのPrometheusをセットアップ |
| **grafana-dashboards** | リアルタイムシステム可視化のための本番環境Grafanaダッシュボードを作成 |
| **distributed-tracing** | リクエストを追跡するためにJaegerとTempoを使用した分散トレーシングを実装 |
| **slo-implementation** | エラーバジェットとアラートを備えたSLIとSLOを定義 |

### Payment Processing (4 skills)

| Skill | Description |
|-------|-------------|
| **stripe-integration** | チェックアウト、サブスクリプション、webhooksのためのStripe決済処理を実装 |
| **paypal-integration** | エクスプレスチェックアウトとサブスクリプションを備えたPayPal決済処理を統合 |
| **pci-compliance** | 安全な決済カードデータ処理のためのPCI DSSコンプライアンスを実装 |
| **billing-automation** | 定期支払いと請求書発行のための自動請求システムを構築 |

### Python Development (5 skills)

| Skill | Description |
|-------|-------------|
| **async-python-patterns** | Python asyncio、並行プログラミング、async/awaitパターンを習得 |
| **python-testing-patterns** | pytest、fixtures、mockingによる包括的なテストを実装 |
| **python-packaging** | 適切な構造とPyPI公開を備えた配布可能なPythonパッケージを作成 |
| **python-performance-optimization** | cProfileとパフォーマンスのベストプラクティスを使用してPythonコードをプロファイル・最適化 |
| **uv-package-manager** | 高速な依存関係管理と仮想環境のためのuvパッケージマネージャーを習得 |

### JavaScript/TypeScript (4 skills)

| Skill | Description |
|-------|-------------|
| **typescript-advanced-types** | ジェネリクスと条件型を含むTypeScriptの高度な型システムを習得 |
| **nodejs-backend-patterns** | Express/Fastifyとベストプラクティスを使用して本番環境対応Node.jsサービスを構築 |
| **javascript-testing-patterns** | Jest、Vitest、Testing Libraryによる包括的なテストを実装 |
| **modern-javascript-patterns** | async/await、分割代入、関数型プログラミングを含むES6+機能を習得 |

### API Scaffolding (1 skill)

| Skill | Description |
|-------|-------------|
| **fastapi-templates** | 非同期パターンとエラーハンドリングを備えた本番環境対応FastAPIプロジェクトを作成 |

### Machine Learning Operations (1 skill)

| Skill | Description |
|-------|-------------|
| **ml-pipeline-workflow** | データ準備からデプロイメントまでのエンドツーエンドMLOpsパイプラインを構築 |

### Security Scanning (1 skill)

| Skill | Description |
|-------|-------------|
| **sast-configuration** | 脆弱性検出のためのStatic Application Security Testingツールを構成 |

## スキルの仕組み

### アクティベーション

スキルは、Claudeがリクエスト内で一致するパターンを検出すると自動的にアクティベートされます：

```
User: "Set up Kubernetes deployment with Helm chart"
→ Activates: helm-chart-scaffolding, k8s-manifest-generator

User: "Build a RAG system for document Q&A"
→ Activates: rag-implementation, prompt-engineering-patterns

User: "Optimize Python async performance"
→ Activates: async-python-patterns, python-performance-optimization
```

### Progressive Disclosure

スキルは、トークン効率のために3層アーキテクチャを使用します：

1. **Metadata**（Frontmatter）: 名前とアクティベーション条件（常にロード）
2. **Instructions**: コアガイダンスとパターン（アクティベート時にロード）
3. **Resources**: 例とテンプレート（オンデマンドでロード）

### エージェントとの統合

スキルは、エージェントと連携して深いドメイン専門知識を提供します：

- **Agents**: 高レベルな推論とオーケストレーション
- **Skills**: 専門知識と実装パターン

ワークフローの例：
```
backend-architect agent → Plans API architecture
  ↓
api-design-principles skill → Provides REST/GraphQL best practices
  ↓
fastapi-templates skill → Supplies production-ready templates
```

## 仕様準拠

すべての55スキルは[Agent Skills Specification](https://github.com/anthropics/skills/blob/main/agent_skills_spec.md)に従っています：

- ✓ 必須の`name`フィールド（ハイフンケース）
- ✓ 「Use when」句を含む必須の`description`フィールド
- ✓ 1024文字未満の説明
- ✓ 完全で切り捨てられていない説明
- ✓ 適切なYAML frontmatterフォーマット

## 新しいスキルの作成

プラグインにスキルを追加するには：

1. `plugins/{plugin-name}/skills/{skill-name}/SKILL.md`を作成
2. YAML frontmatterを追加：
   ```yaml
   ---
   name: skill-name
   description: What the skill does. Use when [activation trigger].
   ---
   ```
3. Progressive Disclosureを使用して包括的なスキルコンテンツを記述
4. `marketplace.json`にスキルパスを追加：
   ```json
   {
     "name": "plugin-name",
     "skills": ["./skills/skill-name"]
   }
   ```

### スキル構造

```
plugins/{plugin-name}/
└── skills/
    └── {skill-name}/
        └── SKILL.md        # Frontmatter + content
```

## メリット

- **トークン効率**: 必要な時にのみ関連する知識をロード
- **専門的な知見**: 肥大化なしに深いドメイン知識を提供
- **明確なアクティベーション**: 明示的なトリガーが意図しない呼び出しを防止
- **組み合わせ可能性**: ワークフロー全体でスキルをミックス＆マッチ
- **保守性**: 分離された更新が他のスキルに影響しない

## リソース

- [Anthropic Skills Repository](https://github.com/anthropics/skills)
- [Agent Skills Documentation](https://docs.claude.com/en/docs/claude-code/skills)
