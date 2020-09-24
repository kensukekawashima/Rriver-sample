# 開発戦略

- 文字や色は、見本と完全一致させる必要はない。また、誤差については±10pxとする。
- 各パートごとにPRを実施。確認等を容易にするため。
- 各containerのサイズについては、後日確認する。

追記 09/24/2020

- 改善項目
  - コンクリフトを解消
    - masterブランチ内のファイルにshunkiさんが書いたコード + kensukeが書いたコードが存在している
    - このkensukeが書いたコードを丸々削除。(これで一応コンフリクト解除。実際は、必要な部分を残さなければならない。)
    - <font color="red">バックアップを取る。</font>コピーはデスクトップにでも置いておいて下さい
      - $ cp -f 作業ファイルがあるディレクトリ名 コピー後の名前
        - <details><summary>例</summary><div>
          
          ```rb
            $ cp -f workspace workspace1
          ```

          </div></details>
    - ブランチを切る
      - <details><summary>切り方</summary><div>
        
        ```
        $ git branch ブランチ名     ブランチを切るコマンドであり移動していない
        $ git checkout ブランチ名   このコマンドで移動する
                 または
        $ git checkout -b ブランチ名  ブランチを作りながら移動もするコマンド
        ```

        </div></details>
    - 新しいブランチにpushして一旦作業を中断
  - ホームディレクトリをgit管理から外す
    - 改善理由
      - 容量が大きいためgitに対しての負荷が大きい
      - 個別作業が難しい
      - <details><summary>イメージ図</summary><div>

          ```rb
          /Users/arakishunki/   ←ホームディレクトリ
              |
              |------- Desctop
              |------- Pictures
              |------- Movies
              |------- workspace
                        |
                        |------practice1
                        |------practice2
                        枝分かれしている部分がホームディレクトリ内にあるディレクトリ。
                        自分はこのさらに下の階にディレクトリを作成しgit管理している。
          ```

          </div></details>
    - 改善方法
      - $ rm -rf .git
      -  これでホームディレクトリがgit管理ではなくなります。
      -  その後、クローンで自分が作成したコードを手元に持ってくる。
      -  <details><summary>注意事項</summary><div>

          ```rb
          クローンする際にターミナルで作業ディレクトリまで移動すること
          ```

          </div></details>