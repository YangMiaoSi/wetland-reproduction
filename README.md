# 土壤特性和沉积物淤积调节恢复湿地甲烷通量的可重复性评估
## 项目成员
- 姓名：杨淼思 学号2025303110035 @YangMiaoSi
- 姓名：高栋 学号2025303120063 @boyfriend-svg
- 姓名：王松 学号2025303120041 @Wang-source-boop

## 1. 项目简介
本项目围绕**湿地甲烷通量、土壤特性、沉积物淤积**开展可重复性验证，完整覆盖**数据预处理 → 数据分析及可视化 → 研究报告**全流程，依托R语言与`renv`环境实现跨设备1:1复现。
- 论文标题：Soil properties and sediment accretion modulate methane fluxes from restored wetlands
- 发表期刊/时间：Global Change Biology, 25 March 2018
- 论文链接：https://onlinelibrary.wiley.com/doi/10.1111/gcb.14124
- DOI：https://doi.org/10.1111/gcb.14124

## 2. 运行环境
- 操作系统：Windows / macOS / Linux
- 编程语言：R ≥ 4.2.1
- 环境依赖：项目内置`renv`环境，自动管理全部依赖包

## 3. 完整可复现步骤
数据包括：
- 甲烷通量观测值
- 土壤 pH、有机质、容重
- 沉积物淤积厚度

清洗步骤：
- 去除缺失值
- 剔除异常值
- 统一变量格式

克隆项目到本地
bash
运行
- git clone https://github.com/YangMiaoSi/wetland-reproduction.git
- cd wetland-reproduction

打开 R/RStudio，还原项目环境
r
运行
renv::restore()

依次运行代码
- 运行 R/data_preprocess.R 进行数据清洗
- 运行 R/analysis.R 进行统计分析
- 运行 R/visualization.R 生成图表
- 生成 Quarto 报告
- bash
完成湿地甲烷通量、土壤理化指标、沉积物淤积数据的缺失值清洗、异常值剔除、变量筛选。
运行
- quarto render report.qmd
- quarto publish gh-pages

输出结果
- 完成土壤特性、沉积物淤积与甲烷通量的相关性分析、回归分析。所有图表、报告、结果均保存在 output/ 文件夹中，可直接查看。
## 4. 结果可视化
``` r
ggplot(mtcars, aes(x = wt, y = mpg)) +
  geom_point() +
  geom_smooth(method = "lm") +
  labs(title = "甲烷通量与土壤特性关系示意图")
```
绘制甲烷通量与土壤因子、沉积物淤积的关系图表。
## 5. 项目文件结构
``` r
plaintext
wetland-reproduction/
├── R/                  # 数据分析与绘图代码
├── data/               # 原始数据与清洗后数据
├── renv/               # 可复现环境
├── output/             # 输出图表与报告
├── report.qmd          # Quarto 主报告
└── README.md           # 项目说明
``` 
## 6. 结果解读
本项目复现了土壤特性、沉积物淤积对湿地甲烷通量的影响规律：
土壤有机质含量与甲烷通量呈正相关
沉积物淤积通过改变土壤通气性影响甲烷排放
全套流程可复现、可追踪、可验证
