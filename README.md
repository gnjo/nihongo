# nihongo
nihongo eval engine

### 減点方式
```
文節に対して加点を行う。文節は句読点で区切られたまとまりの事である。文節毎に加点１する。
一度評価し、変更がないものは高速化の為に評価を省略する。
その後減点を行う。減点は全て１であるので、フラグ形式で有無情報を保持する。
機能１：接続詞の追加。接続詞は、順接の場合は基本的に不要である。
機能２：「にのではが」の連続。XのYのは、別の用語に変更可能である。XでYでも同様である。一文に対して評価する。
機能３：二単語以上の横文字。
機能４：３４行に対する、句読点数。
```
```
３４行の区切りに対して、全体評価を行う。初期値は+0。減点される毎に-1となる。-3以上は打ち切り。
機能は、表示と詳細に分かれる。表示は機能詳細の概要として適切で、字数の少ない物とする。
表示にカーソルを当てた場合、その－であれば、対象行を表示する。
接続詞：+0：接続詞の数一つ毎に減点１。
にので：+0：助詞「にのではが」の連続は不要。
横文字：+0：横文字の数。基本は少ないほうが良い。重複単語は一。例えば、フラグはフラグ、は一つと数える。
読点数：+0：三十四行に対する句読点数。基本は少ないほうが良い。
四ひら：+0:ひらがなが四文字以上連続した場合に減点される。
漢ひら：+0:漢字とひらがなのバランス。均等が最低基準。漢字が多い方がより良い。カタカナは漢字として計算する。
体言バ：+0:体言止めのバランス。五節に対して、体言止めは一以上。
指示語：+0:指示語は最小にする。
```
```
チートシートが右にあれば良いのでは。
```
接続詞。
```
順接：だから、そこで、従って、故に、それ故、すると、それなら、それでは
逆説：しかし、が、けれども、処が、にも関わらず、それでも
並列：また、および、かつ、ならびに、同じく
添加：そして、それに、それから、しかも、その上、そればかりか、そればかりでなく
対比：一方、他方、逆に、反対に、反面
選択：または、それとも、あるいは、もしくは
理由：なぜなら、というのは
補足：なお、但し、ただ、尤も、ちなみに、そもそも、その割
類例：つまり、すなわち、要するに、例えば、いわば
注目：特に、とりわけ、中でも
転換：さて、処で
```
