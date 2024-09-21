# Mac设备下的串口通信环境配置及测试
以MiniSTM32(v3)为例，由于bb上提供的工具多基于windows，以下教程用于mac相关环境的配置，可直接用lab1的demo文件进行测试烧录运行
该型号实物图如下：
<img width="902" alt="image" src="https://github.com/user-attachments/assets/19b88c12-c0e9-42c0-959f-33eb947f2b36">
### STM32CubeIDE的安装/参数设置/十六进制文件生成
和lab1课件中的教程完成一致，不做赘述
### 驱动安装
由于lab1中提供的工具包多为针对较低版本的windows系统，使用mac的同学可以去https://www.wch.cn/downloads/CH341SER_MAC_ZIP.html网址下载或直接下载该仓库里的zip包（官网会一直更新），解压后双击CH34xVCPDriver.pkg 按提示安装。注意，也需要全英文路径防止意外错误。
安装完后会有如图软件出现：
<img width="140" alt="image" src="https://github.com/user-attachments/assets/b39b831a-5ac2-4e62-b980-0ffc29befa58">





