# 使用 WRDS Compustat 进行财务分析 – ACC102 Track 2

## 1. 问题与用户
**问题**：投资者需要对比不同公司的财务健康度和盈利能力，但手动收集 WRDS 数据门槛较高。  
**用户**：有一定编程基础的金融学生或分析师，希望用 SQL 从 WRDS 提取数据并自动计算关键比率。

## 2. 数据来源
- **数据库**：WRDS Compustat (年度 fundamentals)
- **访问日期**：2026年4月17日
- **关键表**：`comp.funda`（财务数据），`comp.security`（代码映射）
- **公司**：AAPL（苹果）、MSFT（微软）
- **年份**：2019–2024

## 3. 方法与步骤
1. 使用 `wrds` 库建立连接
2. 编写 SQL 查询获取两家公司的流动资产、负债、权益、收入、净利润等字段
3. 计算 ROE、ROA、负债权益比、营业利润率
4. 绘制趋势对比图
5. 统计波动性并给出投资建议

## 4. 主要发现
- AAPL 的平均 ROE 高于 MSFT，但波动性更大
- AAPL 的负债权益比显著高于 MSFT，说明其 ROE 优势部分来自更高的财务杠杆
- 两家公司的 ROA 水平相近，核心盈利能力相当

## 5. 如何运行
```bash
pip install wrds pandas matplotlib seaborn
jupyter notebook financial_analysis_wrds.ipynb
