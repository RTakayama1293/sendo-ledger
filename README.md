# sendo-ledger

新日本海商事（SNJ）受発注管理台帳（SENDO v0.5）操作用リポジトリ。  
Claude Code on the Web で受発注台帳の更新・採番・抽出を行う。

## セットアップ

```bash
pip install -r requirements.txt
```

## ディレクトリ構成

```
sendo-ledger/
├── CLAUDE.md              # Claude Code 指示書（基礎情報）
├── README.md
├── requirements.txt
├── .gitignore
│
├── .claude/
│   └── settings.json      # フック設定
│
├── data/
│   ├── raw/               # 入力ファイル投入場所（台帳xlsx、見積PDF、発注書等）
│   ├── processed/         # 中間処理ファイル
│   └── archive/           # 旧バージョン台帳のアーカイブ
│
├── outputs/               # アウトプット（更新台帳xlsx、CSV等）
├── scripts/               # Pythonスクリプト
└── docs/                  # 業務ルール・補足資料
```

## 使い方

1. `data/raw/` に最新の台帳xlsxや仕入先見積PDFを置く
2. Claude Code on the Web でリポジトリを開く
3. キーワードで操作を指示（詳細はCLAUDE.md参照）

### 指示例

```
受発注管理台帳_20260317_1000.xlsx の商品マスタを更新して。
data/raw/にある見積書PDFから商品情報を読み取って追記。
```

```
案件番号採番して。担当は杉田、支店は大阪。
```

```
案件番号 2603-1001-S01 の追跡表を「出荷済」に更新して。出荷日は2026/03/18。
```

```
商品マスタからJAN抽出して。エゾシカ関連商品だけ。CSVで出して。
```
