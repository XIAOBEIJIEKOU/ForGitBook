### How to use msysGit to opreate GitHub?

> GitHub本身自带有uploadfiles功能，但是不可以上传文件夹，如果你不想你的东西在库里面一览无遗，你不妨看看这篇

---

#### Tips：注意两个Settings：一个是对于单个子库的Settings，一个是对于账户全局的Personal Settings

#### ![](/assets/NNWY_01.png)![](/assets/NNWY_03.png)

#### [**1.注册GitHub并且设置邮箱，下载msysGit工具**](#)

#### [**2.需要将GitHub和msysGit做关联，保证msysGit可以连接到你的GitHub库      **](#)**          **

#### `ssh-keygen -t rsa -C "xxx@xx.com"`

#### ** **![](/assets/NNWY_02.png)

#### **输入后连续要按三个回车，就会在默认的文件夹下生成keys文件。（一般都是在**

#### `C:/users/Administrator/.ssh/`**下有个叫id-rsa.pub的文件），找到**`id-rsa.pub`**文件，将里面的内容复制**

#### ![](/assets/NNWY_04.png)

#### [3.**这样，你可以在本地操作远程的GitHub库了！！！要怎么操作呢？**](#)

#### **当你安装完msysGit之后，点击鼠标右键你会发现，果然多了两个Git Bash Here（命令行）和Git **

#### **GUI Here（图形界面），这个就是你与远程连接的工具在本地选择一个文件夹（随意位置）当做你的本地**

#### **库之后，右击，我比较喜欢Git Bash**

#### ![](/assets/NNWY_05.png)![](/assets/NNWY_06.png)

#### **等待下载 ing.....（注意网速和时段！！！github有些时段特别卡！可能还会下载失败）**

#### ~~趁着 ing 的时候，我来造个句：**就好比你本地的根文件夹就是相当于GitHub总库，然后clone的每一个子**~~

#### ~~**库对应于根文件夹下面的每一个子文件夹**~~

#### 下载完成之后会在本地生成一个子库的文件夹，打开之后里面会有一个.git文件。要注意在这个文件夹下

#### 再打开Git Bash，因为.git文件在这里！！！

#### ![](/assets/NNWY_07.png)

#### 大功告成，这就可以在本地库上进行操作，包括建文件夹，html，txt...

#### 搬砖 ing...

#### [4.翻云覆雨一番之后，要注意将结果git上远程库啊！！！哦都尅？](#)

#### 在字库文件夹下：

![](/assets/gitadd.png)

![](/assets/gitdelete.png)

> #### TIP：这个push是使用git init 然后git pull &lt;url&gt; 的操作，如果是用git clone应该直接push就可以

![](/assets/gitfirstpush.png)

#### `git add xxx xxx.html xxx.txt xxx.xx`

#### git 可以添加多个文件（文件夹，HTML，text）到暂存区，中间用空格隔开

`git rm xxx`

git rm -r xxx

git删除文件和文件夹，中间空格隔开

#### `git commit -m   "description"`

#### description表示的是你本次提交的说明

#### `git push`

#### 将本地的操作全部推到GitHub上

#### ![](/assets/NNWY_08.png)

#### 呼~     GG思密达



