# NCKU ACM Notes

![](https://i.imgur.com/5jSeMTH.png)

This website is managed by NCKU ACM Training Course Team.

---
## Course

### 2018 Spring

* [課程連結](https://nckuacm.github.io/2018)
    * [寒訓網站](https://nckuacm.github.io/2018/winter.html)
    * [課程網站](https://nckuacm.github.io/2018)

---
## About NCKUACM Notes

### NCKUACM Notes 架構

* `_includes/` - 網頁區塊元件
    * `comment_count.html` - DISQUS 元件
    * `comments.html` - DISQUS 元件
    * `head.html` - `<head>` 下的內容
    * `navbar.html` - 預設的側邊目錄
    * `sidebar.html` - 定義的側邊目錄
    * `signature.html` - NCKUACM Training Team 的簽名檔
    * `yungshenglu.html` - 成員 Yung-Sheng Lu 的簽名檔
* `_layouts/` - 網頁版面，由 `_include/` 下的區塊所構成
    * `default.html` - 預設版面
    * `page.html` - 其他版面
    * `post.html` - 文章版面
    * `tag_index.html` - 標籤集合下的文章列表版面
* `_plugins/` - 網頁插件
    * `tag_gen.rb/` - 生成文章的標籤
* `_posts/` - 發佈的文章
* `fonts/` - 存放使用的字型
* `public/` - 存放圖片、CSS 檔案
* `slides/` - 存放投影片檔案
* `tags/` - 存放生成的文章分類標籤 (不需手動更新)
* `temp_posts/` - 存放尚未發佈的文章
* `_config.yml` - 定義 Jekyll 的參數與共用變數
* `atom.xml`
* `404.html`
* `about.md`
* `archieve.md`
* `index.html`
* `robots.txt`
* `sitemap.xml`

### 如何撰寫文章？

* 在 `temp_posts/` 或是 `_posts/` 下建立新的文章檔案，檔案名稱可以參考過去文章的各式 (`_posts/` 下的檔案)，檔名規定如下：`YYYY-MM-DD-檔名.md`。
* 在文章內，請務必複製以下表頭參數，可以參考 `_posts/` 下的檔案。範例如下：
    ```
    ---
    layout     : post
    title      : "UVA-696 - How Many Knights"
    subtitle   : "UVa Online Judge"
    date       : 2018-04-08 18:00:00
    author     : "Yung-Sheng Lu"
    tags       : OnlineJudge UVa Math
    comments   : true
    signature  : true
    slides     :
    present    :
    github     : https://github.com/nckuacm/OnlineJudgeUVa/tree/master/UVA-696
    link       : https://uva.onlinejudge.org/index.php?option=onlinejudge&Itemid=99999999&page=show_problem&category=&problem=637&mosmsg=Submission+received+with+ID+21105757
    ---
    ```
    * `layout` - 文章版面格式
        * 預設：`post`
        * 格式：使用預設值 `post`
    * `title` - 文章標題
        * 預設：必填欄位
        * 格式：任意值
    * `subtitle` - 文章副標題
        * 預設：必填欄位
        * 格式：任意值
    * `date` - 文章發佈日期與時間
        * 預設：必填欄位
        * 格式：`YYYY-MM-DD HH:MM:SS`
    * `author`  - 文章作者 (註：如何新增個人簽名檔？)
        * 預設：`NCKUACM Training Team`
        * 格式：任意值
    * `tags` - 文章分類標籤
        * 預設：空值
        * 格式：以「空格」切段作為文章標籤
    * `comments` - 是否允許文章開啟評論
        * 預設：`true`
        * 格式：`true` / `false`
    * `signature` - 是否嵌入作者簽名檔 (註：如何新增個人簽名檔？)
        * 預設：`true`
        * 格式：`true` / `false`
    * `slides` - 投影片連結
        * 預設：空值
        * 格式：`https://github.com/nckuacm/nckuacm_notes/slides/投影片檔名`
    * `present` - 投影片 LIVE 連結 (雲端投影片使用，如：Google Slides、Slides 等)
        * 預設：空值
        * 格式：連結網址
    * `github` - GitHub 連結
        * 預設：空值
        * 格式：連結網址
    * `link` - 外部連結
        * 預設：空值
        * 格式：連結網址

* 文章內容以 Markdown 語言，其中數學格式請參照 MathJax，可以參考 `_posts/` 下的文章。

### 如何發佈文章？

* 文章發佈務必在「文章發佈時間」之後，亦即：「不要發佈未來時間的文章」，可能會發生錯誤。
* 撰寫文章完畢後，若要發佈文章，請將文章置於 `_posts/` 下，檔名規定如下：`YYYY-MM-DD-檔名.md`；若還不想發佈文章，則可以置於 `temp_posts/` 下。
* 文章發佈流程：
    1. 將文章置於 `_posts/` 下，檔名規定如下：`YYYY-MM-DD-檔名.md`。
    2. 開啟終端機 (terminal) 並移至此專案資料夾下。
    3. 移除現有的 `_tags` 資料夾。
        ```bash
        $ rm -r tags/
        ```
    4. 編譯此專案
        ```bash
        $ Jekyll build
        ```
    5. 將新生成的 `_site/` 下的 `_tags/` 搬移到此專案的最上層，亦即：和 `_site` 同一層。
    6. 透過 GitHub 更新本次更動專案的部分
        ```bash
        $ git add .
        $ git commit -m "Update latest post"
        $ git push origin master
        ```
    7. 發布成功，可以稍等約 1 ~ 2 分鐘，至 `https://nckuacm.github.io/nckuacm_notes` 查看文章發佈的結果。

### 如何新增個人簽名檔？

* 個人簽名檔一律放置於 `_includes/` 下，檔案命名可以取自己的名字縮寫 (建議：與簽名檔照片的檔名相同)，並以 `.html` 格式命名。
* 個人簽名檔格式可以 `_includes/signature.html` 作為範本撰寫。
    ```html
    <div class="message">
        <!-- Signature Image -->
        <img class="profile" src="{{ site.baseurl }}public/nckuacm.png" alt="profile-image">
        <!-- Signature Content -->
        <div class="intro-title">
            NCKU ACM Training Team
            <div class="intro-message">
                This course is designed for ACM contest training in National Cheng Kung University.
            </div>
        </div>
    </div>
    ```
    * 個人簽名檔的照片檔案請放置於 `public/` 下，檔案命名可以取自己的名字縮寫 (建議：與簽名檔的檔名相同)，照片大小務必為「正方形」。
    * 在個人簽名檔中，個人照片的路徑需要在下方的 `src` 中 `{{ site.baseurl }}public/` 之後接上個人照片檔名。
        ```html
        <img class="profile" src="{{ site.baseurl }}public/nckuacm.png" alt="profile-image">
        ```
    * 在個人簽名檔中，「姓名」可以取代下方 `NCKU ACM Training Team`，「內容」可以取代下方 `<div class="intro-message">` 內的內容。
        ```html
        <div class="intro-title">
            NCKU ACM Training Team
            <div class="intro-message">
                This course is designed for ACM contest training in National Cheng Kung University.
            </div>
        </div>
        ```
* 完成個人簽名檔後，可以在 `_layouts/post.html` 中 `<!-- Member Signature -->` 之後新增以下片段：
    ```
    {% if page.author == "Author Name" %}
    {% include author_name.html %}
    {% endif %}
    ```
    * `page.author` 後要判斷「是否符合用戶的名字」(即：`Author Name`)，其中這個名稱即為「之後用戶發佈文章所用的名字」。
    * `author_name.html` 即是「引入該用戶的簽名檔」。

---
## Reference

* [C++ STL \<algorithm\> 使用](http://www.cplusplus.com/reference/algorithm/)
