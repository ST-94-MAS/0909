;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;
;Enterprise構築自動化ツール使用方法
; Linux 環境 に Enterpriseの基本構成を構築する
;
;  ↓Host OS                  ↓作成する環境
;    Windows                    GuestOS + Enterprise
; +-----------------+        +------------------+
; |   TeraTerm  +-------------+ArcGIS Server    |
; |    WinSCP       |        | ArcGIS Datastore |
; +-----------------+        | ArcGIS Webadaptor|
;                            | ArcGIs Portal    |
;                            +------------------+
;Guest OSの希望スペック
;CPU(コア数) 4 Core
;Memory      16G
;HDD         60G以上
;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;;


■前提条件
・Host OS(Windows)にTera Termがインストールされていること。
・共有サーバに入れること
・GuestOS(Redhat or CentOS)が作成されていること
※2020年7月29日時点では2つのOSのみがサポートされていることから

■フォルダの中身

    00_rhel76_env_setting.ttl:
    10_portal_install.ttl    : Portal for ArcGISのInstallおよびsiteの作成をします。
    20_server_install.ttl    : ArcGIS ServerのInstallおよびsiteの作成をします。
    30_datastore_install.ttl : ArcGIS DatastoreのInstallおよびsiteの作成をします。
    40_webadaptor_install.ttl: ArcGIS WebadaptorのInstallおよびsiteの作成をします。
    41_setting_warfile.ttl   : warファイルをtomcat/webapps以下に配置
    42_auto_start.ttl        : Portal,Server,DatastoreがOS起動時に自動起動する設定。
    43_web_server.ttl        : WebAdaptor経由でServerに接続する設定
    44_web_portal.ttl        : WebAdaptor経由でPortalに接続する設定
    50_get_enterprise.ttl    : 10.7もしくは10.7.1のEnterpriseのアーカイブを取得する。
    51_unzip_enterprise.ttl  : 取得したアーカイブを解凍
    52_patch.ttl             : 提供されているpatchを取得、適応させる。
    999_setting.ttl          : サーバの情報を記載する
    99_login.ttl             : ユーザーログインする
    99_super_login.ttl       : スーパーユーザーでログインする
    master_exe.ttl           : このマクロを実行すると記載されているマクロが実行され、Enterprise環境が作成される

※それぞれ単体でマクロを実行させることもできます。
  例えばEnterpriseのアーカイブだけ取得したい場合に50_get_enterprise.ttlを実行すれば取得できます。

※50_get_enterprise.ttlについて
  "\\ejfilesvr\製品メディア"から取得しているため、Host OS から共有サーバに入れることを事前に確認してください。
  マクロを実行したらいくつかの選択が出てきますので回答してください。


■使用手順
１.	999_setting.ttlに必要な記述をテキストエディタから行ってください。
２.	1つのサーバ内にEnterpriseを構築する場合はmaster_exe.ttlを実行してください。

■ちょっとしたもの
サクラエディタでTeraTermマクロを開いてctl+bでマクロを実行できる
