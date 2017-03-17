# dotstamp_ansible

<img src="https://raw.githubusercontent.com/wheatandcat/dotstamp_client/master/dist/images/common/about.png" data-canonical-src="https://raw.githubusercontent.com/wheatandcat/dotstamp_client/master/dist/images/common/about.png" width="200" />

## 概要
.stampの環境構築リポジトリ
webサービス：[.stamp](http://dotstamp.com/)
## projectリポジトリ一覧
* サーバーサイド:[dotstamp_server](https://github.com/wheatandcat/dotstamp_server)
* クライアントサイド：[dotstamp_client](https://github.com/wheatandcat/dotstamp_client)
* 環境構築：[dotstamp_ansible](https://github.com/wheatandcat/dotstamp_ansible)
* デプロイスクリプト：[dotstamp_deploy_script](https://github.com/wheatandcat/dotstamp_deploy_script)
* デプロイ環境構築：[dotstamp_deploy_ansible](https://github.com/wheatandcat/dotstamp_deploy_ansible)
## 事前準備
実行には以下が必要です
* Ansible
* VirtualBox
* Vagrant
## ローカル環境構築手順  
### 注意事項  
* 環境構築にはそれなりの時間と容量が必要です。ご注意下さい 
* 開発者はmacで開発を行っているので、それ以外の環境での動作できるかは不明です
* また既存でVagrantを使用している場合に、環境を上書いてしまう可能性があるので、予めリポジトリの中身をご確認の上で実行して下さい
### 構築手順
リポジトリをclone + vagrant起動
```
git clone git@github.com:wheatandcat/dotstamp_ansible.git
cd dotstamp_ansible
vagrant up
```
vagrantでsshできるようにする（開発者用）
```
vagrant ssh-config > ~/.ssh/config
ssh-agent
ssh-add -K ~/.ssh/id_rsa
ssh-agent -l
```
Ansibleの接続確認
```
ansible all -i hosts -m ping
```
Ansibleでローカル環境構築
```
ansible-galaxy install -p ./roles -r roles.yml
ansible-playbook -i hosts site.yml
```
## 各環境構築系
xxx=環境ファイル

DBサーバ
```
ansible-playbook -i xxx db.yml
```
WEBサーバ
```
ansible-playbook -i xxx web.yml
```
バッチサーバ
```
ansible-playbook -i xxx batch.yml
```
デプロイサーバ(初期構築のみ)
```
ansible-playbook -i xxx init.yml
```
## ライセンス
BSDライセンス

