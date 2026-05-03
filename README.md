# rekordbox-mcp

An MCP (Model Context Protocol) server that lets you query and manage your rekordbox library through Claude.

> **Note:** This project is currently read-only. Write features (playlist creation, track editing, etc.) are planned for future updates.

---

rekordboxのライブラリをClaudeから検索・管理できるMCPサーバーです。

> **注意:** 現在は読み取り専用です。プレイリスト作成やトラック編集などの書き込み機能は今後追加予定です。

---

## Features / 機能

| Tool | Description |
|------|-------------|
| `search_tracks` | Filter tracks by BPM range, key, genre, artist, or title |
| `get_playlists` | List all playlists with track counts |
| `get_playlist_tracks` | Get all tracks in a specific playlist |
| `get_library_stats` | Library statistics (total tracks, top genres/artists) |
| `find_duplicates` | Detect tracks with duplicate title + artist |

## Requirements / 必要環境

- macOS with rekordbox 6 or 7 installed
- Python 3.10+

## Installation / インストール

```bash
git clone https://github.com/y08416/rekordbox-mcp.git
cd rekordbox-mcp
python3 -m venv .venv
.venv/bin/pip install pyrekordbox mcp
```

## Claude Desktop Setup / Claude Desktopへの登録

Add the following to `~/Library/Application Support/Claude/claude_desktop_config.json`:

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

Replace `/path/to/rekordbox-mcp` with the actual path where you cloned the repository.

Then restart Claude Desktop. You should see `rekordbox` listed under Connectors.

## Usage Examples / 使い方の例

Once connected, you can ask Claude things like:

- "Show me all tracks with BPM between 128 and 132"
- "What are the top genres in my library?"
- "List all tracks in my Tech House playlist"
- "Find duplicate tracks in my library"

---

- "BPM 128〜132のトラックを一覧で出して"
- "ライブラリで一番多いジャンルは？"
- "Tech Houseプレイリストの曲を全部見せて"
- "重複してる曲を検出して"

## Warning / 注意事項

Always back up your rekordbox library before using any write features (coming soon). Use at your own risk.

rekordboxライブラリのバックアップを必ず取ってから書き込み機能（近日公開予定）を使ってください。自己責任でご利用ください。

## Roadmap / 今後の予定

- [ ] Playlist creation
- [ ] Track comment editing
- [ ] Bulk tag updates
- [ ] Harmonic mix suggestions

## Contact / 連絡先

Twitter: [@yosuke_8416](https://twitter.com/yosuke_8416)
