# 🎵 MP4 转 MP3 在线转换器

一个简洁美观的网页应用，可以将 MP4 视频文件转换为 MP3 音频文件。使用 FFmpeg.wasm 技术，所有转换都在浏览器本地完成，无需上传文件到服务器，保护您的隐私。

## ✨ 特性

- 🔒 **完全本地转换** - 所有处理在浏览器中完成，文件不会上传到服务器
- 🌐 **纯静态网页** - 可部署到 GitHub Pages 等静态托管服务
- 🎨 **美观的界面** - 现代化的渐变设计，简洁易用
- 📱 **响应式设计** - 支持手机、平板和电脑
- 🚀 **拖拽上传** - 支持点击选择或拖拽文件
- 📊 **实时进度** - 显示转换进度和状态
- 💾 **自动下载** - 转换完成后自动下载 MP3 文件

## 🚀 在线使用

### 方法 1: 本地打开（最简单）

直接双击 `index.html` 文件，在浏览器中打开即可使用！

### 方法 2: 本地服务器

```bash
# 使用 Python
python3 -m http.server 8000

# 使用 Node.js
npx http-server -p 8000
```

然后访问 `http://localhost:8000`

### 方法 3: 部署到 GitHub Pages

1. 创建 GitHub 仓库
2. 上传 `index.html` 文件
3. 在仓库设置中启用 GitHub Pages
4. 访问 `https://你的用户名.github.io/仓库名/`

就这么简单！✨

## 📝 使用步骤

1. 打开应用
2. 点击上传区域或拖拽 MP4 文件
3. 等待 FFmpeg 加载（首次使用会下载约 30MB）
4. 点击"开始转换"按钮
5. 等待转换完成，MP3 文件会自动下载

## 🌐 浏览器要求

需要支持 WebAssembly 的现代浏览器：

- ✅ Chrome/Edge 57+
- ✅ Firefox 52+
- ✅ Safari 11+

## 🔧 技术栈

- **FFmpeg.wasm** - WebAssembly 版本的 FFmpeg（单线程版本）
- **纯前端** - HTML + CSS + JavaScript
- **无需服务器** - 可直接打开使用，也可部署到任何静态托管服务

## 📝 注意事项

1. 首次使用时需要下载 FFmpeg.wasm（约 30MB），请耐心等待
2. 使用单线程版本，转换速度较多线程版本慢，但无需服务器配置
3. 较大的视频文件转换时间会更长，请耐心等待
4. 转换质量设置为高质量（VBR quality 2）
5. 所有处理都在浏览器本地完成，文件不会上传到服务器

## 🔧 故障排除

### FFmpeg 加载失败

**可能原因**:
- 网络问题导致无法从 CDN 下载
- 浏览器不支持 WebAssembly

**解决方案**:
- 检查网络连接
- 更新浏览器到最新版本
- 尝试使用其他浏览器（Chrome、Firefox、Safari）
- 打开浏览器控制台（F12）查看详细错误信息

### 点击上传没有反应

**解决方案**:

1. **检查浏览器控制台**
   - 按 F12 打开开发者工具
   - 查看 Console 标签页是否有错误信息
   - 应该能看到 "应用初始化..." 和 "事件监听器绑定完成！" 的日志

2. **刷新页面**
   - 按 Cmd+Shift+R (Mac) 或 Ctrl+Shift+R (Windows) 强制刷新

3. **检查浏览器版本**
   - 确保使用较新版本的浏览器

### 转换失败

- 确保上传的是视频文件（MP4、AVI、MOV 等）
- 检查文件大小，超大文件可能导致浏览器内存不足
- 尝试转换较小的文件测试（建议 < 500MB）
- 查看浏览器控制台的详细错误信息

### 转换速度慢

这是正常现象。为了能够在没有特殊服务器配置的情况下运行（如 GitHub Pages），我们使用了单线程版本的 FFmpeg.wasm。转换速度取决于：
- 文件大小
- 设备性能
- 浏览器性能

通常一个 10MB 的视频需要 30-60 秒来转换。

## 🎯 音频质量

转换使用以下参数：
- 编码器: libmp3lame
- 质量: VBR quality 2（高质量）
- 采样率: 源文件采样率

## 🌐 部署到 GitHub Pages

### 步骤 1: 创建 GitHub 仓库

```bash
# 初始化 git 仓库
git init
git add .
git commit -m "Initial commit: MP4 to MP3 converter"

# 关联到远程仓库
git remote add origin https://github.com/你的用户名/仓库名.git
git branch -M main
git push -u origin main
```

### 步骤 2: 启用 GitHub Pages

1. 进入仓库的 **Settings**
2. 点击左侧的 **Pages**
3. 在 **Source** 下选择 `main` 分支
4. 点击 **Save**

### 步骤 3: 访问你的应用

几分钟后，你的应用将在以下地址可用：
```
https://你的用户名.github.io/仓库名/
```

就这么简单！🎉 所有人都可以访问使用了。

## 📄 许可

MIT License

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

