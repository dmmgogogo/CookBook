```

lib/
├── api/                 # API 请求相关
├── config/             # 配置文件
├── models/            # 数据模型
├── pages/             # 页面文件
├── providers/         # 状态管理
├── routes/            # 路由配置
├── utils/             # 工具类
├── widgets/           # 自定义组件
└── main.dart          # 入口文件

```

```
具体说明：

api/ 目录


存放所有网络请求相关代码
通常按功能模块分类,如 user_api.dart, product_api.dart 等


config/ 目录


存放配置文件,如主题配置、环境变量等
例如 theme.dart, env.dart


models/ 目录


数据模型类
通常和后端 API 的数据结构对应
例如 user_model.dart, product_model.dart


pages/ 目录


存放所有页面文件
可以按功能模块划分子目录
通常一个页面一个文件


providers/ 目录


状态管理相关代码
可以使用 Provider、Riverpod 等
按功能模块分类管理状态


routes/ 目录


路由配置文件
通常包含路由表定义
处理页面跳转逻辑


utils/ 目录


工具类和辅助方法
例如日期格式化、字符串处理等
通用函数集合


widgets/ 目录


可复用的自定义组件
独立于具体业务的 UI 组件
提高代码复用性


main.dart


应用程序入口文件
配置主题、路由等
启动应用程序
```
