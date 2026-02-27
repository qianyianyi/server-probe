# Server Probe Dashboard

一个现代化的服务器探针面板，用于实时监控服务器状态和性能指标。

## 🚀 功能特性

- 📊 **实时监控** - CPU、内存、磁盘、网络使用率
- 📈 **趋势图表** - 性能数据可视化
- 🖥️ **服务器信息** - 详细的系统信息展示
- 🔄 **自动刷新** - 定时更新数据
- 📱 **响应式设计** - 适配所有设备

## 🛠️ 技术栈

- **HTML5** + **CSS3** + **JavaScript**
- **Chart.js** - 数据可视化
- **Font Awesome** - 图标库
- **纯前端实现** - 无需后端依赖

## 📁 文件结构

```
server-probe/
├── index.html          # 主页面文件
├── wrangler.json       # Cloudflare配置
├── _config.toml        # Pages配置
└── README.md           # 项目说明
```

## 🚀 部署到Cloudflare Pages

### 手动部署步骤

1. **登录Cloudflare控制台**
   - 访问: https://dash.cloudflare.com/
   - 选择 **Pages** → **Create a project**

2. **连接Git仓库**
   - 选择 **GitHub** 或其他Git提供商
   - 授权并选择仓库

3. **配置构建设置**
   - **项目名称**: `server-probe`
   - **生产分支**: `main` 或 `master`
   - **构建设置**:
     - **框架预设**: `None`
     - **构建命令**: (留空)
     - **构建输出目录**: `.`

4. **开始部署**
   - 点击 **Save and Deploy**
   - 等待部署完成

### 部署后的访问地址
```
https://server-probe.你的用户名.pages.dev
```

## 🔧 自定义配置

### 连接到真实服务器

当前版本使用模拟数据。要连接到真实服务器，需要：

1. **创建后端API**
   ```javascript
   // 示例API端点
   app.get('/api/server-stats', (req, res) => {
     const stats = {
       cpu: getCPUUsage(),
       memory: getMemoryUsage(),
       disk: getDiskUsage(),
       network: getNetworkStats()
     };
     res.json(stats);
   });
   ```

2. **修改前端数据源**
   ```javascript
   // 替换 generateMockData() 函数
   async function fetchRealData() {
     const response = await fetch('/api/server-stats');
     return await response.json();
   }
   ```

### 添加更多监控项

可以扩展监控：
- 数据库连接数
- 网站访问统计
- 安全事件监控
- 日志文件分析

## 📊 监控指标

- **CPU**: 使用率、负载、核心数
- **内存**: 使用率、已用/可用空间
- **磁盘**: 使用率、已用/可用空间
- **网络**: 上行/下行流量
- **进程**: 运行状态、资源占用

## 🎨 界面特色

- 🌈 **现代化设计** - 渐变背景和卡片布局
- 📱 **完全响应式** - 适配手机和桌面
- 🎯 **实时动画** - 进度条和图表动态更新
- 🔄 **交互控制** - 手动刷新和自动刷新

## 📄 许可证

MIT License - 可自由使用和修改

---

⭐ 如果这个项目对你有帮助，请给个Star！