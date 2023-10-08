# Windows 10 22H2

1. [Git for Windows](https://gitforwindows.org/) 2.42.0.2 をインストール時に `Enable symbolic links` をチェックして `git clone` しても `ln -s` は対象パスのみを含んだテキストファイルになる。

1. `コマンド プロンプト` を `管理者として実行` しないと [mklink](https://ss64.com/nt/mklink.html) が権限エラーになる

    ```
    link> mklink dir1.lnk /D ..\dir1
    この操作を実行するための十分な特権がありません。
    ```

    1. このエラーは英文だと `Access is denied`

1. `設定` / `更新とセキュリティ` / `開発者向け`  (`start ms-settings:developers`) で `開発者モード` を `オン` にすると `コマンド プロンプト` を `管理者として実行` しなくても権限エラーが起きない。

    1. この状態で `git clone` すると Windows でもシンボリックリンクが作成される。

        ```
        ...\link>dir
         ...

        2023/10/08  15:07    <DIR>          .
        2023/10/08  15:07    <DIR>          ..
        2023/10/08  15:07    <SYMLINKD>     dir1 [..\dir1]
        2023/10/08  15:07    <SYMLINK>      ファイル112 [..\dir1\dir11\ファイル112]
                       1 個のファイル                   0 バイト
                       3 個のディレクトリ  ... バイトの空き領域
        ```

        1. エクスプローラでシンボリックリンクをダブルクリックすると、ディレクトリやファイルが開く。

        1. [Sourcetree](https://www.sourcetreeapp.com/) 3.4.15 で `clone` してもシンボリックリンクが作成される。
        1. [Github Desktop](https://desktop.github.com/) 3.3.3 は シンボリックリンクにならない。
