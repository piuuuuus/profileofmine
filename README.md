# 个人求职风采展示网页

一个用于面试展示自我的个人求职风采展示静态网页，支持纯前端部署到 GitHub Pages，全世界任何人都能打开访问。

## 技术栈

- HTML + CSS + JavaScript
- Vue3 (使用CDN方式引入)
- Font Awesome 图标库

## 核心功能

1. **面向面试官**：专业、高级、简洁、印象深刻
2. **动态高级感**：平滑滚动、卡片渐入、微动效、玻璃态质感、现代留白
3. **模块化结构**：支持无限扩展
   - 个人介绍
   - 简历（PDF/Word 预览、下载）
   - 作品集
   - 可自由新增：爱好介绍、旅行足迹、思考感悟、技能清单、项目经历等模块
4. **模块管理**：
   - 拖拽排序
   - 拖拽上传图片/PDF
   - 编辑标题、内容
   - 隐藏/显示
5. **双模式**：
   - 访客模式（公开展示，别人看到的干净界面）
   - 编辑模式（只有我能进入，密码解锁）
6. **数据管理**：
   - 访客只能看，不能改
   - 编辑内容只保存在本地存储 localStorage
   - 别人打开看不到我的私人编辑数据
   - 换设备需要重新编辑，但不会影响别人看到的页面
7. **简历支持**：
   - 上传 PDF/Word
   - 在线预览
   - 一键下载
8. **作品集支持**：
   - 图片卡片
   - 拖拽排序
   - 点击放大预览

## 如何部署到 GitHub Pages

1. **创建 GitHub 仓库**
   - 登录 GitHub，点击右上角的 "New repository"
   - 填写仓库名称（例如：`portfolio` 或 `personal-showcase`）
   - 选择 "Public" 类型
   - 点击 "Create repository"

2. **上传文件**
   - 方法一：使用 Git 命令行
     ```bash
     # 克隆仓库
     git clone https://github.com/your-username/your-repository.git
     
     # 进入仓库目录
     cd your-repository
     
     # 复制所有文件到仓库目录
     # （将 index.html 和 README.md 文件复制到这里）
     
     # 提交并推送
     git add .
     git commit -m "Initial commit"
     git push origin main
     ```
   
   - 方法二：直接在 GitHub 网页上上传
     - 进入创建的仓库
     - 点击 "Add file" -> "Upload files"
     - 拖拽 index.html 和 README.md 文件到上传区域
     - 填写提交信息，点击 "Commit changes"

3. **启用 GitHub Pages**
   - 进入仓库的 "Settings" 页面
   - 点击左侧的 "Pages"
   - 在 "Source" 部分，选择 "main" 分支，点击 "Save"
   - 等待几分钟，GitHub Pages 会生成一个访问链接

4. **访问你的网站**
   - 部署完成后，你可以通过 `https://your-username.github.io/your-repository/` 访问你的个人求职风采展示网页

## 如何进入编辑模式

1. 打开你的个人求职风采展示网页
2. 点击右上角的编辑模式按钮（带铅笔图标的圆形按钮）
3. 在弹出的登录框中输入密码：`admin123`（你可以在代码中修改此密码）
4. 登录后即可进入编辑模式

## 如何添加新模块

1. 进入编辑模式
2. 点击右上角的添加模块按钮（带加号图标的圆形按钮）
3. 在弹出的对话框中填写模块标题和图标类名（例如：`fa-briefcase` 表示公文包图标）
4. 点击 "添加" 按钮
5. 点击新模块的编辑按钮，输入模块内容

## 如何修改登录密码

1. 打开 index.html 文件
2. 找到 `login` 方法中的 `correctPassword` 变量
3. 将其值修改为你想要的密码
4. 保存文件并重新部署

```javascript
login() {
    // 简单的密码验证，实际项目中应该使用更安全的方式
    const correctPassword = 'admin123'; // 修改为你自己的密码
    if (this.loginPassword === correctPassword) {
        // ...
    }
    // ...
}
```

## 注意事项

- 由于数据存储在本地存储 localStorage 中，换设备后需要重新编辑内容
- 上传的文件（简历、作品集图片）会以 base64 格式存储在本地存储中，可能会占用较多存储空间
- 为了保证页面加载速度，建议上传的图片和PDF文件不要太大

## 自定义样式

你可以通过修改 CSS 变量来自定义页面样式：

```css
:root {
    --primary-color: #0a2463; /* 主色调 */
    --secondary-color: #3e92cc; /* 次要色调 */
    --accent-color: #d8315b; /* 强调色 */
    --background-color: #f8f9fa; /* 背景色 */
    --card-background: rgba(255, 255, 255, 0.85); /* 卡片背景色 */
    --text-color: #333; /* 文本颜色 */
    --text-light: #666; /* 浅色文本颜色 */
    --border-radius: 12px; /* 边框圆角 */
    --box-shadow: 0 10px 30px rgba(0, 0, 0, 0.1); /* 阴影效果 */
    --transition: all 0.3s ease; /* 过渡效果 */
}
```
