# KBCopilot - ナレッジ回答アプリ
Dataverse 内のデータの検索を行い、Copilot Studio の生成型の回答で要約返答することができるソリューションです。


# ソリューション

KBCopilot - ナレッジ回答Copilot は、前提として以下のPower Apps で作成されたナレッジ管理アプリをインストールする必要があります。

また、ナレッジ回答アプリはAttachments Grids というPCF (Power Apps Component Framework)を利用しています。そのため、段階的にソリューションをインストールしてください。

手順は以下のとおりです。

1. [Attachments Grid](https://pcf.gallery/attachments-grid/)
2. [KB管理アプリ - Power Apps モデル駆動型アプリのリリース](https://github.com/geekfujiwara/KBCopilot/releases/tag/KBApp)
3. [KBCopilot - Copilot Studioで作成したナレッジ回答Copilotのリリース](https://github.com/geekfujiwara/KBCopilot/releases/tag/KBCopilot)


## インストールの補足

Attachemnts Grid はGitHub上に[ソリューション](https://github.com/BenLBartle/PCF-AttachmentsGrid/blob/master/Solution/bin/Debug/Solution.zip)が提供されています。

こちらからZip ファイルをダウンロードしてください。

![image](https://github.com/geekfujiwara/KBCopilot/assets/96101315/b2358ae9-1bdb-4e47-b565-47a698d96f4c)

> [!NOTE]
> このようにPCF が提供されているPCF Gallery から様々の機能をインストールすることが出来ます。
>
> 有志での提供のため、その殆どがサポート対象外のためその点はご注意ください。


# 機能

ナレッジベースに書かれていることについて質問をしてみます。
※事前にモデル駆動型アプリからなどで、Dataverse にナレッジを登録しておく必要があります。

![image](https://github.com/geekfujiwara/KBCopilot/assets/96101315/78d813b6-5106-4eb9-b204-cfe1f868ee3f)

ナレッジがヒットすると、Copilot に返答が行われます。

![image](https://github.com/geekfujiwara/KBCopilot/assets/96101315/2e8c180e-ee0e-4fba-82e5-df6b100b47ab)

引用のリンクをクリックすると、ソースを確認することが出来ます。
モデル駆動型アプリに遷移する事ができるようになってきます。

![image](https://github.com/geekfujiwara/KBCopilot/assets/96101315/633cfb03-680d-4b8b-902b-2104dba72bc8)

クラウドフローで検索を行っています。

ユーザーのからのメッセージからキーフレーズ抽出をAI Builder にて行います。

![image](https://github.com/geekfujiwara/KBCopilot/assets/96101315/83df26e0-85c7-4901-8aca-76772f2d8bdf)

検索結果はナレッジのテーブルからDataverse 検索機能を利用してTop 3 を抽出しています。

![image](https://github.com/geekfujiwara/KBCopilot/assets/96101315/3abd1b5e-1d08-4e00-9a2e-e74361b8ea93)

抽出した結果をCopilot Studio の生成型の生成のカスタムデータで扱える形式にして返答します。

![image](https://github.com/geekfujiwara/KBCopilot/assets/96101315/342cb7a9-09f7-4bda-ae4f-109842764e6f)

[生成型の回答にカスタム データ ソースを使用する - Microsoft Learn](https://learn.microsoft.com/ja-jp/microsoft-copilot-studio/nlu-generative-answers-custom-data)

