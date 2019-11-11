# git-hook
Gitの運用をスムーズにするためのGit Hookスクリプトです。

## redmine_ticket_refs

コミットコメントに自動的にRedmine連携用のチケットIDを挿入するHOOKです。
コミット時にブランチ名に含まれるチケット番号を元に「refs #XXX」を最初の行に追加するスクリプトです。
https://github.com/bleis-tift/Git-Hooks 元にしています。

### ブランチ名について(bleis-tift/Git-Hooks より転載)

commit-msgでチケットIDの自動入力を行いたい場合、 トピックブランチは以下の命名規則に従う必要があります。

    id/チケットIDを含む
    idは最上位の階層、もしくはその直下の階層である必要がある
    チケットIDより後には、階層をいくつでも追加できる

例えば、以下のブランチ名の場合、チケットIDの自動入力が行われます。

    id/42
    feature/id/10
    id/1/memo/memo/memo
    release/id/20/memo/memo/memo

このようなブランチ上でコミットした場合、コミットメッセージの一行目の最後に、 「 refs チケットID」が追加されます。 refsの前に空白を入れるので、Redmineの場合何も気にせずに使えます。

チケットIDの自動入力が行われないブランチ名の例としては、

    temp
    id/42d
    feature/hoge/id/10

などがあります。