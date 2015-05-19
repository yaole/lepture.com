# 不被重視的 HTML：Accessibility

- date: 2014-10-12 10:40
- tags: talk, web

這是 JSDC 2014 的講稿（2014-10-11），內容是關於 Web Accessibility 的，與 JS 的關係不大，主要是關於 HTML 的。

-----

- Slide: <http://lab.lepture.com/jsdc-2014/slide.html>
- Repo: <https://github.com/lepture/jsdc-2014>

大家好，我今天談一點 Web 可訪問性的話題，主要是 HTML 相關的，與 JS 的關係並不是很大。

（自我介紹略）

那我要講可訪問性，當然是因爲它很重要，比如說它有經濟價值，因爲生活中有許多某種能力缺失的人。比如說有些國家的法律規定了，你必須實現 Web 的可訪問性。但是最重要的是，做爲開發者，你本來就應該做這些事。爲什麼呢？因爲這是標準規範，你所需要的只是遵循這些標準與規範而已。

我們舉點現實生活中可訪問性的例子，比如捷運都有一個可容輪椅的入口，這方便殘疾人通過，比如說小便池有一個比較低，這方便小朋友。但是還有一些事情就不太如意了，比如說紅綠燈。我們看這樣一個交通燈，對紅綠色盲來說就沒有識別度了。

我們看看色盲這一塊，這個圖片你們能看到上面是什麼數字麼？如果你看到的不是 74 的話，那你可能就是色盲了。那這一塊呢，其實在現實生活中是做得挺差的。參見中華民國《道路交通安全規則》第六十四條，對考駕照者有一項要求，即能辨別紅、黃、綠色，也就是說紅綠色盲是不能考駕照者。這當然可以理解，但是只要我們的紅綠燈稍微改變一下，比如給紅綠燈加上形狀，那紅綠色盲者不就能識別了麼。你要知道，全世界有大約 8% 的人是紅綠色盲呢。現實挺不公平的，要改變也需要花費更多的人力與時間。

但是互聯網不一樣。互聯網意味着自由平等，它從一開始就是爲所有人設計的，所有人理應都能正常的使用互聯網。我們舉個好一點的例子。大家知道 Trello 吧，不知道也沒關係，它是一個項目管理工具。Trello 的個人設置裏有一個選項叫色盲友好(Color Blind Friendly)，開啓之後 label 的背景就是不純色了，比如你看這個綠色裏有斜線，這樣就不會和紅色的 label 混淆了。

本來講這個話題，我是挺擔心的，怕是班門弄斧了。不過用了一下臺灣的一些公共服務網站後，發現這個擔心有點多餘了。我之前以爲只有大陸的這類網站難用，原來臺灣的也一樣嘛。

可訪問性其實是一個很大的話題，它應該從設計之初就被重視起來，比如前面提到的 Trello 的例子，它是一個設計方面的實現。當我們談可訪問性時，不僅僅只是只視覺障礙者，也包括其它感觀有問題的人，比如說聽覺，甚至也包括所有感觀都正常的人。例如在現在的屏幕分辨率下，還有許多網站的文章正文字體大小居然是 12px，根本就看不清楚嘛，這也可以說是可訪問性差。關於閱讀性文字，我有寫一個 CSS 庫，[yue.css](http://lab.lepture.com/yue.css/)，大家有興趣可以看看。

在可訪問性這一塊，我們有些官方網站確實有在做。但是他們的做法都是錯的，基本相當於形象工程。比如說人民網，這個是大陸的一個官方媒體網站。他們專門爲盲人開設了專欄，就會有語音讀內容了。還有一些政府網站也是差不多，給你專門開設一個盲人用的網站，好像獻愛心一樣。但是他們的網站其實正常人用起來都很費勁啦。

這種特殊對待的方案都是錯誤的做法，大家也不怎麼埋單。因爲並沒有什麼特殊的地方，Web 在設計時就已經考慮到這些問題了，也都有通用的解決方案。

我們講可訪問性，這個話題的內容有點多，不會在這裏細講。我們單講點與前端，與寫代碼有點關係的。雖然這件事應該從設計之初就要考慮。

所謂工與善其事，必先利其器。所謂知已知彼，百戰不怠。我們看看盲人上網用什麼，用讀屏軟件嘛。Mac 在這一塊做得就比較好，系統自帶的 Voice Over 挺好用的。Windows 我沒有怎麼用過，也沒聽人說用 Windows 自帶的工具，一般都是另外買的。因爲我是用 Mac 的，只需要了解一下 Voice Over 就夠了。

那現在有 Mac 的同學們可以看看 Voice Over 怎麼用的，Command + F5 就可以開啓了。

（演示 Voice Over）

其實 Accessibility 的實踐是件很簡單的事，並不需要花多少時間與精力，只需要做一點點小改變就可以提高不少。

那我們舉個很簡單的例子。許多網站都有用 icon font 來做圖標，很流行哦，看起來都很不錯的樣子。可是許多時候就忽略了可訪問性了。比如有的圖標，你根本就猜不出來它是什麼意思，這對視力正常的人來說都沒有可訪問性，你需要加個 tooltip 之類的來解釋一下。那我這裏的這個例子是一個齒輪圖標，大家都知道它是 settings 的意思啦，那對視力正常的人來說還好，但是假如你看不見的話，你根本就不知道它是個什麼東西。

那我們給這個圖標一個很簡單的屬性（attribute）aria-label=“Settings”，我們來看看 demo。

（使用 Voice Over 演示一下兩者的區別）

上面這個例子是不是很簡單？我們現在就可以開始做出改變了。比如零時政府不是有一個萌典網站麼，我們看看萌典的網站，上面不是有很多 icon font 麼，大家可以給它加上 aria-label。

我們再舉一個簡單的例子，Landmarks。

這個也是個挺簡單的東西，內容也不多，就這麼幾個（見 slide），但是作用卻很大，使用 Voice Over 可以方便的跳轉。那我們來看一個例子，其實就是給相應的 block element 標上相應的 role 就好了。我們先看一下 Voice Over 的設置，需要它支持 Landmarks，把這個勾上就好了。那我們看這個 demo，我們開啓 Voice Over，Command + F5，然後用 Web Rotor 快速定位 landmarks，VO + U，也就是 Control + Option + U，那如果沒有出現 Landmarks 的選項的話，就按一下左右鍵。那這個時候就可以很方便的定位了，比如你看一篇文章，那就是在 main 區域裏，那你要跳轉頁面的話，就跳到 navigation 裏去咯。

我們再演示一個 aria live region 的例子。我們看這個 demo，只需要打開 Voice Over 就好了，它會自己提示你有新訊息。如果沒有效果的話，檢查一下 Voice Over，看看是否打開了 live region 的支持。這個功能在 Twitter 的信息流裏有用到哦。

但是要真的做好可訪問性，又是一件很困難的事。它的困難主要還是在複雜度上面，你需要考慮的東西太多了。那這裏舉一個 UI widget 方面的例子，tablist。我們簡單看一下它的 HTML 結構，這裏使用的 attributes 就多很多了，我們看到有 role，有 aria-selected，aria-controls 之類的。看起來會比較複雜。同時我們還要考慮正常的視覺效果，這裏有個小 tricks，我們把 aria-hidden=true 設置爲 display none，這樣讀屏軟體讀不到，視覺上也會看不到。

（演示 tablist demo）

那這樣一個小的 UI widget 看起來就有點麻煩了，那想想整個網站，是不是會更無從下手呢。

除了複雜以外，還有一些歷史問題。比如說這個 aria-required 與 required。aria-required 是給讀屏軟體用的，required 是 HTML5 新加的特性。那我們應該用什麼呢！放在今天來看的就，當然是用 required 就可以了。這裏就會有一個可訪問性上的 attributes 與 HTML5 的重複，我會激進一點，傾向於只用 HTML5 的部分，其實大多數瀏覽器已經支持得挺好了。那我們來看一下 aria required 的 demo。

(演示 aria-required demo）

那你還可能需要考慮一下 keyboard binding，就是鍵盤快捷鍵。有些需要滑鼠操作的才能工作的地方，你可能就需要設計一些 key binding 来幫助别人使用。那對於盲人來說呢，使用鍵盤是比使用滑鼠要方便多了的。

然後還有驗證碼，就是你註冊時經常會出現的那個東西。比如這個，這個是支付寶登錄時的驗證碼，它是個扭曲的字符，K8WM，我們也許看得清楚，但是如果看不到的話，那怎麼處理呢。這是我聽說的，據說有一個 QQ 羣，你把圖片 copy 一下，發到羣裏，然後會有視力正常的人告訴你這是個什麼東西，挺麻煩的吧。但是在臺灣就不用這麼麻煩了，你們知道 reCaptcha 這個項目吧，現在是 Google 的了。我們看一下 reCaptcha，它不僅有圖片，還是聲音驗證碼，就是這裏，你點這個地方就會有語音，那這樣看不到的人就可以用聽的了。這個服務挺方便的，但是在大陸就用不成，因爲被牆了嘛。但是臺灣沒有呀，如果大家自己有做網站，需要用到驗證碼的話，就儘量使用 reCaptcha，也比你自己寫一套 Captcha 要方便。

那我說到提升可訪問性是件很簡單的事，也是件很困難的事。做一點點改變是很簡單的，比如之前說的給 icon font 加上 aria-label，真的挺簡單的。可是你要一口氣做得很完美的話，那幾乎就不可能了。我們一點一點改變，慢慢來，總是好的。不積跬步無以至千裏嘛。

同時它也能幫你更好的組織整理你的 HTML 結構，能幫助搜索引擎更好的索引。它對你寫 HTML 有一定的指導意義。（略）

最重要的還是我們開發者，身爲開發者應該有的驕傲。我們有能力去實現這些標準，那我們就會做咯，這是基本的職業素養。下面這些鏈接都是不錯的資源，大家可以都看看。

謝謝。那我就講完了。

哦。 One more thing，這個 slide 本身也是 accessible 的。

（演示 slide 的可訪問性）