# subsystems

- 编译构建
    - [轻量和小型系统编译构建指导](subsys-build-mini-lite.md)
    - [标准系统编译构建指导](subsys-build-standard-large.md)
    - [构建系统编码规范与最佳实践](subsys-build-gn-coding-style-and-best-practice.md)
    - [编译构建Kconfig可视化配置指导](subsys-build-gn-kconfig-visual-config-guide.md)
- [分布式远程启动](subsys-remote-start.md)
- 图形图像
    - [图形图像概述](subsys-graphics-overview.md)
    - [容器类组件开发指导](subsys-graphics-container-guide.md)
    - [布局容器类组件开发指导](subsys-graphics-layout-guide.md)
    - [普通组件开发指导](subsys-graphics-common-guide.md)
    - [动画开发指导](subsys-graphics-animation-guide.md)
- 媒体
    - 相机
        - [相机开发概述](subsys-multimedia-camera-overview.md)
        - [拍照开发指导](subsys-multimedia-camera-photo-guide.md)
        - [录像开发指导](subsys-multimedia-camera-record-guide.md)
        - [预览开发指导](subsys-multimedia-camera-preview-guide.md)
    - 音视频
        - [音视频开发概述](subsys-multimedia-video-overview.md)
        - [音视频播放开发指导](subsys-multimedia-video-play-guide.md)
        - [音视频录制开发指导](subsys-multimedia-video-record-guide.md)
- 公共基础
    - [公共基础库概述](subsys-utils-overview.md)
    - [公共基础库开发指导](subsys-utils-guide.md)
    - [公共基础库常见问题](subsys-utils-faqs.md)
- AI框架
    - [概述](subsys-aiframework-guide.md)
    - [搭建环境](subsys-aiframework-envbuild.md)
    - 技术规范
        - [代码管理规范](subsys-aiframework-tech-codemanage.md)
        - [命名规范](subsys-aiframework-tech-name.md)
        - [接口开发规范](subsys-aiframework-tech-interface.md)
    - 开发指导
        - [SDK开发过程](subsys-aiframework-devguide-sdk.md)
        - [插件的开发过程](subsys-aiframework-devguide-plugin.md)
        - [配置文件的开发过程](subsys-aiframework-devguide-conf.md)
    - 开发示例
        - [唤醒词识别SDK的开发示例](subsys-aiframework-demo-sdk.md)
        - [唤醒词识别插件的开发示例](subsys-aiframework-demo-plugin.md)
        - [唤醒词识别配置文件的开发示例](subsys-aiframework-demo-conf.md)
- 数据管理
    - 关系型数据库
      - [关系型数据库概述](subsys-data-relational-database-overview.md)
      - [关系型数据库开发指导](subsys-data-relational-database-guide.md)
    - 轻量级数据存储
      - [轻量级数据存储概述](subsys-data-storage-overview.md)
      - [轻量级数据存储开发指导](subsys-data-storage-guide.md)
- Sensor服务
    - [Sensor服务概述](subsys-sensor-overview.md)
    - [Sensor服务使用指导](subsys-sensor-guide.md)
    - [Sensor服务使用实例](subsys-sensor-demo.md)
- USB服务
    - [USB服务概述](subsys-usbservice-overview.md)
    - [USB服务使用指导](subsys-usbservice-guide.md)
    - [USB服务使用实例](subsys-usbservice-demo.md)
- 用户程序框架
    - [概述](subsys-application-framework-overview.md)
    - [搭建环境](subsys-application-framework-envbuild.md)
    - [开发指导](subsys-application-framework-guide.md)
    - [开发实例](subsys-application-framework-demo.md)
- [OTA升级](subsys-ota-guide.md)
- 电话服务
    - [电话服务概述](subsys-tel-overview.md)
    - [电话服务开发指导](subsys-tel-guide.md)
- 安全
    - [概述](subsys-security-overview.md)
    - [应用验签开发指导](subsys-security-sigverify.md)
    - [应用权限管理开发指导](subsys-security-rightmanagement.md)
    - [IPC通信鉴权开发指导](subsys-security-communicationverify.md)
    - [设备安全等级管理开发指南](subsys-security-devicesecuritylevel.md)
- 启动恢复
    - [启动恢复子系统概述](subsys-boot-overview.md)
    - [init启动引导组件](subsys-boot-init.md)
    - [appspawn应用孵化组件](subsys-boot-appspawn.md)
    - [appspawn标准系统应用孵化组件](subsys-boot-appspawn-standard.md)
    - [bootstrap服务启动组件](subsys-boot-bootstrap.md)
    - [syspara系统属性组件](subsys-boot-syspara.md)
    - [常见问题](subsys-boot-faqs.md)
    - [参考](subsys-boot-ref.md)
- [测试用例开发指导](subsys-testguide-test.md)
- DFX
    - [DFX概述](subsys-dfx-overview.md)
    - [HiLog开发指导](subsys-dfx-hilog-rich.md)
    - [HiLog_Lite开发指导](subsys-dfx-hilog-lite.md)
    - [HiTrace开发指导](subsys-dfx-hitrace.md)
    - [HiCollie开发指导](subsys-dfx-hicollie.md)
    - HiSysEvent开发指导
        - [HiSysEvent打点配置指导](subsys-dfx-hisysevent-logging-config.md)
        - [HiSysEvent打点指导](subsys-dfx-hisysevent-logging.md)
        - [HiSysEvent订阅指导](subsys-dfx-hisysevent-listening.md)
        - [HiSysEvent查询指导](subsys-dfx-hisysevent-query.md)
        - [HiSysEvent工具使用指导](subsys-dfx-hisysevent-tool.md)
    - [HiDumper开发指导](subsys-dfx-hidumper.md)
    - [HiChecker开发指导](subsys-dfx-hichecker.md)
    - [Faultlogger开发指导](subsys-dfx-faultlogger.md)
- 调测工具
    - [bytrace使用指导](subsys-toolchain-bytrace-guide.md)
    - [hdc_std使用指导](subsys-toolchain-hdc-guide.md)
    - [hiperf使用指导](subsys-toolchain-hiperf.md)
- [XTS测试用例开发指导](subsys-xts-guide.md)