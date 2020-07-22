# Mac OS 系统重装笔记

## 重装系统

抹掉磁盘还得先取消激活锁，不然打不开恢复模式

### 关闭激活锁

激活锁是 macOS Catalina 10.15 或更高版本的一项功能。在使用 macOS 恢复功能完成后，请按照以下步骤关闭激活锁。

1. 选取 Apple 菜单  >“系统偏好设置”。
2. 点按“Apple ID”。
3. 点按边栏中的“iCloud”。
4. 取消选中右侧的“查找我的 Mac”复选框，然后在出现提示时输入您的 Apple ID 密码。



### 通过 macOS 恢复功能启动

要通过 macOS 恢复功能启动，请将 Mac 开机，然后立即按住键盘上的以下组合键之一。当您看到 Apple 标志、旋转的地球或[其他启动屏幕](https://support.apple.com/zh-cn/HT204156)时，请松开这些按键。

- Command (⌘)-R

  重新安装您在 Mac 上安装过的最新 macOS（建议操作）。

- Option-⌘-R

  升级到与您的 Mac 兼容的最新 macOS。

- Shift-Option-⌘-R

  重新安装 Mac 随附的 macOS 或与它最接近且仍在提供的版本。

### 抹掉磁盘

1. 从 macOS 恢复功能启动。然后从“实用工具”窗口中选择“磁盘工具”，并点按“继续”。
   如果您抹掉的不是 Mac 启动时使用的磁盘，则无需从 macOS 恢复功能启动：只需从“应用程序”文件夹的“实用工具”文件夹中打开“磁盘工具”。 
   ![恢复功能中的“macOS 实用工具”窗口](https://support.apple.com/library/content/dam/edam/applecare/images/zh_CN/macos/Catalina/macos-catalina-recovery-mode-utilities-disk-utility.jpg)
2. 从“磁盘工具”的菜单栏中选取“显示”>“显示所有设备”。边栏随即会显示磁盘（设备）以及其中的所有容器和宗卷。Mac 启动时使用的磁盘列在列表顶部。在这个示例中，Apple SSD 是启动磁盘：
   ![在“磁盘工具”中抹掉磁盘并选取方案](https://support.apple.com/library/content/dam/edam/applecare/images/zh_CN/macos/Catalina/macos-catalina-disk-utility-erase-internal-drive.jpg)
3. 选择要抹掉的磁盘。
4. 点按“抹掉”，然后填写以下各项：
   - *名称：*键入您希望磁盘在被抹掉后使用的名称。
   - *格式：*选取“APFS”或“Mac OS 扩展（日志式）”。默认情况下，“磁盘工具”会显示兼容的格式。
   - *方案*：选取“GUID 分区图”。
5. 点按“抹掉”，以开始抹掉磁盘以及其中的每个容器和宗卷。系统可能会要求您输入您的 Apple ID。
6. 完成后，退出“磁盘工具”。
7. 如果您希望 Mac 能够从您抹掉的磁盘启动，则可以在这个磁盘上重新安装 macOS。



## 软件安装

### 搜狗输入法

皮肤名称：**清雅**

### chrome

### ClashX

[link](https://dl.trojan-cdn.com/trojan/macos/)

### pulse

### lemon

### pdfguru

### Rectangle

软件分屏

### IINA

好用的视频播放器

### 超级右键

增加finder中右键的功能

### Mounty

挂载软件，解决硬盘与mac os不兼容

### Scroll reverse

解决鼠标滚轮和触控板滑动方向不同的问题

### sublime

`tool`-`install package controller`

在`/.zshrc`中添加

```
alias subl="/Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl"
```

### Homebrew

正常安装报错

```
curl: (7) Failed to connect to raw.githubusercontent.com port 443
```

解决办法

通过修改`hosts`解决此问题。

**查询真实IP**

在https://www.ipaddress.com/查询raw.githubusercontent.com的真实IP。

[![up-730db80898b3bb975647e99575be12ef87a.p](https://oscimg.oschina.net/oscnet/up-730db80898b3bb975647e99575be12ef87a.png)](https://oscimg.oschina.net/oscnet/up-730db80898b3bb975647e99575be12ef87a.png)

**修改hosts**

```
sudo vim /etc/hosts
```

添加如下内容：

```
199.232.28.133 raw.githubusercontent.com
```

### Iterm+zsh+oh my zsh

去官网下载[Iterm](https://www.iterm2.com/index.html)

更新`zsh`

```
brew install zsh
```

将zsh设置为默认shell

```
chsh -s /bin/zsh
```

安装Oh my zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

安装Powerline fonts

```
# clone
git clone https://github.com/powerline/fonts.git --depth=1
# install
cd fonts
./install.sh
# clean-up a bit
cd ..
rm -rf fonts
```

在Iterm的`Preference-profile`中的`Colors`中设置配色为`Solarized Dark`，在`Text`中将字体设置为`Melso powerline`

修改zsh主题，`vim ~/.zshrc`后，将主题部分改为`ZSH_THEME="agnoster"`

自动补全插件

```shell
git clone git://github.com/zsh-users/zsh-autosuggestions $ZSH_CUSTOM/plugins/zsh-autosuggestions

```

高亮插件

```shell
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```

编辑.zshrc文件如下

```text
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)
```

修改vim配置

```shell
git clone --depth=1 https://github.com/amix/vimrc.git ~/.vim_runtime
~/.vim_runtime/install_basic_vimrc.sh
```

`progiles-sessions`中的`Status bar enabled`可以增加头部的状态栏

<img src="/Users/fool/Library/Application Support/typora-user-images/image-20200722194308962.png" alt="image-20200722194308962" style="zoom:50%;" />

