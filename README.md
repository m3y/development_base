development_base
================

開発環境構築
------------
```
$ vagrant up
### ssh の設定
$ vagrant ssh-config --host <HOSTNAME> >> ~/.ssh/config
```
<HOSTNAME> は任意

注意事項
--------
VirtualBox 5.02 では起動できないバグがようなので、5.0以下のパッケージを利用する必要あり。
