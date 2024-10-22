# 网球比赛动量分析项目

本项目是为了参加2024年美国大学生数学建模竞赛（MCM）C题而创建的，主要研究和分析网球比赛中动量的变化及其对比赛结果的影响。我们的团队通过构建数据驱动的模型，深入探讨了比赛中的动量变化如何影响比赛的胜负。此项目最终获得了S奖。

## 比赛题目和任务概述

### 题目翻译

2024 MCM Problem C: 网球中的动量 在2023年温布尔顿男子单打决赛中，20岁的西班牙新星阿尔卡拉斯战胜了36岁的德约科维奇。本题目要求参赛者利用温布尔顿网球赛的详细比赛数据来研究网球比赛中的动量变化，并建立模型来预测这种动量的变化对比赛结果的影响。

### 挑战任务

- **模型建立**：开发模型捕捉比赛中的动量变化。
- **数据分析**：分析动量如何在比赛中起作用，并预测其变化。
- **模型验证**：在其他比赛数据上测试模型的预测性能。
- **报告撰写**：撰写详细的研究报告和为教练提供的备赛建议摘要。

## 最终论文摘要与方法

### 论文摘要

我们的研究通过详细分析2023年温布尔顿网球赛的数据，采用多种统计和机器学习方法，对比赛中的动量变化进行了量化分析。研究结果揭示了动量与比赛结果之间存在显著的相关性，并成功开发了预测模型来预测比赛中动量的变化。

### 使用的方法

### 数据预处理

数据预处理是数据分析的重要步骤，确保了分析的准确性和有效性。在你们的项目中，数据预处理包括以下几个关键步骤：

1. **缺失值处理**：首先识别数据中的缺失值，并根据情况填充或删除。例如，若某个关键变量缺失，可能选择删除该行；如果是次要变量，可能选择用平均值或中位数填充。
2. **异常值检测**：通过可视化（如箱线图）和统计方法（如IQR）识别并处理异常值，确保数据的一致性和可靠性。
3. **数据类型转换**：根据模型的需求转换数据类型，如将时间戳转换为日期格式，或将分类数据编码为数值数据。

### 动量量化

动量量化是项目的核心部分，目的是将网球比赛中的“动量”这一抽象概念转换为可度量和分析的数值指标。具体方法如下：

1. **基于得分的动量计算**：定义一个基于连续得分事件的动量计算公式，如连续赢得点的次数与赢得的总点数之比。
2. **滑动窗口技术**：应用滑动窗口技术计算一定时间窗口内的动量得分，突出显示比赛中的动量变化。
3. **加权动量指标**：引入加权系数来增强关键得分（如破发点）的影响，更准确地反映比赛的动态。

### 统计分析

统计分析用于探索数据中的模式和关系，以及验证动量与比赛结果之间的关联性。

1. **相关性分析**：使用皮尔逊或斯皮尔曼相关系数评估动量得分与比赛结果之间的线性关系。
2. **假设检验**：进行t测试或ANOVA测试来评估不同动量水平下的比赛结果是否存在显著差异。

### 预测模型建立

模型建立旨在基于已量化的动量指标预测比赛结果，主要使用了以下几种模型：

1. **多元线性回归模型**：使用动量指标作为自变量，比赛结果（如最终胜负）作为因变量构建模型，分析变量间的线性关系。
2. **BP神经网络**：构建神经网络模型来处理非线性关系，提高预测的准确性。选择合适的网络结构和参数，如学习率、隐藏层数量和节点数，以优化模型性能。

### 模型评估与验证

模型评估是确认模型预测能力的关键步骤。

1. **交叉验证**：使用k折交叉验证方法评估模型的稳定性和可靠性，确保模型在未见数据上的泛化能力。
2. **性能指标**：计算RMSE、准确率、召回率等性能指标，评估模型在不同方面的表现。
3. **模型比较**：比较不同模型的性能，选择最佳模型应用于实际问题。
### 论文中的关键代码与Notebook对应关系

- **1.ipynb**：
  - **代码功能**：加载和清洗数据，为分析准备数据框架。
  - **论文部分**：数据预处理描述。
- **2.ipynb** 和 **2_1.ipynb**：
  - **代码功能**：计算动量指标，进行初步的动量分析。
  - **论文部分**：动量的定义和初步分析。
- **2_2.ipynb**：
  - **代码功能**：进行动量与比赛结果的相关性分析。
  - **论文部分**：统计分析结果和讨论。
- **3_1.ipynb**：
  - **代码功能**：构建多元线性回归模型。
  - **论文部分**：模型建立和理论依据。
- **3_2.ipynb**：
  - **代码功能**：构建和训练BP神经网络模型。
  - **论文部分**：神经网络模型的应用和结果。
- **4_1.ipynb** 到 **4_5.ipynb**：
  - **代码功能**：模型的综合评估，应用模型到新的数据集，进行预测和总结。
  - **论文部分**：模型评估，通用性测试，最终结论和建议。