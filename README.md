# 使用 Github Actions 编译 TWRP 恢复模式
```
仅支持 TWRP（twrp-14 仓库尚未准备好）/ 12.1 / 11 / 9.0
```
---
![twrp_jpg](https://s3.bmp.ovh/imgs/2024/10/07/7e8dccdad37f834d.jpg) 
## 发布说明
```
= 2024-10-07
- 修复一些错误
- 优化代码
- 解决与 vendor_boot 相关的问题
- 解决发布问题

= 2024-09-22
- 现在支持 TWRP 14

= 2024-09-05
- 将恢复模式包含在三星设备的 tar 中
- 包含恢复模式安装器 zip
- LDCheck 用于检查缺失的依赖项。
- TWRP 允许非 Github/Gitlab 远程设备树
- 在 README 中澄清选项
- 增加内核内联构建的交换空间大小
- 移除共同树输入字段（不需要）
- 修复 Omni 清单的构建
- 更新至 ubuntu-20.04
- 更新以适配 Android 12.1 AOSP 最小 TWRP 清单
- 完全重构使用逻辑以降低使用难度
- 优化参数传递部分，现在你可以同时运行多个工作器
- TWRP 编译测试通过

```

-----

## 输出将如下所示
![](https://s3.bmp.ovh/imgs/2024/10/07/830c7e6f9f983fac.jpg) 

## 参数说明
| 名称 | 描述 | 示例 |
| ------------ | -------------------- | ------------ |
| `MANIFEST_BRANCH` | 源分支 | twrp-14 |
| `DEVICE_TREE_URL` | 设备树地址 | https://github.com/kinguser981/android_device_samsung_a05s.git  |
| `DEVICE_TREE_BRANCH` | 你想要用于构建的设备分支（通常与清单分支相对应） | android-14 |
| `DEVICE_PATH` | 设备树的位置，相对于工作空间根目录（通常在 BoardConfig.mk 中列为 "LOCAL_PATH" 或 "DEVICE_PATH"） | device/samsung/a05s |
| `DEVICE_NAME` | 型号名称（与设备树中的 twrp_`<DEVICE_NAME>`.mk 相同） | a05s |
| `DEVICE_MAKEFILE` | 来自树的设备特定 makefile 名称（格式：`<PREFIX>_<DEVICE_NAME>`） | twrp_a05s |
| `BUILD_TARGET` | 构建目标分区（boot/recovery/vendor_boot） | recovery |
| `RECOVERY_INSTALLER` | 包含恢复模式安装器 zip | 可选 |
| `RECOVERY_TAR` | 三星设备的恢复模式转为 tar | 可选 |

-----

## 使用说明

#### 1. 点击此仓库右上角的 'Fork'
![](https://s3.bmp.ovh/imgs/2024/09/07/acd37b59bde6971e.png) 
#### 2. 等待自动重定向后，你将看到自己的用户名
## 构建恢复模式
#### 3. 点击 'Actions' 然后点击 'TWRP Recovery Builder 2024'
![](https://s3.bmp.ovh/imgs/2024/09/07/4e0db9b997ea3522.png) 
#### 4. 点击 'Run workflow'，选择你想要构建的恢复模式的分支，并根据上述 '参数说明' 填写
![](https://s3.bmp.ovh/imgs/2024/09/07/29a2d0acf63c6e4f.png) 
#### 5. 填写完毕后，点击 'Run workflow' 开始运行

-----

## 编译结果
可在 [Release](../../releases) 下载

-----
## 参考和致谢
- https://github.com/that1 
- https://github.com/TeamWin 
- https://github.com/cd-Crypton 
- https://github.com/azwhikaru 
- 以及我在所有仓库和脚本中使用的所有贡献者。
