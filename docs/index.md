# Welcome to MkDocs

For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

## Project layout

    .github/workflows/publish.yml

    docs/
        commands/   # 様々な媒体のコマンドのまとめ
            docker.md   # MkDocsのコマンド
            git.md  # gitのコマンド
            window.md   # コマンドプロンプトのコマンド

        competitive_programming/    # 競プロ
            template.md # 競プロのテンプレート

        daily/  DailyLog
            # 月ごとにファイルが分けられている
            # それぞれに画像ファイル、index.md、reports.mdが入っている
            index.md    # 過去の記録

        schedule/   # スケジュール
            schedule.md # スケジュール

        spike/  # Spike
            template.md # Spikeのテンプレート

        index.md  # The documentation homepage.
        
        link.md # リンク集
    
    mkdocs.yml    # The configuration file.