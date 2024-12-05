# 项目启动
flutter create .
flutter pub get

# 安装iOS依赖
cd ios
pod install

# 添加iPhone图标
在 pubspec.yaml 中添加：
```yaml
dev_dependencies:
  flutter_launcher_icons: ^0.9.2

flutter_icons:
  ios: true
  image_path: "assets/icon/app_icon.png" # 替换为你的图标路径
```

然后运行：
```bash
flutter pub run flutter_launcher_icons:main
```

最后执行：
```bash
flutter run
# flutter run -d macos
# flutter build ios --release
``` 
