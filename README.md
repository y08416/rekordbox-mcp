# rekordbox-mcp

An MCP (Model Context Protocol) server that connects your rekordbox library to Claude, letting you search and manage your tracks using natural language.

> **Status:** Read-only for now. Write features (playlist creation, track editing, etc.) are coming in future updates.

---

## Features

| Tool | Description |
|------|-------------|
| `search_tracks` | Filter tracks by BPM range, key, genre, artist, or title |
| `get_playlists` | List all playlists with track counts |
| `get_playlist_tracks` | Get all tracks in a specific playlist |
| `get_library_stats` | Library statistics (total tracks, top genres/artists) |
| `find_duplicates` | Detect tracks with duplicate title + artist |

## Requirements

- macOS
- rekordbox 6 or 7 installed
- Python 3.10+
- [Claude Desktop](https://claude.ai/download)

## Installation

**1. Clone the repository**

```bash
git clone https://github.com/y08416/rekordbox-mcp.git
cd rekordbox-mcp
```

**2. Create a virtual environment and install dependencies**

```bash
python3 -m venv .venv
.venv/bin/pip install pyrekordbox mcp
```

## Claude Desktop Setup

**1. Open the config file**

```
~/Library/Application Support/Claude/claude_desktop_config.json
```

**2. Add the `mcpServers` section**

```json
{
  "mcpServers": {
    "rekordbox": {
      "command": "/path/to/rekordbox-mcp/.venv/bin/python3",
      "args": ["/path/to/rekordbox-mcp/server.py"]
    }
  }
}
```

Replace `/path/to/rekordbox-mcp` with the actual path. For example, if you cloned it to your Documents folder:

```
/Users/yourname/Documents/rekordbox-mcp
```

**3. Restart Claude Desktop**

After restarting, click the `+` button in the chat input area and go to **Connectors**. You should see `rekordbox` listed and toggled on.

## Usage Examples

Once connected, you can ask Claude things like:

- "Show me all tracks with BPM between 128 and 132"
- "What are the top genres in my library?"
- "List all tracks in my Tech House playlist"
- "Find duplicate tracks in my library"
- "How many tracks do I have in total?"

## Warning

This tool accesses your rekordbox database directly. It is currently **read-only**, so no data will be modified. That said, always keep a backup of your library just in case.

## Roadmap

- [ ] Playlist creation
- [ ] Track comment / tag editing
- [ ] Bulk metadata updates
- [ ] Harmonic mix suggestions

## Contact

Twitter: [@yosuke_8416](https://twitter.com/yosuke_8416)

---

# rekordbox-mcp（日本語）

rekordboxのライブラリをClaudeと自然言語で操作できるMCPサーバーです。「BPM 130〜135のTech Houseを出して」のような指示をClaudeに送るだけで、ライブラリを検索・分析できます。

> **現在のステータス:** 読み取り専用です。プレイリスト作成やタグ編集などの書き込み機能は今後追加予定です。

---

## 機能一覧

| ツール | 内容 |
|--------|------|
| `search_tracks` | BPM・キー・ジャンル・アーティスト・タイトルで曲を検索 |
| `get_playlists` | プレイリスト一覧をトラック数付きで取得 |
| `get_playlist_tracks` | 指定プレイリストの曲一覧を取得 |
| `get_library_stats` | ライブラリ全体の統計（総曲数・上位ジャンル/アーティスト） |
| `find_duplicates` | タイトル＋アーティストが重複している曲を検出 |

## 必要なもの

- macOS
- rekordbox 6 または 7 がインストール済み
- Python 3.10 以上
- [Claude Desktop](https://claude.ai/download)

## インストール手順

**1. リポジトリをクローン**

```bash
git clone https://github.com/y08416/rekordbox-mcp.git
cd rekordbox-mcp
```

**2. 仮想環境を作成して依存パッケージをインストール**

```bash
python3 -m venv .venv
.venv/bin/pip install pyrekordbox mcp
```

## Claude Desktopへの登録

**1. 設定ファイルを開く**

以下のファイルをテキストエディタで開いてください：

```
~/Library/Application Support/Claude/claude_desktop_config.json
```

**2. `mcpServers` を追加**

```json
{
  "mcpServers": {
    "rekordbox": {
      "command": "/path/to/rekordbox-mcp/.venv/bin/python3",
      "args": ["/path/to/rekordbox-mcp/server.py"]
    }
  }
}
```

`/path/to/rekordbox-mcp` の部分は実際のパスに書き換えてください。例えばDocumentsフォルダにクローンした場合：

```
/Users/あなたのユーザー名/Documents/rekordbox-mcp
```

**3. Claude Desktopを再起動**

再起動後、チャット入力欄の「+」ボタン → **コネクタ** を開くと `rekordbox` が表示されます。トグルがオンになっていれば接続完了です。

## 使い方の例

接続できたら、Claudeにこんな感じで話しかけてみてください：

- 「BPM 128〜132のトラックを一覧で出して」
- 「ライブラリで一番多いジャンルは？」
- 「Tech Houseプレイリストの曲を全部見せて」
- 「重複してる曲を検出して」
- 「トラックは全部で何曲ある？」

## 注意事項

このツールはrekordboxのデータベースに直接アクセスします。現在は**読み取り専用**なのでデータが変更されることはありませんが、念のためライブラリのバックアップを取っておくことをおすすめします。

## 今後の予定

- [ ] プレイリスト作成
- [ ] トラックのコメント・タグ編集
- [ ] メタデータの一括更新
- [ ] ハーモニックミックス提案

## 連絡先

Twitter: [@yosuke_8416](https://twitter.com/yosuke_8416)
