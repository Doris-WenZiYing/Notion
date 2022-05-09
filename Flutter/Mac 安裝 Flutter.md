[![hackmd-github-sync-badge](https://hackmd.io/-HOsXE9kRnumvVI5T6AzJw/badge)](https://hackmd.io/-HOsXE9kRnumvVI5T6AzJw)
###### Tags: `Flutter` `Mac`
# **Mac 安裝 Flutter**

1. Flutter 需要 Git 才能安裝，建議安裝 Xcode，安裝 Xcode 時會幫忙安裝 Git
2. 下載 [Flutter SDK](https://flutter.dev/docs/get-started/install/macos) 與 [Android SDK](https://developer.android.com/studio)
3. 設定PATH

    
    >💡添加指令bin到path(environment 環境) 


    - 查看path `echo $PATH`
    
    - 輸入 `export PATH=${PATH}:/home/bin` 可把/home/bin加到path內 (但每次都要打)
    - 放到`~/.bash_profile` or `~/.profile`裡面就能夠被自動執行(我忘記要不要重開之類的或者好像要下`source ~/.bash_profile`, 這裡要注意看你是bash還是zsh)

4. 下 <font color="red">`flutter doctor`</font> 查看缺少什麼, 當下指令<font color="red">`flutter doctor --android-licenses`</font>遇到 : 
    - Exception in thread "main" java.lang.NoClassDefFoundError: 需要檢查Android Studio 的 Tools > SDK Manager > Appearance & Behavior  > System Settings > Android SDK > SDK Tools > Android SDK Command - line tools，接著選擇 Apply 按鈕。
    - 或者遇到ERROR: Error installing cocoapods: ERROR: Failed to build gem native extension, 可以使用 brew 安裝

        ```shell=zsh
        $ brew cleanup -d -v 
        $ brew install cocoapods
        ```


## 參考書：

[前言 | 《Flutter实战》电子书](https://book.flutterchina.club/#%E7%BC%98%E8%B5%B7)