## 帰宅困難者を対象とした避難所位置情報オープン化の実践−目黒区を例として−
### 1.本研究について

世界で起こる大地震の20％は日本で起こっており、日本と災害は切り離せない存在となっている。甚大な被害を引き起こした2011年の東日本大震災時においては避難場所と避難所が区別されず混乱を招いた為、内閣府は平成25年に災害対策基本法（昭和36年法律第223号）を改正し、指定緊急避難場所と指定避難所を区別しなければならないこととした。又、災害の種類ごとの指定をするように呼びかけており、各避難所の情報は住民に知らされなければならないとされている。
<br>現状では、避難所情報は地方自治体の公式サイト又は地理院地図 指定緊急避難場所情報、東京都防災マップ等から確認でできる。しかしそれぞれのウェブサイトによって地図表現が異なり、避難所マップ自体も行政区全域を表現する反面、各避難所への細かな道路が判読しづらく、ナビゲーション目的には適していない。そこで、本研究では誰もがアクセスが可能であり、更に足りない部分は自ら編集作業も行える草の根のオープンデータ地図プラットフォームOpenStreetMapにこれらの避難所情報を確認できるようにすべきだと考えた。対象地域については、東日本大震災時において帰宅困難者の受け入れについて問題が起きたとされる、東京都渋谷区及び隣接する目黒区とした。対象施設は主に帰宅困難者向けの建物が付随する避難所に限定し、本研究は目黒区を対象地域とした。

#### 災害避難所の定義
* 避難所：災害によって自宅で生活できない場合に生活をする場所
* 一時集合場所:災害が起きた時に次の行動を決めるためにまず集まる場所。
* 避難場所：一時集合場所も危険と判断された時、更に避難する場所。

### 2.研究手法

1)データ収集
具体的なデータ作成手法として、政府標準利用規約に則り公開されている国土地理院の地理院地図 指定緊急避難場所の地図情報より避難所情報をリストアップし、既存のOpenStreetMap登録データと比較を行った結果の現状で避難所タグが入力されていないのを確認した。
2）OpenStreetMapタグの定義
現時点でのOpenStreetMapでの避難所として定義できるのは、避難小屋のタグamenity=shelter,一時集合場所のsocial_facility=shelter,emergency=assembly_pointの三つがあった。避難小屋は悪天候の際に避難ができる小さい小屋であるので、現時点ではemergency＝assembly_pointタグが指定緊急避難場所及び指定緊急避難所のタグとして適当であると判断し、避難所と広域避難所として該当するエリア及び建物にその情報を付加した。情報を付加する際に、OpenStreetMap　Wikiのemergency=assembly_pointの日本語翻訳ページの作成もまた行った。

### 3.成果

結果として、目黒区における避難所情報を新規に57箇所入力することができた。また隣接する渋谷区と目黒区との比較調査を通して、避難所や避難場所の定義は同じだが区ごとで分類方法が異なることも明らかになった。例えば目黒区では避難所という区別しかなかったが、渋谷区は加えて避難場所、一時集合場所、帰宅困難者支援施設等より細かく分類されている。又OpenStreetMapにおける帰宅困難者支援施設に該当するタグのみが存在しなかった為、帰宅困難者支援施設のタグを考察しOpenStreetMap Wikiに新たなタグとして提案することができた。

### 4.課題
#### 提案：帰宅困難者支援施設タグ

帰宅困難者支援施設の重要性は、2011年の東日本大震災において渋谷区民以外の大勢の人が帰宅困難者になった問題で明らかになった。この帰宅困難者が多くいて動けない状況を日本において重大な災害とみなし、避難所のタグであるemergency:assembly_pointにunable_to_move=yesを反映した。
帰宅困難者支援施設のタグemergency=assembly_point:unable_to_move=yesは今の状態では仮のタグとなっているので、公式地物としての認定に関する議論はこれから始まり、最終的には投票で正式に決定するので、そのためのタグ提案のプロセスを経ることが今後の課題である。

#### 提案：emergency=assembly_pointの分類
1)避難所・避難場所の区別について
避難所・避難場所のタグを災害ごとに分けること、避難所以外の災害支援施設の入力が未着手である。避難所と避難場所は日本では区別すべきとされているが、OpenStreetMapでは同じタグとして区別されていたのでどのように表現すべきかが検討すべき課題である。各避難施設の定義をふまえて帰宅困難者の視点から考えると、一時集合場所と避難場所は一時的な利用を目的とされていることから帰宅困難者も利用ができると考えられるが避難所は区民以外は利用できない場合があるので、特に帰宅困難者が多いと想定される地域ではどの施設が利用できるのかを記載しておく必要がある。

2)災害ごとの区別について
現在のこのタグで分類できるのは、

* emergency=assembly_point:earthquake 
* emergency=assembly_point:fire
* emergency=assembly_point:flood
* emergency=assembly_point:landslide
* emergency=assembly_point:tornade
* emergency=assembly_point:tsunamiの６種類であった。内閣府は指定緊急避難場所・指定緊急避難所の指定を促しているのと同時に日本工業規格（JIS)の災害種別の図記号（JIS　Z8210)を使った災害種別避難誘導標識システム（JIS　Z9098、H28.3.22）により災害ごとの避難場所の表示を促しており、それによる災害分類の中で上記の６つに該当指定ない高潮、内水氾濫、崖崩れ、土石流、火山等の分類も区別するべきかを議論すべきだと考える。

### 5.結論
本研究によってOpenStreetMapの目黒地区における避難所と広域避難所の情報の入力が完了し、避難所のwikiページの作成、及び日本において重要性の高い帰宅困難者支援施設のタグを新たに提案することができた。提案した議論に加えて更に細かい災害対策に関する情報をインドアマッピングで入力することで、より速やかな災害支援や避難をオープンソースで利用でき流ようになると考える。


