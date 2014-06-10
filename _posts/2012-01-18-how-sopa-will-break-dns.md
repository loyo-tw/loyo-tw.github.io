---
layout: post-zh
title: How SOPA will break DNS
title-zh: SOPA 與 DNS 行為探討
description: "關於SOPA"
modified: 2012-01-18
tags: [SOPA,DNS,Small Talk]
comments: true
share: true
---

<figure class="half">
    <div class='img-center'>
    <img src="http://1.bp.blogspot.com/-VyMW-xGkvqk/TxMLaa5IfXI/AAAAAAAAAAg/bAoiloaAfTI/s400/IMG_2882_large_JPG_verge_medium_landscape.jpg" alt="">
    <figcaption>SOPA(Stop Online Piracy Act)，也稱為 H.R. 3261</figcaption>
    </div>
</figure>

隨著2012總統大選的結束，讓我將心思放回 SOPA 這事情上面，同時也將這件事情做一個紀錄和想法的整理。會注意到 SOPA 這個詞兒，除了在新聞中重覆聽到之外，竟然也和 DNS 這詞一起出現，畢竟智慧財產相關規範跟 DNS 實在沒有辦法直接聯想在一起( DNS 也有智慧財產？)，所以究竟 SOPA 和 DNS 到底是甚麼關係呢？

要探討這個問題前，勢必先行了解一下 SOPA 究竟是個甚麼樣的東西。
YouTube 與 vimeo 直接搜尋 SOPA 可找到許多相關的說明，以下截錄其中一則影片說明。

<iframe width="560" height="315" src="//www.youtube.com/embed/yDX8Lyl16Qs" frameborder="0"> </iframe>

[SOPA](http://en.wikipedia.org/wiki/Stop_Online_Piracy_Act)(Stop Online Piracy Act)，也稱為 [H.R. 3261](http://hdl.loc.gov/loc.uscongress/legislation.112hr3261) 看了全名就可以比較容易了解和防止線上盜版行為有關(縮寫完全猜不出來)。於 2011 年 10 月 26 日於美國眾議院被提出的法案，內容針對網路環境與智慧財產做出規範，像是在 YouTube 上傳非授權過的內容(MV, 電影內容等)都在其欲改善的範圍內。

針對防止線上盜版相關的法案， SOPA 並非第一例，例如  [PIPA - The PROTECT IP Act](http://en.wikipedia.org/wiki/PROTECT_IP_Act) (Preventing Real Online Threats to Economic Creativity and Theft of Intellectual Property Act) 又稱 S. 968 此法也為備受爭議之法案，且都延續了更之前的法案編修而來。延續之前法案編修這句話也許可以解讀成更嚴格的規範及更細節的限制，也因其過於嚴格的規範與牽扯到的關係者擴大，使得這些法案鬧得沸沸揚揚。以 SOPA 舉例，連搜尋引擎上的搜尋結果只要是牽扯到非法的內容或連結都有可能被此法限制禁止顯示甚至關站(這邊用限制存取該網站也許比較合理)，所以連 Google, YouTube 等服務都遭受波及。換句話說把這些防範侵權的責任推給 Google, Yahoo, YouTube 等服務去執行，辦不好就等著遭殃這樣的感覺，此舉當然引起這些大公司的不滿。

對於許多內容由用戶所產生的網站(如 YouTube)，其實是很難完全防止侵權內容的建立與傳遞。另外根據於 1998 年通過生效的數位化千禧年著作權法案(DMCA)規定，網站只需將被檢舉的內容於指定時間內移除即可，而 SOPA 的規範又與此部分有很大相似性，無疑是兩套標準的感覺。

<figure class="half">
  <img src="http://2.bp.blogspot.com/-KLa18wAbmBs/TxVHMgyAS3I/AAAAAAAAAAo/SSf9Dzlfi1U/s1600/youtube.png" alt="">
  <figcaption>針對有侵權嫌疑之影片，經投訴後會顯示無法播放。</figcaption>
</figure>

接著回到 SOPA 與 DNS 的關係，根據這些法案的內容，有提到可以將被檢舉的網站做限制存取的動作，便是透過  DNS 來做到的。舉個比較極端的例子：你在瀏覽器打了 YouTube 的網址，結果竟然沒有辦法連上 YouTube 的網站，甚至竟然連到了內容顯示「此網站含有侵權內容，無法顯示」的頁面，讓人情何以堪！(然後接著就打電話去罵 ISP 為什麼看不到XD)

上述舉的例子便是透過 DNS 的設定來做的網頁轉指向動作，強制將使用者輸入的網址轉到另一個特定的頁面甚至直接讓此網址沒有回應，在這樣做法下相信許多鄉民是難以接受的。

那麼 DNS 究竟是怎麼樣的東西呢，下面簡單說明一下：

> DNS 為網路上很重要的基本服務之一，簡單說就是將使用者輸入的網址轉成 IP Address 的服務。因為網路協定皆使用 IP 在運作，所以網址與 IP 之間的轉換是不可或缺的重要角色，此角色即為 DNS，目前 DNS 大部分是各 ISP 自行建置(如中華電信的 DNS 168.95.1.1, 168.95.192.1 或是 Google 的 DNS 8.8.8.8, 8.8.4.4)。

正因為 SOPA 透過 DNS 來限制網站內容的存取，而 DNS 又是很重要的基礎服務，這點引起了不少的議題。(補充： 不只 SOPA 有提出透過 DNS做存取限制，再更之前的 PIPA 也有提出類似的概念，兩者差異僅做了部分修改，於 PIPA 法案時已有許多反駁透過 DNS 做存取限制的聲音出現)。

首先對於 DNS 的部分來看，DNS 長久以來最困擾的問題就是使用者得到惡意的解析結果，明明輸入 YouTube 的網址，但是卻跳到某廣告商的網頁，更嚴重的就是輸入了某銀行的網址，但是卻連到某惡意釣魚網站進而騙取使用者帳號密碼的狀況，這點是非常需要改進的地方。然而若是因為網站有侵權內容而去刻意去做轉指向的動作，這不就是跟上述惡意解析結果的情境一模一樣嘛！而且還能打上「正義」這兩個字的名號。

<figure class="half">
  <img src="http://4.bp.blogspot.com/-YY9obznH-Fc/TxMLMggWOvI/AAAAAAAAAAY/kJ6yeIv_J9Q/s400/11548378_3f3489.jpg" alt="">
  <figcaption>冠上正義的字眼，是否就能忽略實質上的意義呢？</figcaption>
</figure>

那麼對於惡意解析結果這種輸入網址結果卻跑出不該出現的網頁的狀況，是否有解呢？

答案是有的。

DNSSEC(DNS Security Extensions) ，正是為了解決此問題而定義出來，透過數位簽章的概念來確保使用者輸入的網址和對應的 IP 正確無誤，不過因為實做上的困難推行至今仍未非常廣泛的被使用。但不可否認對於域名與 IP 對應完整性的需求日益增加，每天都有許多人不慎連到惡意的網址造成巨大的損失，為資訊安全的一大威脅。

<figure class="half">
  <img  style="vertical-align:middle;" src="http://2.bp.blogspot.com/-bLqZOdOUdpw/TxWzfBJWmeI/AAAAAAAAAC4/_YfIKQhV4Rk/s400/dnssec2.png" alt="">
  <figcaption>DNSSEC 藉由數位簽章的概念預防 DNS 紀錄遭受竄改</figcaption>
</figure>

然而 SOPA 所提出轉向或是不解析的動作，無疑會和 DNSSEC 數位簽章的概念相牴觸(因為無法對應到正確的簽章結果)，這樣不論哪邊勢必都會面對相當程度的修改及妥協，造成 DNSSEC 實行及有效性的一大障礙。

另外因為 DNS 設定是可以由用戶自行做修改的，所以若是因為 SOPA 一案的關係，造成網頁無法正常瀏覽，使用者大可以自行修改 DNS 設定改成海外的 DNS Servers，如此一來又是暢行無阻活蹦蹦的一尾活龍了，但延伸的問題是海外之 DNS Server 是否安全以及 DNS 整體環境架構的改變的議題。

接著針對實作面來看的話，確實透過 DNS 來做轉向的動作是辦得到的，但需注意造成的影響可以非常大，更不提這些網站清單的維護與更新了(清單維護成本與責任應該是落在 ISP 頭上)。越往基礎服務去動手腳所造成的影響會越大，相對應的成本也會越高。

防止盜版的議題一直都備受重視， SOPA 法案的提出也說明了對此的決心，但整體的手法是否能被大眾所接受是個很大的問題，背後牽扯的商業利益與各服務之間的立場有著非常敏感的關係。更重要的是，網際網路上的自由度不容忽視，也許這是一個險惡的環境，但這取決於使用者的道德標準與良知，法律只是其中的一個環節但並非全部，當我們連上網路時，早就已經深陷其中的一環，保護自己的權力也讓這個環境保持開放自由的標準。

最後，若 SOPA 法案實行後，何時會輪到我們？ 也許就是我們忽視這些事情的時候。

備註：
寫這篇文章本來是想紀錄一些自己的觀察和想法，其中也包含了很多自己的觀點，若有錯誤或不宜的地方，也請不吝指教。針對這部分的觀察，也許會在整理成一篇心得吧。

參考資料：

* [http://en.wikipedia.org/wiki/PROTECT_IP_Act](http://en.wikipedia.org/wiki/PROTECT_IP_Act)
* [http://en.wikipedia.org/wiki/Stop_Online_Piracy_Act](http://en.wikipedia.org/wiki/Stop_Online_Piracy_Act)
* [http://www.dns.com.tw/?p=1765](http://www.dns.com.tw/?p=1765)
* [http://blog.trendmicro.com/unintended-consequences-how-sopa-could-threaten-internet-security/](http://blog.trendmicro.com/unintended-consequences-how-sopa-could-threaten-internet-security/)
* [http://www.circleid.com/pdf/PROTECT-IP-Technical-Whitepaper-Final.pdf](http://www.circleid.com/pdf/PROTECT-IP-Technical-Whitepaper-Final.pdf)
* [http://www.techdirt.com/articles/20111214/18075617093/former-dhs-assistant-secretary-stewart-baker-sopa-20-still-disaster-cybersecurity.shtml](http://www.techdirt.com/articles/20111214/18075617093/former-dhs-assistant-secretary-stewart-baker-sopa-20-still-disaster-cybersecurity.shtml)
* [http://www.circleid.com/posts/20111211_technical_comments_on_mandated_dns_filtering_requirements_sopa/](http://www.circleid.com/posts/20111211_technical_comments_on_mandated_dns_filtering_requirements_sopa/)



