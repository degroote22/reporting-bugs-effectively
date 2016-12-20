# 如何有效地報告錯誤

_作者: Simon Tatham, 專業及免費軟體程式師_

翻譯:梅普華

## 介紹

寫過供大眾使用軟體的人可能都收過一份以上的爛錯誤報告. 有啥都沒講的報告(這個程式不會動), 有不合理的報告或資訊不足的報告, 也有提供**不正確**資訊的報告. 還有一些報告查到後來不是使用者自己攪錯, 就是其他程式惹禍, 或是網路斷線等等.

有個理由可以解釋為什麼技術支援工作這麼難做, 原因就是這些亂七八糟的錯誤報告. 不過並非所有錯誤報告都是這麼糟糕. 我工作之餘有在維護免費軟體, 有時候會收到一些非常清楚有幫助而且**很有內容**的錯誤報告.

我會試著在這篇短文中清楚說明良好錯誤報告的重點. 基本上我希望全世界的人在報告任何錯誤前都能讀讀這篇短文. 當然我更希望每個送錯誤報告給**我**的人都讀過.

簡而言之, 錯誤報告的目的是要讓程式師能親眼目睹程式出錯. 你可以親身示範給他們看, 也可以提供一份詳細而徹底的指令教他們如何重現問題, 如果他們可以重現問題, 就會試著收集更多資訊去瞭解問題的原因. 如果他們無法重現問題, 就只能要你幫他們收集資訊.

在錯誤報告中, 必須要把真實發生的事實(我在電腦前看到這個狀況)和臆測(我**認為**問題可能是)很明顯的區分開來. 必要時可以把臆測略過不提, 不過事實絕對不能漏.

因為你希望錯誤能被修正, 才會提出報告錯誤. 沒有必要對程式師惡言相向或故作無助: 問題有可能是他們搞的, 但也可能是你自己惹的. 或許對程式師發脾氣有點道理, 不過如果你能協助提供所有必要的資訊, 問題就能儘快修好. 另外也請記住, 既然程式是免費的, 表示作者是基於好心而提供的. 如果很多人對他們不禮貌, 他們可能就不會那麼好心了.

## "程式不會動."

多少相信程式師的基本智能吧. 如果程式完全不會動, 他們應該會發現的. 既然他們沒有發現, 表示他們用的時候沒問題. 所以要不是你的作法和他們不同, 就是你的環境和他們不同. 他們需要資訊, 錯誤報告的目的就是提供這些資訊. 資訊過多往往好過資訊不足.

很多程式(特別是免費的)都會公開已知的問題清單. 如果你能找到這樣的已知問題清單, 應該好好讀一遍, 看看你剛發現的問題是否為新問題. 如果是已知的問題就不值得再報告一次, 不過如果你認為你的資訊比較齊全, 還是可以聯絡程式師. 因為如果你能提供一些原本沒有的資訊, 他們或許能更輕易地解決問題.

這篇短文充滿了指引原則. 這些原則都不是絕對不變的規定. 每個程式師自有期望的錯誤報告方式. 如果程式附有自己的錯誤報告指引原則, 應該要讀一遍. 如果程式所附的指引原則與本文衝突, 就照程式的規矩來做.

如果你不是在報告錯誤, 而是就程式使用上的問題求助, 應該說明已經在那些地方找過答案(我看了第4章的5.2節, 可是找不到任何相關的內容). 這會讓程式師知道人們會期望到什麼地方找答案, 以後就能讓文件更易使用.<a name="showme"></a>

## <a name="showme">"試給我看."</a>

報告錯誤的最佳方法之一就是直接示範給程式師看. 讓他們站到你的電腦前面, 執行他們的軟體, 然後指出問題所在. 讓他們看著你打開電腦, 看著你執行並操作軟體, 並且看到軟體所產生的反應.

程式師對自己的程式瞭若指掌. 他們知道哪些部份絕對正確, 也知道哪些部份可能會有問題. 他們光憑直覺就知道要找些什麼. 在程式跑出明顯的錯誤之前, 他們可能已經提早注意到一些**細微**的錯誤並從中得到線索. 他們可以觀察電腦所有的執行過程, 並且挑出對他們重要的資訊.

有了這些可能還不夠. 他們可能會覺得還需要更多資訊, 並且要求你重複執行給他們看. 他們也可能會要你說明整個操作過程, 以便他們能自己重複重現問題. 他們也可能會改變操作過程多試幾次, 看看問題只在某一種狀況發生, 還是在相關的多種狀況下都有出現. 如果運氣不好, 他們可能得坐下來花上幾個小時拿出整組開發工具**真正**深入調查. 不過最重要的還是讓程式師看到電腦出錯. 只要他們能看到問題發生, 通常都可以由此開始嘗試修正問題.

## "教我如何做給自己看."

現在是個Internet時代. 同時也是全球通訊的時代. 在這個時代只要按個鈕就能把我的軟體傳送給位在俄羅斯的某人, 對方也一樣能輕易地把意見傳給我. 不過如果他用我的程式遇到問題, 可就**沒法子**把我找到他電腦前看著程式出錯. 如果能的話, "試給我看"的作法是很好的, 不過通常都做不到.

如果你必須向一個不可能到你身旁的程式師報告錯誤, 首要目標是讓他們能**重現**問題. 希望讓程式師執行自己的那份程式, 進行相同的操作, 然後以相同的方式出錯. 當他們能親眼看到問題發生, 就可以開始處理.

所以你得絲毫不差地把自己做的事告訴他們. 如果這是個有圖形介面的程式, 告訴他們你按了哪些按鈕以及按各按鈕的次序. 如果是輸入命令執行的程式, 就要精確地告知你所輸入的命令. 可能的話應該儘量提供整個過程的精確記錄, 裡面包含所有你所輸入的命令以及電腦的反應.

把你所能想到的所有輸入都給程式師. 如果程式由某個檔案讀資料, 你可能也得送一份檔案拷貝過去. 如果程式會透過網路和另一台電腦通訊, 你可能沒法子把另一台電腦送過去, 不過至少可以說明電腦的類型 以及上面所執行的軟體(如果能的話).

## "我這裡能正常執行. 究竟出了什麼問題?"

如果你提供程式師一長串輸入和動作, 他們照著執行自己的程式, 結果卻一切正常, 表示你提供給他們的資訊還不夠. 可能是這個問題並不會在每台電腦出現; 或是你和他們的系統間有某些差異. 也可能是你誤解了這個程式的作用. 你們看到一模一樣的顯示輸出, 可是你認為這樣的輸出是錯的, 而他們知道這是對的.

所以你也得敘述發生的事情. 精確地告知你看到的內容. 告知為何你認為所看到的內容是錯的; 如果能告知你預期看到的結果更好. 如果你用"然後就出問題了"這種寫法, 就會略過了一些非常重要的資訊.

如果你看到錯誤訊息, 應該要小心精確地告訴程式師訊息的內容. 這些訊息**非常**重要! 在目前這個階段, 程式師只是想找出問題所在, 並不會嘗試去修正問題. 他們必須知道什麼地方出錯, 而那些錯誤訊息正是電腦對問題的最佳敘述. 如果沒有其他方法能輕易記下問題就把問題抄下來. 不過如果不能同時報告錯誤訊息的內容, 光說程式出錯是沒有意義的.

如果錯誤訊息裡有數字時更要特別注意, **一定**要讓程式師知道那些數字. 你看不懂並不表示沒有意義. 這些數字裡面隱藏有程式師能解讀的各種資訊, 而且很可能包含極重要的線索. 錯誤訊息裡會有數字, 是因為電腦無法精確地用 文字回報錯誤, 只能儘量用其他方式把重要的訊息呈現出來.

在這個階段程式師事實上是在做偵探一樣的工作. 他們不知道發生什麼事, 也無法接近現場親眼目睹, 所以只能努力找尋線索把問題挖出來. 錯誤訊息, 無法理解的數字代碼, 甚至無法解釋的遲滯都和犯罪現場的指紋一樣重要. 所以一定要保存起來.

如果你用的是Unix, 程式可能會產生一個核心傾印(core dump). 核心傾印是個很好的線索來源, 所以絕對不要刪掉. 不過大部份的程式師都不喜歡突然收到附有核心傾印大檔案的電子郵件, 所以寄出前一定要先詢問對方. 另外有一點要特別注意, 因為這個檔案記錄了完整的程式執行狀態, 所以裡面可能含有各種"機密" (程式可能正在處理私人訊息或機密資料).

## "問題出現後我又試著..."

當錯誤發生之後, 你可以做各種因應的動作. 大部份動作都會讓問題更嚴重. 我有個唸書時期的朋友不小心刪掉她所有的Word文件, 她在找專家求救之前試著重裝了Word又執行"磁碟重整". 這兩個動作對救回檔案都沒有幫助, 反而把磁碟機內容弄得更亂. 最後就是沒有任何檔案回復程式能救回她的檔案. 如果她把電腦放著不去動, 可能還有點機會.

這樣的使用者就像縮在角落的麝香猴: 背緊貼著牆面對死亡威脅時會瘋狂地攻擊, 因為它覺得有動作總比什麼都不做要好. 不過這種作法並不適用於電腦產生的問題.

和麝香猴相反的是羚羊. 當羚羊面對無法預期的事物或害怕時就會定住不動. 它會停下來保持完全靜止, 試著不要引起任何注意, 同時思考最佳的因應措施. (如果羚羊有技術支援專線可用, 這時候就會打電話求援.) 一旦決定最安全的做法後, 它就會照著執行.

所以遇到問題時要立即停止**所有動作**. 不要碰任何按鍵. 看著螢幕注意是否有任何不尋常的地方, 然後把異常之處記下或抄下來. 再來或許可以小心地按"確定"或"取消", 看哪一個看起來最安全而定. 要試著養成一種直覺反應 - 如果電腦出現預期之外的反應, 什麼都不要動.

如果你有辦法排除問題(不管是把出問題的程式關掉或是重開電腦), 可以試著讓問題再次重現. 程式師喜歡那些能重複產生的問題. 這時候快樂的程式師能更快更有效率地修正問題.

## "我認為一定是超光速調變的極化出了問題."

並不是程式師以外的人才會寫出爛錯誤報告. 我所看過最糟糕的錯誤報告中有些就是程式師寫的, 而且有些還是很優秀的師式師.

我曾經和另一個程式師合作, 他一直在尋找自己程式裡的錯誤並試著修正. 每次遇到解不出來的問題時, 就打電話叫我幫忙. 當我問他"哪裡出錯了?", 他就會回答他目前對問題應如何修正的看法.

如果他的看法正確無誤事情就很順利. 由於他已經把事情完成一半了, 我們就能一起把工作完成. 這時候他的意見很有幫助 而且非常有效.

問題是他經常會出錯. 這時候他會花時間找出為何程式中某個部份產生錯誤的資料, 到最後才發現那些資料是正確的, 結果我們花了半小時去查一段完全正確的程式碼, 而實際的問題卻在別的地方.

我確信他並不會對醫生這樣做. 大家都不會和醫生這樣講話:"醫生, 我得了Hydroyoyodyne病(譯註:虛構的怪病), 給我開個藥吧.". 你應該會說有哪裡不舒服, 哪裡酸痛哪裡起疹, 有沒有發燒等等, 然後讓醫生診斷並開出處方. 否則醫生會把你當憂鬱症或神經病, 理直氣壯地趕你出門.

對程式師也一樣. 提供你自己的診斷有時可能有幫助, 不過一定要先敘述症狀. 診斷是可有可無的, 絕不能取代症狀敘述. 同樣的道理, 在錯誤報告之外附加一份把問題修好的程式碼是很有幫助, 不過程式碼並不能取代錯誤報告.

如果程式師要你提供更多資訊, 絕對不要偽造資料! 曾經有人回報一個錯誤, 我要他試一個我知道不能動的命令. 要他試這個命令, 是因為我想知道它會出現哪一個錯誤訊息. 知道會傳回哪一個錯誤訊息就等於得到重要的線索. 可是他並沒有真的去試, 卻直接回信給我說:"不, 那個命令沒有用." 我費了好一番功夫才說服他實際去試命令.

用你的聰明智慧幫助程式師是很好. 即使你的推論不對, 程式師也應該心存感謝, 因為至少你已經**試著**讓他們更好過. 不過記得要報告症狀, 否則你可能會讓他們過得更痛苦.

## "真奇怪, 剛剛才出過問題的."

程式師聽到"偶發性的錯誤"一定都會很頭大. 能依照某段單純動作過程產生的錯誤算是簡單的問題. 程式師可以在嚴密觀察的測試環境下重複這些動作, 仔細觀察問題發生時的所有細節. 不過很多問題都不是這樣的: 有些程式一星期會當一次, 也有些問題很久很久才出現一次, 還有些問題程式師在的時候絕不出現, 等最後期限逼近時卻時常發作.

大部份偶發性的錯誤並不是真正的偶發. 其中多數都有某些邏輯存在. 有些可能是在機器記憶體不足時才出現, 有些錯誤可能是因為另一隻程式在不對的時點修改一個重要檔案, 還有些錯誤可能只在每小時前30分出現! (我真的遇過這種錯誤)

如果你能重現錯誤而程式師不能, 很可能是因為你和程式師的電腦在某個地方有差異, 而這個差異就是問題的原因. 我曾經遇到一個怪問題, 視窗會在螢幕左上角**縮成**一個小球. 不過只有在800x600的螢幕上才會發生; 在我的1024x768螢幕上完全沒有問題.

程式師會想得到你對於問題所知的全部資料. 你可以在另一台機器試看看. 也可以試個兩三次看看出問題的頻率如何. 如果問題只在你努力工作時才出現, 要展示給別人看時又完全正常, 出錯的原因可能是長時間執行或檔案太大. 試著記下出錯時你正在做的動作, 而且儘可能記下細節. 如果觀察到任何模式都要記下來. 你所提供的任何資料多少都有幫助. 即使只是"機率性"的敘述 (比如有執行Emacs時似乎比較容易當), 雖然不能提供指向問題的直接線索, 不過還是可能協助程式師重現問題.

更重要的是, 程式師要確認他們處理的是真正的偶發性問題還是與機器相關的錯誤. 他們會要知道很多有關你的電腦的細節, 這樣才能找出你的電腦和他們的電腦的差異所在. 很多細節會視程式而定, 不過版本號碼通常是一定要的. 程式本身的版本, 作業系統的版本, 可能還要包括其他與問題有關的程式的版本號碼.

## "所以我把磁片載入視窗系統中..."

寫得清楚是錯誤報告的基本. 如果程式師看不懂你的意思, 報告有寫等於沒寫.

我收到全世界來的錯誤報告. 很多報告來自非英語系地區, 而且很多人為英文寫得不好致歉. 通常有為英文不好而致歉的錯誤報告實際上都非常清楚有用. 寫得最含糊不清的報告全都是來自英語系地區, 這些作者認為他們不必寫的清楚精確, 我還是能明白其中的意思.

*   **要明確**. 如果你可以用不同方法完成同一件事, 就要寫出你用的方法. "我選取Load"可能是說"我點選Load"或是 "我按了Alt-L鍵". 把你做的事說清楚. 有時候這點很重要.
*   **要詳細**. 寧願多給資訊而不要少給. 如果你說得太多, 程式師可以略過一些不看. 不過如果你說得太少, 他們就得回來問更多的問題. 我收過一份裡面只有一句話的錯誤報告. 我花了好幾個星期才得到足夠份量的有用資訊, 因為他的回覆每次都只有一個短句子.
*   **要小心代名詞**. 避免在意義不明確時使用"它"或"視窗"之類的字眼. 考慮以下的狀況: "我啟動FooApp. 它跑出一個警告視窗. 我試著把它關掉可是它當掉了." 這裡並沒有明確指明使用者想關掉什麼東西. 他究竟要關掉警告視窗還是整個FooApp? 你可以改寫成"我啟動FooApp, FooApp顯示一個警告視窗. 我試圖關閉警告視窗, 結果FooApp當掉了." 這些寫比較長而且囉嗦, 不過比較清楚也不容易誤解.
*   **閱讀你寫的東西**. 自己把報告重新讀一遍, 看看有是否夠清楚. 如果你有寫出了重現問題的步驟列表, 試著照做一遍確定沒有漏掉任何步驟.

## 摘要

*   一份錯誤報告的首要目標是要讓程式師親眼看到問題. 如果你不能到他們面前把問題顯示出來, 就得提供詳細的指示讓他們能自己做出來.
*   萬一首要目標無法達成, 程式師**沒法子**自己看到問題發生, 那麼錯誤報告的第二目標就是描述問題狀況. 儘量詳細敘述每件事. 把看到的東西都寫出來, 期望看到的東西也要寫出來. 錯誤訊息也要抄下來, 如果訊息裡有數字的話**更是**不能漏掉.
*   當你的電腦出現預期之外的反應, 記得**什麼動作都不要做**. 在你冷靜之前什麼都不要做, 另外不要進行任何有危險性的動作.
*   如果你自認能力夠的話可以儘量嘗試自己診斷問題, 不過即使你做了診斷, 還是應該報告問題的症狀.
*   要準備在程式師需要時提供額外的資訊. 如果他們不需要就不會要. 程式師並不會故意刁難. 還有可以把版本號碼先準備好, 因為很可能會需要.
*   要寫得清楚明白. 照你的意思去寫並且確定意思不會被誤解.
*   最後一點就是**要精確**. 程式師喜歡精確.

* * *

**聲明:** 事實上我從未看過麝香猴或是羚羊. 我的動物學知識不一定是對的.