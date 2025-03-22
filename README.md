# 老约翰读书会"一书一测"批改分析系统

一个简单、高效的阅读测评批改分析系统，专为老约翰读书会设计。

## 功能特性

- 答案录入：快速录入学生测评答案
- 自动批改：系统自动对比标准答案进行批改
- 测评报告：生成详细的测评分析报告
- 错题分析：识别学生常见错误并提供分析
- 能力维度分析：对学生的各项阅读能力进行评估
- 进步追踪：记录学生历次测评成绩，分析进步情况
- 标准答案库：管理不同年级和书籍的标准答案库
- 报告分享：生成可分享的测评报告链接
- 历史记录：查看并管理所有批改历史
- 批量导入：支持从Excel批量导入标准答案库，一次处理多个文件

## 新功能更新

### 批量导入Excel答案库

现在可以通过Excel文件批量导入标准答案库，支持以下功能：

- 一次选择并导入多个Excel文件
- 自动从文件名解析年级和书籍信息（文件命名格式：年级-书籍.xlsx）
- 兼容多种Excel表头格式（支持"题号"/"题目序号"、"题目"/"问题"等多种列名）
- 直观的导入进度显示，包括实时进度条和处理状态
- 自动将导入的答案添加到答案库

### 报告分享功能

为方便与家长和学生沟通，新增测评报告分享功能：

- 一键生成可分享的报告链接
- 链接可通过微信、短信或邮件发送
- 无需登录即可查看完整报告
- 分享记录页面管理所有已分享的报告

### 移动端优化

为提高系统在手机和平板设备上的易用性，进行了以下优化：

- 响应式界面设计，适配各种屏幕尺寸
- 优化移动端触控体验
- 改进移动端下的表单布局和按钮大小
- 确保测评报告在移动设备上完整显示

## 使用指南

### 答案录入

1. 点击"答案录入"标签，进入答案录入页面
2. 输入学生姓名，选择年级和书籍
3. 为每个题目选择学生的答案选项
4. 点击"提交答案"按钮完成批改

### 批量导入标准答案

1. 进入"答案库管理"页面
2. 在批量导入区域中，选择一个或多个Excel文件（命名格式：年级-书籍.xlsx）
3. 点击"导入Excel"按钮开始导入
4. 查看导入进度和结果

### 查看测评报告

- 答案提交后自动生成测评报告
- 报告包含准确率、能力维度分析、错题分析等内容
- 可打印报告或通过链接分享报告
- 所有报告自动保存到历史记录中

## 系统要求

- 现代浏览器（Chrome、Firefox、Safari、Edge等）
- 建议屏幕分辨率不低于1280 x 720
- 支持桌面和移动设备访问

## 隐私说明

本系统所有数据均存储在本地浏览器中，不会上传到服务器。关闭浏览器或清除浏览器数据可能会导致已保存的数据丢失。

## 技术说明

本系统采用纯前端技术构建，使用HTML、CSS和JavaScript实现，无需后端服务器支持，可以在浏览器中直接运行。数据存储在浏览器本地，刷新页面后数据会重置（除非启用本地存储功能）。

## 开始使用

### 方法一：直接打开HTML文件（无需安装）

1. 下载所有文件到本地文件夹
2. 用浏览器打开index.html文件
3. 开始使用系统进行答案录入和批改

### 方法二：使用npm启动（推荐用于开发）

1. 确保已安装Node.js环境（https://nodejs.org/）
2. 打开命令行，进入项目文件夹
3. 首次使用，运行 `npm install` 安装依赖
4. 运行 `npm start` 启动本地服务器
5. 在浏览器中访问服务器提供的地址（通常是 http://localhost:5000）

## 批量上传标准答案方案

### Excel格式批量导入（官方推荐方案）

为管理160本书的标准答案，系统采用Excel表格批量导入方案，支持完整的题目、选项及解析数据：

#### Excel表格格式要求

准备一个包含以下列的Excel表格：

| dimension | number | question | optionA | optionB | optionC | optionD | answer | explanation |
|-----------|--------|----------|---------|---------|---------|---------|--------|-------------|
| 获取信息维度 | 1 | 小熊在花园里发现了什么植物？ | 玫瑰 | 向日葵 | 胡萝卜 | 郁金香 | C | 书中明确提到小熊发现的是胡萝卜。 |
| 整体感知维度 | 4 | 故事的主角是谁？ | 小熊 | 小兔 | 小猫 | 小狗 | A | 故事的主角是小熊。 |
| 解释推断维度 | 7 | 小熊每天给植物浇水，这说明它是一个怎样的小熊？ | 懒惰 | 细心 | 马虎 | 不负责任 | B | 小熊每天都细心照顾植物，说明它很细心。 |

#### 维度对应关系

表格中的维度名称将被映射为系统内部的维度索引：

| 维度名称 | 系统索引 |
|---------|---------|
| 获取信息维度 | 0 |
| 整体感知维度 | 1 |
| 解释推断维度 | 2 |
| 评价鉴赏维度 | 3 |
| 转化运用维度 | 4 |

#### 批量导入操作步骤

1. 准备Excel文件：
   - 按上述格式整理每本书的题目数据
   - 可以将一本书的所有题目放在同一个Excel文件中
   - 保存为.xlsx或.xls格式

2. 在系统中导入：
   - 进入"答案库管理"页面
   - 选择对应的年级和书籍名称
   - 点击"导入Excel答案库"按钮
   - 在弹出的文件选择器中选择准备好的Excel文件
   - 系统将自动解析并导入数据

3. 验证导入结果：
   - 导入成功后会显示成功提示
   - 可通过查看该书籍的标准答案进行验证
   - 检查题目、选项和解析是否正确导入

#### 批量处理160本书的策略

对于160本书的大规模导入，建议：

1. 准备Excel文件：
   - 每本书准备一个独立的Excel文件
   - 文件命名建议包含年级和书籍名称，便于识别
   - 每个Excel文件只包含一本书的所有题目

2. 批量导入：
   - 每次选择一个年级
   - 可以一次选择多个Excel文件进行批量导入
   - 系统会自动按顺序处理每个文件
   - 导入过程中会显示进度提示
   - 建议每批次导入不超过20个文件，避免浏览器负载过重

3. 导入后数据保存：
   - 系统将自动保存导入的数据到浏览器本地存储
   - 建议每导入一本书后检查数据是否正确
   - 避免刷新页面或关闭浏览器导致数据丢失

#### 系统实现代码

系统已整合以下代码实现Excel导入功能：

```javascript
// 导入Excel功能实现
function setupExcelImport() {
    // 创建导入按钮
    const importExcelBtn = document.createElement('button');
    importExcelBtn.textContent = '导入Excel答案库';
    importExcelBtn.className = 'primary-btn';
    importExcelBtn.style.marginTop = '20px';
    document.querySelector('#answer-management .form-container').appendChild(importExcelBtn);
    
    // 添加文件输入控件（隐藏）
    const fileInput = document.createElement('input');
    fileInput.type = 'file';
    fileInput.accept = '.xlsx, .xls, .csv';
    fileInput.style.display = 'none';
    document.querySelector('#answer-management .form-container').appendChild(fileInput);
    
    // 点击导入按钮时触发文件选择
    importExcelBtn.addEventListener('click', function() {
        fileInput.click();
    });
    
    // 文件选择后处理
    fileInput.addEventListener('change', async function(e) {
        const file = e.target.files[0];
        if (!file) return;
        
        try {
            const data = await readExcelFile(file);
            processExcelData(data);
            alert('答案库导入成功！');
        } catch (error) {
            alert('导入失败，请检查文件格式！');
            console.error(error);
        }
    });
}

// 处理Excel数据并添加到答案库
function processExcelData(data) {
    const grade = document.getElementById('manage-grade').value;
    const book = document.getElementById('manage-book').value;
    
    if (!grade || !book) {
        alert('请先选择年级和书籍！');
        return;
    }
    
    const bookKey = `${grade}-${book}`;
    
    // 准备数据数组
    const answers = [];
    const dimensions = [];
    const questions = [];
    const options = [];
    const explanations = [];
    
    // 处理每一行数据
    data.forEach(row => {
        const index = parseInt(row.number) - 1;
        
        // 存储答案
        answers[index] = row.answer;
        
        // 存储维度
        const dimensionMap = {
            '获取信息维度': 0,
            '整体感知维度': 1,
            '解释推断维度': 2,
            '评价鉴赏维度': 3,
            '转化运用维度': 4
        };
        dimensions[index] = dimensionMap[row.dimension] || 0;
        
        // 存储题目和选项
        questions[index] = row.question;
        options[index] = {
            A: row.optionA,
            B: row.optionB,
            C: row.optionC,
            D: row.optionD
        };
        
        // 存储解析
        explanations[index] = row.explanation;
    });
    
    // 保存到答案库
    answersDatabase[bookKey] = {
        answers: answers,
        dimensions: dimensions,
        questions: questions,
        options: options,
        explanations: explanations
    };
    
    // 保存到本地存储
    localStorage.setItem('answersDatabase', JSON.stringify(answersDatabase));
}
```

### 本地存储功能

为确保导入的答案库数据不会丢失，系统实现了本地存储功能：

```javascript
// 初始化时从本地存储加载数据
function initAnswersFromLocalStorage() {
    const savedAnswers = localStorage.getItem('answersDatabase');
    if (savedAnswers) {
        try {
            answersDatabase = JSON.parse(savedAnswers);
            console.log('从本地存储加载了答案库数据');
        } catch (e) {
            console.error('读取本地存储数据失败', e);
        }
    }
}

// 在页面加载时调用
document.addEventListener('DOMContentLoaded', function() {
    initAnswersFromLocalStorage();
    // ... 其他初始化函数
});
```

## 错题分析与能力评估

系统根据导入的答案库数据，对学生作答进行全方位分析：

1. **题目与选项展示**：
   - 学生答题界面将显示完整题目和四个选项
   - 选项采用直观的ABCD单选形式

2. **错题详细解析**：
   - 展示学生错误选项与正确选项对比
   - 提供基于explanation字段的详细解析
   - 说明该题考察的能力维度

3. **五维度能力分析**：
   - 根据题目维度分类评估五个能力维度
   - 使用雷达图直观展示各维度得分
   - 针对薄弱维度提供个性化学习建议

## 注意事项

- 首次使用前，请先通过Excel导入标准答案库
- 系统使用浏览器本地存储保存数据，不会丢失（除非清除浏览器数据）
- 推荐使用Chrome、Edge或Firefox等现代浏览器
- 要使用Excel导入功能，需要在index.html中引入xlsx库：`<script src="https://cdn.jsdelivr.net/npm/xlsx/dist/xlsx.full.min.js"></script>`
- 批量导入大量数据时，建议分批进行，避免浏览器负载过重 

读书会课后阅读题批改系统/
├── index.html              # 主页面
├── css/
│   ├── style.css           # 主样式
│   └── report.css          # 报告样式
├── js/
│   ├── main.js             # 主逻辑
│   ├── database.js         # 答案库管理
│   ├── evaluation.js       # 评估逻辑
│   └── report.js           # 报告生成
└── assets/
    └── logo.svg            # 系统logo 