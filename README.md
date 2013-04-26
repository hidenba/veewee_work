veewee_work
===========

veewee working project

OSのISOファイルは$PROJECT_ROOT/isoに置くといいね

## インストーラで入れたvagrantの諸々を退避 ##
$ mv ~/vagrant.d ~/vagtant.d.bak

## boxのテンプレート一覧を表示 ##
$ bundle exec vagrant basebox templates

## テンプレートを作成(ubuntu-12.10) ##
$ bundle exec vagrant basebox define 'ubuntu12.10' 'ubuntu-12.10-server-amd64'

## isoの場所を変更 ##
$cd definitions/ubuntu12.10
$vi definition.rv

:iso_src => "iso/ubuntu-12.10-server-amd64.iso",
の部分をダウンロードしてあるOSのisoファイルを指定する

## ビルド ##
$ bundle exec vagrant basebox build ubuntu12.10

## boxのエクスポート ##
$ bundle exec vagrant basebox export ubuntu12.10
