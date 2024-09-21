# Mac设备下的串口通信环境配置及测试
以MiniSTM32(v3)为例，由于bb上提供的工具多基于windows，以下教程用于mac相关环境的配置，可直接用lab1的demo文件进行测试烧录运行。
该型号实物图如下：
<img width="902" alt="image" src="https://github.com/user-attachments/assets/19b88c12-c0e9-42c0-959f-33eb947f2b36">
## STM32CubeIDE的安装/参数设置/十六进制文件生成
和lab1课件中的教程完成一致，不做赘述
## 硬件
需要先买一个转接口，Mac初始的各种插口不太适配
## 驱动
### 安装
由于lab1中提供的工具包多为针对较低版本的windows系统，使用Mac的同学可以去[官网](https://www.wch.cn/downloads/CH341SER_MAC_ZIP.html)下载或直接下载该仓库里的zip包（官网会一直更新），解压后双击CH34xVCPDriver.pkg 按提示安装。注意，也需要全英文路径防止意外错误。

安装完后会有如图软件出现：

<img width="140" alt="image" src="https://github.com/user-attachments/assets/b39b831a-5ac2-4e62-b980-0ffc29befa58">

### 测试是否成功安装
将线接好，打开V3电源开关，在终端输入
```bash
ls /dev/cu.*
```
如果显示出类似类似 cu.wchusbserial... 的设备名称，说明驱动已安装成功：
```bash
sakn@SAKNdeMacBook-Pro ~ % ls /dev/cu.*
/dev/cu.Bluetooth-Incoming-Port	/dev/cu.wchusbserial11330
/dev/cu.usbserial-11330		/dev/cu.wlan-debug
```
## 串口通信工具
### 安装
我使用的是免费的和官方衔接的最新版STM32CubeProgrammer（包太大就不放在库里了，官网安装需要的账号和安装STM IDE的是同一账号），官网安装链接如下：
[STM32CubeProgrammer 下载链接](https://www.st.com/en/development-tools/stm32cubeprog.html)

解压后一路点默认到安装成功，如果安装时没注意路径无法找到它在哪里，可以
按 Command + Space 打开 Spotlight 搜索，在搜索框中输入STM32CubeProgrammer进行寻找

<img width="588" alt="image" src="https://github.com/user-attachments/assets/da126641-380e-4991-9c87-d4f3e1969cbb">

### 使用
详细教程在csdn上有，链接如下：
https://blog.csdn.net/weixin_62292999/article/details/140446389

注意，实际测试中发现有一些和lab课件中的操作区别：

##### 1.下图中均需设置为low，否则点击connect会无法连接

<img width="245" alt="image" src="https://github.com/user-attachments/assets/f1938838-0ccf-426d-a631-37b57d439081">


##### 2.port选择里的名称有变化，类似下图
<img width="1198" alt="image" src="https://github.com/user-attachments/assets/1dab0768-2dc2-4a4f-81e1-5a879199d938">


##### 3.准备写入时需要将BOOT0接入V3.3电位（如图），然后按复位键，点connect，start programming，弹出成功烧录窗口后断开连接（成功烧录后可能会在控制台连续报错并自动断开连接，不用管它，可能是因为烧录完成后不是串口通信模式了）。然后将BOOT0复原到GND，点击reset，程序正常运行。

<img width="229" alt="image" src="https://github.com/user-attachments/assets/7ec21e93-55d6-4e65-b181-6a174b3a4aff">

##### 4.如果想要清除之前其他方式烧录的结果以此检验是否通过串口烧录成功，可以在成功连接后先按下图中的full chip erase按键将烧录结果清零，再进行重新烧录。
<img width="356" alt="image" src="https://github.com/user-attachments/assets/4b33d5cf-6b5d-4d8d-b526-dc68d12a6aaf">













