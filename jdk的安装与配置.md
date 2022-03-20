# jdk的安装与配置

1. jdk的版本选择

   - jdk8 ✅
   - jdk11
   - jdk17

2. jdk安装包的下载

   - jdk[官网](https://www.oracle.com/java/technologies/javase/javase8-archive-downloads.html)
     - 😊 官网值得信任
     - 😒 下载需要账号
     - 😒 没有M芯片可用的ARM版本的jdk
     - 😒 官网jdk安装包在安装之后需要手动配置环境变量
   - [azul](https://www.azul.com/downloads/)
     - 😒 网站打开比较慢
     - 😊 下载不需要账号
     - 😊 有M芯片可用的ARM版本的jdk
     - 😊 安装包在安装之后需要手动配置环境变量

3. jdk的安装

   - jdk安装比较简单，下一步下一步安装就可以了

4. 环境变量配置

   - 如果是安装的azul下载的安装包可用不用手动配置环境变量
   - 如果是安装的官网的jdk就需要配置环境变量

   1. 确认安装之后jdk文件所在的路径

      ```
      /Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home
      ```

   2. 确认macos所使用的shell

      - bash

        ```
        -bash: kkkk: command not found
        
        vim ~/.bash_profile
        
        export JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home"
        export PATH="$JAVA_HOME/bin:$PATH"
        
        source ~/.bash_profile
        ```

        

      - zsh

        ```
        -zsh: kkkk: command not found
        
        vim ~/.bash_profile
        
        export JAVA_HOME="/Library/Java/JavaVirtualMachines/jdk1.8.0_202.jdk/Contents/Home"
        export PATH="$JAVA_HOME/bin:$PATH"
        
        vim ~/.zprofile
        
        [[ -e ~/.profile ]] && emulate sh -c 'source ~/.bash_profile'
        
        source  ~/.zprofile
        
        ```

        

   