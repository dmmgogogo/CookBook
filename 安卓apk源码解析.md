# ADB Shell PM Path 故障排查指南

## 问题检查步骤

### 1. 确认设备已授权并正常连接

运行以下命令检查设备状态：

```bash
adb devices
```

输出应包含设备序列号，并显示 device 状态。如果显示 unauthorized，请在手机上点击授权。

### 2. 确认包名是否正确

运行以下命令检查应用是否安装，确保包名无误：

```bash
adb shell pm list packages | grep athome
```

如果输出为：
```
package:jp.co.athome
```
说明包名是正确的。

### 3. 更正命令格式

运行以下命令获取 APK 路径：

```bash
adb shell pm path jp.co.athome
```

**注意：** 不要在包名前加 package: 前缀。

### 4. 检查权限

如果设备未 Root 或系统限制访问某些路径，可能需要更高权限。尝试以下命令：

```bash
adb root
adb shell pm path jp.co.athome
```

如果设备不支持 adb root，可能需要手动查找路径。

## 执行结果

已正确执行命令：
```bash
adb shell pm path jp.co.athome
```

输出结果为：
```
package:/data/app/~~uXSYI42jBrTneinjaBG-7A==/jp.co.athome-Y_iHWf7FksLb78Jjdf_7Tw==/base.apk
```

这表示 jp.co.athome 应用的 APK 文件路径是：
```
/data/app/~~uXSYI42jBrTneinjaBG-7A==/jp.co.athome-Y_iHWf7FksLb78Jjdf_7Tw==/base.apk
```

## 后续操作

### 1. 将 APK 文件提取到本地

使用 adb pull 命令提取 APK 文件：

```bash
adb pull /data/app/~~uXSYI42jBrTneinjaBG-7A==/jp.co.athome-Y_iHWf7FksLb78Jjdf_7Tw==/base.apk .
```

这会将文件保存到当前工作目录下。

### 2. 检查提取结果

确保文件已成功下载，可以通过 ls 或 Finder 验证。

### 3. 解包或反编译 APK（可选）

使用 apktool 或其他工具解包 APK，以便查看资源或代码：

```bash
apktool d base.apk -o jp.co.athome_source
```

或者用 jadx 查看代码：

```bash
jadx-gui base.apk
```

示例（jadx 用法）：
```bash
jadx jp.co.recruit.android.suumo.source
```
