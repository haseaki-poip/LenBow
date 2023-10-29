# 友達との本の貸し借り管理サービス「LenBow」

[![IMAGE ALT TEXT HERE](https://jphacks.com/wp-content/uploads/2023/07/JPHACKS2023_ogp.png)](https://www.youtube.com/watch?v=yYRQEdfGjEg)

[デモ動画(こちらをクリックすることで動画ページへ飛びます](https://drive.google.com/file/d/1VPHbAtzYipJsI83txQl0LWmnsymWu2gj/view?usp=drive_link)

[プロダクトURL(このURLからLINEでbotを友達追加してサービスを利用できます](https://liff.line.me/1645278921-kWRPP32q/?accountId=263xoaqc)</br>
※ スマホでサービスを利用するようにしてください。PCやタブレット等で操作すると不具合が生じる場合があります。

### LINE Botの友達追加QRコード
![qrcode](https://github.com/jphacks/NG_2312/blob/feature/readme/images/linebot_qr.png)

## 製品概要
### 背景(製品開発のきっかけ、課題等）
学生エンジニアは将来のため、自分の好奇心のために日々を勉強に費やしています。しかし勉強する上で欠かせないのが技術書ですが、一冊3000円と学生にとっては安いとは言えない金額です。友達が持っていれば貸してもらいたいし、触りだけでも読ませてもれえれば納得して3000円という値段を払い本を買うことができます。 ただやはり貸し借りを行うということはその管理も大変になるということです。借りている側は返す日が遅れれば友達の信頼を失い、貸している側もなるべく早く返して欲しいけど催促して関係を悪くしたくないですよね。 (僕も友達に「リーダブルコード」を貸したまま当分かえってこず、なかなか催促できないまま私のコードはスパゲッティに…)
そういった悩みに対して、友達との本の貸し借りに特化した管理サービスを考えました。管理サービスはすでに世に存在しますが、アプリインストール、アカウント登録、友達追加といった面倒な操作が多くかえって管理を煩わしくしていると思います。自分がやる分にはまだいいですが、友達にもその手間をさせるのは気が引けますよね。 そういった課題にもアプローチをかけて開発に取り組みました！
### 製品説明（具体的な製品の説明）
1. LINEでのbotの友達追加でサービス開始
2. (本を貸す側) 返してもらう日や貸す本の詳細登録をしQRコードを発行
   ![register-flow](https://github.com/jphacks/NG_2312/blob/feature/readme/images/register.png)
4. (借りる側) QRコードを読み取ることで、貸し借りが成立
   ![borrow-flow](https://github.com/jphacks/NG_2312/blob/feature/readme/images/borrow.png)
6. 返す日になると借りている側にbotから催促の通知がいく
   通知のURLからどんな本を借りていたか詳細を確認できます。
   ![notify-flow](https://github.com/jphacks/NG_2312/blob/feature/readme/images/notify.png)
8. 本が帰ってきたら、返却を完了
   ![return-flow](https://github.com/jphacks/NG_2312/blob/feature/readme/images/return.png)
### 特長
#### 1. 特長1  ログイン操作やアプリインストール、初期設定など面倒なこと一切なく利用が開始できる。
LINE BotやLIFF(LINE Frontend Framework)を使用しているためユーザはインストールやログイン処理などを意識することなくサービスを開始できます。またLINEという馴染みの深いアプリ上でサービスが動作するためユーザは抵抗感なく利用できるようになると考えます。
#### 2. 特長2  簡単数ステップで貸し借りが登録できる
1. 本のキーワードを入れるだけで本の詳細(画像やタイトル、説明)が登録できる
2. 複数の本のバーコードがうつった写真を入力すれば複数同時に本の詳細を登録できる
3. QRコードを発行、読み取りするだけで貸し借り成立

#### 3. 特長3  借りている側に返却催促の通知がbotからくる
返却日になるとbotから催促LINEがくるため、借りている側は返却日を忘れて友達の信頼を失うことはなくなります。貸している側も言い出しづらい催促を代行してくれるため貸し借りを気持ちよくできます。 また通知のURLから借りている本の情報を確認できるため、別の人から借りているものを持ってきてしまった..なんてことも起きません。

### 解決出来ること
- 学生エンジニアが金銭的問題によって勉強不足になる
  - 気軽にエンジニアの友達同士で貸し借りできるようになるのでいろんな技術書と出会えます
- 本を貸し借りした際の借りパク、大幅な延滞
  - 催促通知機能が搭載されており返し忘れを防止します
- エンジニア同士の信頼の低下、コミュニティーの衰退
  - 貸し借りをし、互いに支え合うことで信頼関係が生まれコミュニティの活性化に繋がります
### 今後の展望
- 一度貸した本の履歴機能
- 自分の持っている本の登録及び友達の持っている本情報の可視化
- 本返却時のお礼機能(ギフト、メッセージカードなど)
### 注力したこと（こだわり等）
* 技術にLIFFを選定し、連携を工夫することでユーザーログインや、アプリのインストール、初期情報登録といった煩わしいユーザーによる操作をなくしました。
* QRコードの生成やQRコード読み取り機能を実装することで貸し借りの登録をより簡単にしました。
* 本情報の登録で複数の本のバーコードが載った写真を入力することで、画像処理と商品情報APIを組み合わせ複数同時に登録ができる機能を実装しました。

## 開発技術
### 活用した技術
- 画像処理
#### API・データ
- Google Books APIs
- LINE Messaging API

#### フレームワーク・ライブラリ・モジュール
- React
- Next.js
- TailWind
- Prisma
- Supabase
- OpenCV
- LIFF

#### デバイス

### 独自技術
#### ハッカソンで開発した独自機能・技術
- LIFF(LINE Frontend Framework)と連携し、アプリ起動時の自動ログイン処理 [実装内容](https://github.com/jphacks/NG_2312/commit/2af72e7a5005316d8e30b40fd45dc9e562f40220)



#### 製品に取り入れた研究内容（データ・ソフトウェアなど）（※アカデミック部門の場合のみ提出必須）
* 
* 
