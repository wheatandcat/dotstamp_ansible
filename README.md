# dotstamp_ansible

<img src="https://raw.githubusercontent.com/wheatandcat/dotstamp_client/master/dist/images/common/about.png" data-canonical-src="https://raw.githubusercontent.com/wheatandcat/dotstamp_client/master/dist/images/common/about.png" width="200" />

## 概要
.stampの環境構築リポジトリ
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
* リポジトリをclone + vagrant起動
```
git clone git@github.com:wheatandcat/dotstamp_ansible.git
cd dotstamp_ansible
vagrant up
```
* vagrantでsshできるようにする（開発者用）
```
vagrant ssh-config > ~/.ssh/config
ssh-agent
ssh-add -K ~/.ssh/id_rsa
ssh-agent -l
```
* Ansible接続確認
```
ansible all -i hosts -m ping
```
* Ansibleでローカル環境構築
```
ansible-playbook -i hosts site.yml
```
