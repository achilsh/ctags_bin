# ctags_bin
===========================
要点说明:
----------------
- **`ctags 文件安装`**
     直接将二进制文件替换到 .vimrc配置文件中指定的路径


- **`vimff作为svn diff的查看代码的工具**
    编写脚本diffwrap.sh
    ```bash
    #!/bin/sh
    #过滤掉svn diff的前五个命令行参数
    shift 5
    #使用vimdiff比较文件
    vimdiff "$@"
    ```

    在svn的配置文件，一般为~/.subversion/config文件，找到配置行diff-cmd,修改为如下
    ```
    diff-cmd=/usr/local/bin/diffwrap.sh
    ```

