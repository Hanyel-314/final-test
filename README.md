# 电梯体验 - Elevator Experience

一个使用 p5.js 创建的第一人称视角电梯交互体验。

## 🌐 在线访问

### 方法 1：GitHub Pages（推荐）
如果已启用 GitHub Pages，访问：
```
https://Hanyel-314.github.io/final-test/
```

### 方法 2：在线预览服务
使用以下任一服务直接预览：

**HTMLPreview：**
```
https://htmlpreview.github.io/?https://github.com/Hanyel-314/final-test/blob/claude/elevator-experience-01MKmEoFCuuVLDTWucLkXy6p/index.html
```

**RawGit：**
```
https://raw.githack.com/Hanyel-314/final-test/claude/elevator-experience-01MKmEoFCuuVLDTWucLkXy6p/index.html
```

### 方法 3：下载到本地
1. 点击右上角 **Code** → **Download ZIP**
2. 解压后双击 `index.html` 即可运行
3. 或者右键点击 `index.html` → 选择浏览器打开

## 功能特性

- **第一人称视角**：站在电梯内部，面向电梯门
- **5 个不同楼层**：每层都有独特的外部场景
  - 1层：温馨的大堂 (Lobby)
  - 2层：办公区域 (Office)
  - 3层：艺术展览 (Gallery)
  - 4层：霓虹科技 (Neon)
  - 5层：天台景观 (Rooftop)
- **真实的电梯行为**：
  - 点击按钮后，电梯会按顺序经过每一层
  - 楼层数字逐层变化（不会直接跳跃）
  - 到达目标楼层后自动开门
  - 平滑的门开合动画
  - 运行时的轻微抖动效果
- **交互式按钮面板**：
  - 左侧5个楼层按钮
  - 激活状态发光显示
  - 当前楼层带绿色指示灯
  - 支持队列系统（可连续点击多个楼层）
- **氛围渲染**：
  - 顶部柔和灯光
  - 金属质感的电梯墙面
  - 透视网格地板
  - LED风格的楼层显示器

## 使用方法

### 在线预览

直接用浏览器打开 `index.html` 文件即可。

### GitHub Pages 部署

1. 将此仓库推送到 GitHub
2. 在仓库设置中启用 GitHub Pages
3. 选择主分支作为源
4. 访问提供的 GitHub Pages URL

### 本地运行

```bash
# 方法1：使用 Python 简单服务器
python -m http.server 8000

# 方法2：使用 Node.js http-server
npx http-server

# 方法3：直接双击 index.html（推荐）
```

然后在浏览器中打开 `http://localhost:8000` 或直接打开文件。

## 交互说明

1. **选择楼层**：点击左侧按钮面板上的楼层按钮（1-5）
2. **等待到达**：电梯会逐层经过并显示楼层数字变化
3. **观看场景**：到达后电梯门会自动打开，展示该楼层的外部场景
4. **继续使用**：门关闭后可以继续选择其他楼层
5. **队列功能**：运行中也可以点击其他楼层按钮，会自动排队

## 技术栈

- **p5.js** - 创意编程库（全局模式）
- **HTML5 Canvas** - 2D渲染
- **纯 JavaScript** - 无需构建工具
- **响应式设计** - 支持桌面和移动设备

## 状态机设计

电梯使用以下状态机：

- `IDLE` - 空闲状态，等待用户输入
- `MOVING` - 移动中，楼层数字逐层变化
- `DOOR_OPENING` - 门正在打开
- `DOOR_OPEN` - 门已打开，展示外部场景
- `DOOR_CLOSING` - 门正在关闭

## 浏览器兼容性

- Chrome/Edge (推荐)
- Firefox
- Safari
- 移动浏览器（支持触摸操作）

## 自定义

你可以轻松修改：

- **楼层数量**：修改 `buttons` 数组
- **动画速度**：调整状态转换的时间参数
- **外部场景**：编辑 `drawLobby`, `drawOffice` 等函数
- **颜色主题**：修改各个绘制函数中的颜色值
- **画布尺寸**：修改 `createCanvas(600, 800)` 参数

## 代码结构

```
index.html
├── HTML 结构
├── CSS 样式
└── JavaScript
    ├── Elevator 类（状态管理）
    ├── 绘制函数
    │   ├── drawCabin() - 电梯内部
    │   ├── drawDoors() - 门和场景
    │   ├── drawPanel() - 按钮面板
    │   ├── drawFloorIndicator() - 楼层显示
    │   └── draw[Floor]() - 各楼层场景
    └── 交互处理
        ├── mousePressed()
        ├── touchStarted()
        └── handleClick()
```

## 🚀 启用 GitHub Pages

要在 GitHub 上直接访问此项目，请按以下步骤设置 GitHub Pages：

1. 进入 GitHub 仓库页面
2. 点击 **Settings**（设置）
3. 在左侧菜单找到 **Pages**
4. 在 **Source** 下选择分支：
   - 选择 `claude/elevator-experience-01MKmEoFCuuVLDTWucLkXy6p` 分支
   - 或者选择 `main` 分支（如果已合并）
5. 点击 **Save**（保存）
6. 等待几分钟后，访问显示的 URL

## 🐛 故障排除

如果页面显示黑屏：
1. **检查浏览器控制台**（按 F12）
   - 应该看到 "Script started", "Setup called", "Setup complete"
   - 如果有红色错误，检查是否是网络问题
2. **检查 p5.js CDN 是否可访问**
   - 如果在国内，CDN 可能被墙
   - 可以下载项目到本地运行
3. **尝试不同浏览器**
   - 推荐使用 Chrome 或 Firefox

## License

MIT License - 自由使用和修改

---

享受你的电梯之旅！ 🛗✨
