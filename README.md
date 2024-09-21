# Mac设备下的串口通信环境配置及测试
以MiniSTM32(v3)为例，由于bb上提供的工具多基于windows，以下教程用于mac相关环境的配置，可直接用lab1的demo文件进行测试烧录运行
该型号实物图如下：
<img width="902" alt="image" src="https://github.com/user-attachments/assets/19b88c12-c0e9-42c0-959f-33eb947f2b36">
### STM32CubeIDE的安装/参数设置/十六进制文件生成
和lab1课件中的教程完成一致，不做赘述
### 驱动
#### 安装
由于lab1中提供的工具包多为针对较低版本的windows系统，使用mac的同学可以去https://www.wch.cn/downloads/CH341SER_MAC_ZIP.html网址下载或直接下载该仓库里的zip包（官网会一直更新），解压后双击CH34xVCPDriver.pkg 按提示安装。注意，也需要全英文路径防止意外错误。
安装完后会有如图软件出现：
<img width="140" alt="image" src="https://github.com/user-attachments/assets/b39b831a-5ac2-4e62-b980-0ffc29befa58">
#### 测试是否成功安装
将线接好，打开V3电源开关，在终端输入ls /dev/cu.*
如果显示出类似类似 cu.wchusbserial... 的设备名称，说明驱动已安装成功：
sakn@SAKNdeMacBook-Pro ~ % ls /dev/cu.*
/dev/cu.Bluetooth-Incoming-Port	/dev/cu.wchusbserial11330
/dev/cu.usbserial-11330		/dev/cu.wlan-debug
### 串口通信工具
我使用的是免费的和官方衔接的最新版STM32CubeProgrammer（包太大就不放在库里了，官网安装需要的账号和安装STM IDE的是同一账号），官网安装链接如下：
https://www.st.com/en/development-tools/stm32cubeprog.html
解压后一路点默认到安装成功，如果安装时没注意路径无法找到它在哪里，可以
按 Command + Space 打开 Spotlight 搜索，在搜索框中输入STM32CubeProgrammer进行寻找
<img width="588" alt="image" src="https://github.com/user-attachments/assets/da126641-380e-4991-9c87-d4f3e1969cbb">








