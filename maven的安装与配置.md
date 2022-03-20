# maven的安装与配置

1. maven下载

   - maven[官网下载](https://maven.apache.org)

2. mavne安装（mavne环境变量配置）

   - 双击maven zip包解压

   - 将maven的文件夹移动到 /Library中

   - bash shell

     ```
     vim ~/.bash_profile
     
     export MAVEN_HOME="/Library/apache-maven-3.8.5"
     export PATH="$MAVEN_HOME/bin:$PATH"
     
     source ~/.bash_profile
     
     #验证maven是否配置成功
     mvn -version
     ```

     

   - zsh shell

     ```
     vim ~/.bash_profile
     
     export MAVEN_HOME="/Library/apache-maven-3.8.5"
     export PATH="$MAVEN_HOME/bin:$PATH"
     
     #如果有编辑过zprofile 请执行如下步骤
     source ~/.zprofile
     
     #如果没有编辑过zprofile 请执行如下步骤
     vim ~/.zprofile
     
     [[ -e ~/.profile ]] && emulate sh -c 'source ~/.bash_profile'
     
     source  ~/.zprofile
     
     
     ```

     

3. 配置maven属性

   - 本地仓库

     ```
     #找到maven的文件夹，进入conf文件夹，编辑setting.xml文件
     <localRepository>/Users/cafe/Documents/maven_Repository</localRepository>
     ```

     

   - 远程仓库（配置阿里的远程仓库）

     ```
     <!-- 可以在这配置公司的私服 -->
          <mirror>
     <id>alimaven</id>
     <name>aliyun maven</name>
     <url>http://maven.aliyun.com/nexus/content/groups/public/</url>
     <mirrorOf>central</mirrorOf>
     </mirror>
         <mirror>
     ```

4. 验证配置的两个仓库是否生效

   - 下载一个springboot的项目

   - 解压下载的demo项目

   - 在终端中进入demo文件

     ```
     mvn package
     ```

   - 日志中有阿里云的网站就证明远程仓库配置成功

   - 在进入配置的本地仓库文件夹中，有下载下来的依赖jar包，就证明本地仓库配置成功