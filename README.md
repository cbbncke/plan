# 目标倒计时

一款轻量级多目标倒计时卡片应用，纯前端技术栈，本地存储，无广告无账号。

## 功能

- **多目标卡片** — 标题、备注、emoji、倒计时天数，一屏掌握所有目标
- **增删改排序** — 添加/编辑/删除目标，上下排序调整优先级
- **深浅主题** — 深色 / 浅色两套主题，即时切换
- **到期提醒** — 剩余天数归零时卡片自动标记「已到期」
- **数据持久化** — localStorage 本地存储，刷新/重启不丢失

## 技术栈

| 模块 | 方案 |
|------|------|
| 前端 | HTML5 + CSS3 + 原生 JS，零依赖 |
| 存储 | localStorage |
| 打包 | Android WebView 壳（Java） |

## 项目结构

```
plan/
├── index.html              # 前端源码（单文件，含 CSS + JS）
├── android/                # Android 工程（WebView 壳）
│   ├── app/src/main/
│   │   ├── assets/
│   │   │   └── index.html  # 前端副本，打包进 APK
│   │   ├── java/.../       # MainActivity（WebView 加载）
│   │   ├── res/            # 图标、布局、主题
│   │   └── AndroidManifest.xml
│   ├── build.gradle
│   └── settings.gradle
├── 产品规划.md              # 产品需求文档
└── README.md
```

## 快速开始

### 浏览器预览

直接双击 `index.html` 即可。

### 构建 APK

需要 JDK 21 + Android SDK（platform 34+）：

```bash
cd android

# 设置环境变量（按实际路径修改）
export JAVA_HOME="C:\Program Files\Android\openjdk\jdk-21.0.8"
export ANDROID_HOME="$HOME/AppData/Local/Android/Sdk"

# 构建 Debug APK
gradle assembleDebug --no-daemon
```

产出路径：`app/build/outputs/apk/debug/app-debug.apk`

### 安装到手机

```bash
adb install app/build/outputs/apk/debug/app-debug.apk
```

## 卡片配色

| 主题 | 渐变效果 |
|------|---------|
| `dark` | 深蓝黑渐变，倒计时绿色 |
| `green` | 深绿渐变，倒计时淡绿 |
| `blue` | 浅蓝渐变，倒计时深蓝 |

## License

MIT
