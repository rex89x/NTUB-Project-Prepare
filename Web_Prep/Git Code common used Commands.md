# Git Code common used Commands

View the git code with HackMD.

CMD Common Used Commands
---

- pwd------------Print Working Directory：所在位置
- ls------------List：資料夾下所有檔案
- cd------------Change Directory：切換位置(補充：cd.. 切到上層）
- man------------Manual：使用說明書
- touch------------建立檔案、更改時間
- rm------------Remove：刪除
- mkdir------------Make directory：建立資料夾
- mv------------Move：移動、更名
- cp------------Copy：複製

CMD Well Used Commands
---

- vim：文字編輯器(補充：wq 存檔跳出、i 插入文字、esc 普通編輯模式)
- grep：抓取文字
- wget：下載檔案
- echo：印出文字
- curl：送出 request
- ">"：重新導向
- ">>"：新增內容
- "|"：把很多指令接起來

Git CMD Common Used Commands
---

- git inint--initial：告訴 Git 要做版本控制，用來初始化
- git status：查詢狀況
- git add + (檔案名稱)：將檔案加入版本控制
- git rm --cached + (檔案名稱)：將檔案移除變 untracked
- git commit：新建版本
- git commit -am + (訊息)：新建版本且可留言
- git log：查看歷史資料(補充：+ --online：簡短歷史資料)
- git checkout：回到之前版本
- git checkout master：回到最新狀態

Git Branch CMD Well Used Commands
---

- git branch + (名稱)：建立 branch
- git branch -v：查看有哪些 branch
- git branch -d：刪除 branch
- git merge：合併 branch (補充：merge 可能會造成衝突(conflic)，此時需手動解決)

Git Github CMD Create a new repository on the CMD
---

- echo "# practice-git" >> README.md
- git init 
- git add README.md
- git commit -m "first commit"
- git remote add origin git@[網址]
- git push -u origin master

Git Github CMD push an existing repository on the CMD
---

- git remote add origin git@[網址]
- git push -u origin master

Rex Tsou 2021/05/08

###### tags: `Django` `Templates` `SQL`
