# 烧录

> ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
> - 如您使用的是master分支2022年5月9日及之后的源码，请使用HiTool工具进行烧录。
> - 当前版本的DevEco Device Tool暂不支持上述日期后的源码烧录，将在下个版本中适配。

在Windows下采用USB烧录方式进行Hi3516DV300的烧录。


1. 请连接好电脑和待烧录开发板，需要同时连接串口和USB口，具体可参考[Hi3516DV300开发板介绍](https://gitee.com/openharmony/docs/blob/master/zh-cn/device-dev/quick-start/quickstart-lite-introduction-hi3516.md)。

2. 根据[Hi3516DV300/Hi3518EV300开发板串口驱动安装指导](https://device.harmonyos.com/cn/docs/documentation/guide/hi3516_hi3518-drivers-0000001050743695)安装USB转串口的驱动程序。若您的设备中已安装此驱动，请忽略该步骤。

3. 在DevEco Device Tool中，选择REMOTE DEVELOPMENT &gt; Local PC，查看远程计算机（Ubuntu开发环境）与本地计算机（Windows开发环境）的连接状态。

   - 如果Local PC右边连接按钮为![zh-cn_image_0000001261315939](figures/zh-cn_image_0000001261315939.png)，则远程计算机与本地计算机为已连接状态，不需要执行其他操作。
   - 如果Local PC右边连接按钮为![zh-cn_image_0000001261515989](figures/zh-cn_image_0000001261515989.png)，则点击绿色连接进行按钮。

   ![zh-cn_image_0000001261395999](figures/zh-cn_image_0000001261395999.png)

   > ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
   > 该操作仅在远程模式（Windows+Ubuntu混合开发环境）中需要设置，如果采用本地模式（Windows开发环境或Ubuntu开发环境），则请跳过该步骤。

4. 在DevEco Device Tool中，点击QUICK ACCESS &gt; DevEco Home &gt; Device，查看并记录对应的串口号。

   ![zh-cn_image_0000001216516128](figures/zh-cn_image_0000001216516128.png)

5. 在QUICK ACCESS &gt; DevEco Home &gt; Projects中，点击**Settings**打开工程配置界面。

   ![zh-cn_image_0000001198566364](figures/zh-cn_image_0000001198566364.png)

6. 在“hi3516dv300”页签，设置烧录选项，包括upload_partitions、upload_port和upload_protocol。

   - upload_partitions：选择待烧录的文件，默认情况下会同时烧录fastboot、kernel、rootfs和userfs。
   - upload_port：选择已查询到的串口号。
   - upload_protocol：选择烧录协议，固定选择“hiburn-usb”。

   ![zh-cn_image_0000001223190441](figures/zh-cn_image_0000001223190441.png)

7. 分别检查待烧录文件的烧录信息，DevEco Device Tool已预置默认的烧录文件信息，可根据实际情况进行调整。待烧录文件包括：fastboot、kernel、rootfs和userfs。

   1. 在“hi3516dv300_fastboot”页签，在New Option选项中选择需要修改的项，例如partition_bin（烧录文件路径）、partition_addr（烧录文件起始地址）、partition_length（烧录文件分区长度）等。

       ![zh-cn_image_0000001198889702](figures/zh-cn_image_0000001198889702.png)

   2. 然后在Partition Options中，分别修改上述步骤中选择的修改项。

       > ![icon-note.gif](public_sys-resources/icon-note.gif) **说明：**
       > 在设置烧录分区起始地址和分区长度时，应根据实际待烧录文件的大小进行设置，要求设置的烧录分区大小，要大于待烧录文件的大小；同时，各烧录文件的分区地址设置不能出现重叠。

       ![zh-cn_image_0000001243290907](figures/zh-cn_image_0000001243290907.png)

   3. 按照相同的方法修改kernel、rootfs和userfs的烧录文件信息。

8. 所有的配置都修改完成后，在工程配置页签的顶部，点击**Save**进行保存。

9. 点击hi3516dv300下的**Upload**按钮，启动烧录。

   ![zh-cn_image_0000001267231481](figures/zh-cn_image_0000001267231481.png)

10. 在终端窗口显示如下提示信息时，按住复位键，插拔USB线，最后松开复位键启动烧录。

    ![zh-cn_image_0000001114129426](figures/zh-cn_image_0000001114129426.png)

    启动烧录后，界面提示如下信息时，表示烧录成功。

    ![zh-cn_image_0000001160649343](figures/zh-cn_image_0000001160649343.png)

11. 烧录成功后，请根据[运行](quickstart-ide-standard-running-hi3516-running.md)章节进行操作，启动系统。
