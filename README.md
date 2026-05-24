# My-SRE-Journey
Recording my 24-month journey to becoming an SRE.
The core principle of the Linux system is that everything is a file.

**Feynman Explanations**: Linux treats everything as a file, just like a secretary organizing all kinds of office documents in a unified way.

**费曼式讲解**：Linux 把所有事物都视作文件，就像秘书用统一逻辑整理各类办公文件一样.

## Phase 1 / 第一阶段：Linux基础入门
### Command Line Practice / 命令行练习
- 2026-05-05: Practiced `cd`, `ls -al`, `pwd`,`man` ,`clear`commands
- 2026-05-05: 练习了cd切换目录、ls查看文件等基础命令，理解了相对路径和绝对路径的区别


**Feynman Explanations**: The absolute path from pwd is like your mailing address. cd ..is like taking stairs down, and plaincd is like hitting the elevator's home button. 

**费曼式讲解**:pwd的绝对路径,就像你的通信地址.  cd..就像在走楼梯,只能一层一层走.cd就像走电梯直达.


- 2026-05-07: Practiced `cd -`, `ls -ltrh`, `mkdir -p`,`man -k` ,``pwd`,`man -k directory``commands
- 2026-05-07: 练习了`cd -`, `ls -ltrh`, `mkdir -p`,`man -k` ,``pwd`,`man -k directory``命令,
- **费曼式讲解**:`ls -al`命令让我看到文件的前面'rwxr-xr-x'的字符对权限的描述,正如我理解的洋葱安全模型一样.`mkdir -p`递归创建多级目录、一键穿梭真的神奇.cd -完美解决了我来回切目录的麻烦，练得意犹未尽。
  
**Feynman Explanations**:The 9-character permission string split into 3 groups aligns perfectly with my understanding of the'security onion' model for access control.The recursive magic of mkdir -p just solved my directory-building headache.


- 2026-05-08: Practiced `mkdir -p`, `touch`, `cp -r`,`mv` ,`rm -i` commands
- 2026-05-08: 练习了`mkdir -p`, `touch`, `cp -r`,`mv` ,`rm -i` 命令


**Troubleshooting Lab**:When I used the`cp -r`command, I should only write the source folder name and the target path.But I added a slash and wrote an absolute path by mistake.It caused an error, and the terminal showed permission denied.

**纠错实验室**:我用 cp -r 命令的时候搞砸了两件事,一是我本该复制整个 project 文件夹，却给它指了单个文件(是由于我的把简单问题复杂化)；二是我用了绝对路径把文件发到了我不想去的地方，没老老实实在当前目录操作.


**Feynman Explanations**:The `mv` command does two jobs: it moves files to a different path, or renames them in the same folder.
The `rm -i`option is really interesting. It’s like ordering a steak in a restaurant. The waiter asks you step by step: which kind of steak you want, how well-done you like it, and what sauce you prefer. Every single step asks for my confirmation before deleting anything. This keeps me from deleting files by accident.

**费曼式讲解**:`mv`身肩两职啊。当目标路径是不同的时候，它就是移动了。当目标路径是相同的时候，它原来就是改个名字。`rm -i`它就像我点了一份菜一样，这个服务员会站在这旁边。比如例如我点了一份牛排，他他会问我，您要的是菲力牛排还是其他的什么牛排？然后还会问我是几分熟，是三分熟、五分熟还是七分熟？然后会会问问我是要加胡椒酱，是要加胡椒酱还是要加什么其他的酱？


- 2026-05-14: Practiced:I try out the Linux commands I’ve learned before, complete simple tasks and simulate real scenarios. It makes me feel fully involved.
- 2026-05-14: 练习:我在尝试用前面学习到的命令,完成一些简单的任务.模拟真实的场景,这让我很有代入感.

**Troubleshooting Lab**:I forgot the command to go back to the upper folder. Isn’t it `cd..`? What is it actually? I feel a bit silly.

When creating the backup folder, I typed the wrong characters and created some "ghost files". In a real working environment, troubleshooting such mistakes would waste a lot of time. I have to type every character carefully. Maybe I’m just not familiar enough with the keyboard and can’t touch-type accurately yet.

I keep making the same mistake: there must be a space between a command and its parameters. This stops me from finishing tasks correctly and makes me doubt myself.
To go back to the parent directory, it has to be `cd ..` with a space in between.
I can create two folders at the same path using Brace Expansion {}.

When moving a file and renaming it at the same time, we can use this format:  
`mv source_file target_folder/new_name`.  
Since it’s my first time trying this, I didn’t know such a convenient way existed.  
This isn’t really a mistake; it’s just a new knowledge point for me.  
I feel I’ve gained a lot from learning it.

It turns out that `ls folder1 folder2` can list and view the files inside two folders at the same time.

**纠错实验室**:我忘记了,怎样返回上级文件夹的命令,不是`cd..`?应该是什么呢,我感到自己的愚笨.在创建backup文件夹时,我敲错了字符,制造了“幽灵文件”我想在真实的环境中那将要耗费大量的时间来排查错误,我得认真敲对每一个字符,可能真的是我对键盘不够熟悉,没法正确的盲打.
我犯了同一个错误,命令和参数之间需空格,导致我不能正确完成任务,产生自我怀疑.返回上级目录,`cd..`后面要加空格.
原来在同一路径文件夹下再次创建两个文件夹,可以使用布氏扩展（Brace Expansion {}）.
移动文件并同时重命名操作时,`mv 被操作文件 目标文件夹/新名称`因我第一次操作,不了解可以这样便捷,所以这不算是一个错误,而是我的知识点.我感到很有收获.
原来`ls 文件夹1 文件夹2`可以同时列表查看两个文件夹下的文件.


- 2026-05-17: Practiced:Real-scenario practice replaces boring rote command memorization. I solve real production issues step by step: run codes, fix errors, rethink, adjust and make them work. Such hands-on practice brings quick understanding and long-lasting memory. Commands like ls -lh and rm -ir are deeply engraved in my mind, and this interactive mode feels just like chatting with Linux.


- 2026-05-17: 练习了:模拟真实场景,打破了按照字典背诵命令的枯燥方式,而是把生产线上的实际需要问题让我来解决,我通过执行-报错-思考-校准-跑通,代入式的练习让我快速理解,记忆犹新.前面提到的所有命令,`ls -lh`,`rm -ir`的命令让我印象深刻,这种交互式的感觉,让我觉得能和linux对话.

  
**Troubleshooting Lab**:I can now understand the simple error messages from the previous command exercises and figure out the reasons behind them.I'll try the Tab key for command completion.

**纠错实验室**:前面命令练习提到的简单报错,我能读懂了,并且我能思考为什么.由于我之前把简单的路径复杂化,输入出错,我要尝试用tab键,补全命令.

**Growth Mindset**:Perhaps I have an extremely sharp sense of security, so I remember clearly the `-i` parameter used with the `rm` command. I compare `mkdir -p` to Russian nesting dolls, and I can make as many nested layers as I want, haha.
I'm going to try using the Tab key to autocomplete commands.



- 2026-05-19: Practiced:`cat`, `tail -f`, `grep -color`,`head -n` ,`echo >>` commands
- 2026-05-19: 练习了:cat`, `tail -f`, `grep -color`,`head -n` ,`echo >>` 命令.
  
**Growth Mindset**:I think the line break layout that the echo command uses for newly added content is very logical and fits common thinking habits.
Perhaps I possess a stronger awareness of potential security risks than most people. I explicitly refuse to write commands and parameters in space-free shorthand. It is not only visually messy, but also highly prone to misjudgment once additional parameters are added.
I use Tab to complete command parameters now; it’s super efficient.


- 2026-05-21: Practiced: `tail -n`, `grep -color -E`,`head -n` ,`echo >>` `wc -l`commands
- 2026-05-21: 练习了:`tail -n`, `grep -color -E`,`head -n` ,`echo >>` `wc -l`命令


**Troubleshooting Lab**:
1. When matching multiple keywords with grep, I used "&" instead of "|" and left out the "-E" parameter, leading to command failure.
2. I did not use tail -n to set the data range before filtering keywords and counting lines with wc -l. Lacking valid conditions confused the Linux system and stopped the execution.
**纠错实验室**:1.我在grep命令同时显示多个关键字时,使用了"&'而不是"|",我漏掉了"-E"参数,导致命令失败.2.我在grep命令显示多个关键字,并wc -l统计的时候,没有首先tail -n列出范围,导致系统肯定无法识别.等于没给条件,却让linux手足无措.


**Growth Mindset**:Mistakes teach more than being right. Correctness feels good, but mistakes make you reflect. Today, typos and wrong spaces taught me pipe rules and wc tricks—these lessons stick better than one success.Tail sets the range, grep points out the focus, and wc counts them.Long pipeline commands with tail, grep, and wc caused many errors. Instead of using them to "show off" or making them too long— which makes troubleshooting overwhelming—simplify into short, single-step commands. This way, when checking for mistakes, you can focus more clearly and specifically on each error.Staring at the terminal, I compared commands and gradually realized where I went wrong.



- 2026-05-24: Reviewed: `tail -n`, `grep -color -E`,`echo >>` commands
- 2026-05-24: 复习了:`tail -n`, `grep -color -E`,`echo >>` 命令

**Troubleshooting Lab**:When using the -E parameter of the grep command, the correct format is "A|B", while I wrote "A" | "B" by mistake.Today I managed to link tail and grep via pipe operator, and ran the combined command accurately.
**纠错实验室**:grep 用 - E 做多关键词或匹配时，所有关键词和分隔符.grep用-E参数,应该是"A|B",而我写成"A" | "B",



### Permission & Security / 权限与安全
- 2026-05-06:
- **Feynman Explanations**: Learned that Linux permission model is like an onion.Linux system is like a big house.
The Desktop is just like the surface of my office desk.Documents serve as boxes for storing office files.
Pictures are similar to a photo wall.Downloads acts as a mailbox at home to receive letters and packages.
-**费曼式讲解**:理解了Linux权限的洋葱模型，一切皆文件的核心逻辑.Linux系统就像一栋大房子，Desktop如同办公桌台面，Documents是存放办公资料的文件盒，Pictures好比照片墙，Downloads则相当于家里的信箱，用来接收信件和各类快递文件。


