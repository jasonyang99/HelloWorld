![Alt text](https://www.advantech.tw/css/css-img/advantech-logo-notagl.svg "Hello git")

![alt text](https://github.com/Advgcipc/HelloWorld/Fork.png "Fork Icon")


![Alt text](https://i.iter01.com/images/e2cf72ca1cfe4a9d2ada8555a68d2cd544ae2bb3068c6a48b460798d4144f6c2.png "git SSH clone")



>第一步：設定原作的遠端節點
舉例來說，這是 Fork 過來的專案：

$ git remote -v
origin	https://github.com/eddiekao/dummy-git.git (fetch)
origin	https://github.com/eddiekao/dummy-git.git (push)


git remote 指令加上 -v 參數後可以看到更完整的資訊。從這裡可以看得出來目前這個專案只有設定一個遠端節點 origin。接下來我要幫它加上另一個遠端節點，這個遠端節點指的位置就是原作的專案：

$ git remote add dummy-kao https://github.com/kaochenlong/dummy-git.git


其實大部份的資料都會教你使用 upstream 做為原作遠端節點的名字，但為避免大家跟之前在「Push 上傳到 GitHub」章節介紹的 upstream 搞混，所以這裡我故意使用 dummy-kao 做為指向原作的遠端節點。這時候在這個專案應該就有 2 個遠端節點了，一個是原來的 origin，一個是原作的 dummy-kao：

$ git remote -v
dummy-kao	https://github.com/kaochenlong/dummy-git.git (fetch)
dummy-kao	https://github.com/kaochenlong/dummy-git.git (push)
origin	https://github.com/eddiekao/dummy-git.git (fetch)
origin	https://github.com/eddiekao/dummy-git.git (push)

>第二步：抓取原作專案的內容
接下來，就是使用 Fetch 指令來取得原作專案最新版的內容：

$ git fetch dummy-kao
remote: Counting objects: 4, done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 4 (delta 1), reused 3 (delta 1), pack-reused 1
Unpacking objects: 100% (4/4), done.
From https://github.com/kaochenlong/dummy-git
 * [new branch]      features/mailer      -> dummy-kao/features/mailer
 * [new branch]      features/mailer-plus -> dummy-kao/features/mailer-plus
 * [new branch]      features/mailer_pro  -> dummy-kao/features/mailer_pro
 * [new branch]      features/member      -> dummy-kao/features/member
 * [new branch]      master               -> dummy-kao/master


$ git merge dummy-kao/master
Updating ac341ae..689b015
Fast-forward
 contact.html | 2 ++
 1 file changed, 2 insertions(+)
 

 
> 第三步：推回自己的專案
這個步驟要不要做就看你自己決定了，畢竟在你電腦上已經是最新版本了，如果你希望你在 GitHub 上那個 Fork 的專案也跟到最新版，只要推上去就行了：


$ git push origin master
Counting objects: 4, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (4/4), done.
Writing objects: 100% (4/4), 596 bytes | 596.00 KiB/s, done.
Total 4 (delta 1), reused 0 (delta 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://github.com/eddiekao/dummy-git.git
   ac341ae..689b015  master -> master


> Markdown 區塊引言
> > Markdown 區塊引言

Markdown Setext形式
===================

Markdown Setext形式
-------------------

# 1st Atx形式 !! #

## 2nd Atx形式 !! ##

### 3rd Atx形式 !! ###

#### 4th Atx形式 !! ####

##### 5th Atx形式 !! #####

###### 6th Atx形式 !! ######


<table>
    <tr>
        <td>Foo</td>
    </tr>
</table>

表格
====
  |姓名|性別|年齡|國籍|
  |---|----|----|---|
  |妹子|男|94|日本|
  |漢子|女|87|美國|

強調
====

*single asterisks*

_single underscores_

**double asterisks**

__double underscores__

縮行
====

>文字內容
>>縮行
>>>縮行
>>>>(以此類推)


> ## This is a header.
> 
> 1.   This is the first list item.
> 2.   This is the second list item.

分隔線
======

--------------------------------

Markdown支援有序清單和無序清單
==============================
無序清單使用星號、加號或是減號作為清單標記：

*   Red
*   Green
*   Blue


**待辦事項**
============

- [x] Red 
- [x] Green
- [x] Blue


  |Project Name|Bring up|GPIO|HSIO|Super IO|GOP(VBT)|
  |----|----|----|----|----|----|
  |SOM 2569|Done| | | | |
  |SOM 3569|Done| | | | |
  |SOM 6869|Done| | | | |
  |SOM 7569|Done| | | | |
