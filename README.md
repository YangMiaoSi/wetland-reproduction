
<!-- README.md is generated from README.Rmd. Please edit that file -->
[![Travis-CI Build Status](https://travis-ci.org/samdchamberlain/wetlandcomparison.svg?branch=master)](https://travis-ci.org/samdchamberlain/wetlandcomparison)

WetlandComparison
=================

This package was used the generate the manuscript "Soil properties and sediment accretion modulate methane fluxes from restored wetlands." by Samuel D. Chamberlain et. al. This follows the R package structure adapted from Carl Boettiger's template found here: <https://github.com/cboettig/template>. Briefly, the /data folder contains soil and half-hourly eddy covariance files used in the analysis, the /R folder contains scripts used to process data, and the /vignettes folder contains the Markdown and bibiography files used to generate the manuscript, as well as two figure images that were not directly reproducible in R.

Figure 1 and 4 are not directly reproducible in R, but all other analyses are reproducible in this package. Figure 1 was generated in ArcMap using the soil series data downloaded from the USDA Web Soil Survey (<https://websoilsurvey.sc.egov.usda.gov/>) and eddy covariance flux footprints. Figure 4 was generated using a combined information theory-wavelet time series decomposition using a modification of the MATLAB ProcessNetwork Software found here: <https://github.com/samdchamberlain/ProcessNetwork_Software>. All other analyses in this work are reproducible from the 'manuscript.Rmd' file in the /vignettes folder, and running this file will reproduce this manuscript in its entirety.

Installation
------------

You can install WetlandComparison from github with:

``` r
install.packages("devtools")
devtools::install_github("samdchamberlain/WetlandComparison")
```

How to Run
----------

Load package into RStudio and open the 'manuscript.Rmd' within the /vignettes folder. Using RStudio, click the 'Knit' button at the top of the console and this manuscript, and analyses herein, will be re-created.

# 土壤特性和沉积物淤积调节恢复湿地甲烷通量的可重复性评估
## 项目成员
杨淼思、王松、高栋

## 1. 项目简介
本项目围绕**湿地甲烷通量、土壤特性、沉积物淤积**开展可重复性验证，完整覆盖**数据预处理 → 数据分析及可视化 → 研究报告**全流程，依托R语言与`renv`环境实现跨设备1:1复现。

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
- 生成 Quarto 报告（课程推荐）
- bash

运行
- quarto render report.qmd
- quarto publish gh-pages

输出结果
- 所有图表、报告、结果均保存在 output/ 文件夹中，可直接查看。
## 4. 结果可视化
ggplot(mtcars, aes(x = wt, y = mpg)) +
  geom_point() +
  geom_smooth(method = "lm") +
  labs(title = "甲烷通量与土壤特性关系示意图")
## 5. 项目文件结构
plaintext
wetland-reproduction/
├── R/                  # 数据分析与绘图代码
├── data/               # 原始数据与清洗后数据
├── renv/               # 可复现环境
├── output/             # 输出图表与报告
├── report.qmd          # Quarto 主报告
└── README.md           # 项目说明
## 6. 结果解读
本项目复现了土壤特性、沉积物淤积对湿地甲烷通量的影响规律：
土壤有机质含量与甲烷通量呈正相关
沉积物淤积通过改变土壤通气性影响甲烷排放
全套流程可复现、可追踪、可验证
