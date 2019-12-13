# learning-docker: Dockerの練習

## ミニレポート

### Q1-1: 同じ `docker container run` コマンドを2回実行すると、1回目と2回目で違いはありますか？どう違いますか？

【回答欄】
1度目は"Unable to find image Ubuntu:latest locally"と言われてイメージのダウンロードが始まった
2度目は特に何も起きずにHello Worldがechoされた

### Q1-2: なぜ違いますか？

【回答欄】
1度目はDoockerホスト上に存在しないイメージをダウンロードする必要があるため、その分違いがでる


### Q1-3: `docker container ls` と `docker container ls -a` はどう違いますか？

【回答欄】
`docker container ls`は'CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS              PORTS               NAMES'と表示されたが
`docker container ls -a`はそれぞれの内容が表示されている

### Q1-4: `docker image ls` と `docker container ls -a` はどう違いますか？（間違ってもいいので、自分の考えを述べてください）

【回答欄】
lsは中身ではなく概要をリストするが、-aのオプションをつけると実行された中身も表示する？

### Q1-5: `ubuntu` イメージでの `cat /etc/issue` の結果をペーストしてください

【回答欄】
root@4e68b107d70d:/# cat /etc/issue
Ubuntu 18.04.3 LTS \n \l

### Q1-6: `docker image ls` と `docker container ls -a` はどう変化しましたか？

【回答欄】
`docker image ls`は変化しなかった
`docker container ls -a`は/bin/bashコマンドを実行した跡が残っていた

### Q2-1: `-d` (デタッチド・モード) でコンテナを起動すると、どのような状態になりましたか？

【回答欄】
コマンドラインには特に何も起きなかった

### Q2-2: http://localhost/ をブラウザで開くと、何が表示されましたか？

【回答欄】
" Welcome to nginx!
  If you see this page, the nginx web server is successfully installed and working. Further configuration is required.

  For online documentation and support please refer to nginx.org.
  Commercial support is available at nginx.com.

  Thank you for using nginx. "

### Q2-3: コンテナの起動時と終了時で、docker container ls -a はどのように変化しましたか？

【回答欄】
`STATUS`と`PORTS`に表示されるものが変わっている
自分の環境では
`STATUS`が`up 6 minutes(6分間起動中)`から`Exited (0) 16 seconds ago(16秒前に離脱)`
`PORTS`では`0.0.0.0:80->80/tcp`が消えている

### Q3-1: `docker build -t sample-image .` 実行時に表示されている `building...` は、Dockerfileのどの行から実行されましたか？

【回答欄】

`# "docker build"時に実行される処理`
`RUN echo "building..."`


### Q3-2: `docker run sample-image` を実行すると、どうなりましたか？

【回答欄】

`Hello, from docker container!`が表示された
