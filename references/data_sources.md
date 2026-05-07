# 经济学研究常用数据源

## 一、宏观经济学数据

### 1. 国家统计局
- 网址: https://data.stats.gov.cn/
- 数据内容: GDP、CPI、PPI、人口、就业等
- 更新频率: 月度/季度/年度
- 获取方式: 网页下载/API

### 2. 世界银行 WDI
- 网址: https://data.worldbank.org/
- 数据内容: 全球宏观经济指标
- 覆盖范围: 200+国家，50年+
- 获取方式: API（pandas_datareader）

```python
import pandas_datareader as pdr
df = pdr.wb.download(
    country=['CN', 'US', 'JP'],
    indicator=['NY.GDP.MKTP.KD', 'SP.POP.TOTL'],
    start=2000, end=2023
)
```

### 3. OECD Stat
- 网址: https://stats.oecd.org/
- 数据内容: OECD国家经济社会指标
- 特色: 产业结构、创新指标

---

## 二、金融与资本市场数据

### 1. CSMAR 数据库
- 数据内容: 中国上市公司财务、治理、交易数据
- 获取方式: 高校订阅

### 2. Wind 金融终端
- 数据内容: 中国金融市场全口径数据
- 获取方式: 机构订阅

### 3. Yahoo Finance
- 网址: https://finance.yahoo.com/
- 数据内容: 全球股票、汇率、商品
- 获取方式: 免费（yfinance库）

```python
import yfinance as yf
ticker = yf.Ticker("AAPL")
df = ticker.history(period="5y")
```

---

## 三、微观调查数据

### 1. CHFS (中国家庭金融调查)
- 主办: 西南财经大学
- 数据内容: 家庭资产负债、消费、信贷
- 获取方式: 申请获取

### 2. CFPS (中国家庭追踪调查)
- 主办: 北京大学
- 数据内容: 家庭人口、健康、经济
- 获取方式: 申请获取

### 3. CHNS (中国健康与营养调查)
- 主办: 北卡大学 + 中国疾控中心
- 数据内容: 健康、营养、经济
- 获取方式: 公开下载

---

## 四、区域与城市数据

### 1. 中国城市统计年鉴
- 数据内容: 地级市经济社会发展指标
- 获取方式: 年鉴/数据库

### 2. 中国县域统计年鉴
- 数据内容: 县级经济社会发展指标
- 获取方式: 年鉴/数据库

---

## 五、国际研究数据

### 1. Penn World Table
- 网址: https://www.rug.nl/ggdc/productivity/pwt/
- 数据内容: 国家层面生产率数据
- 特色: PPP调整、可比性强

### 2. IMF WEO
- 网址: https://www.imf.org/en/Publications/WEO
- 数据内容: 全球经济展望数据
- 特色: 预测数据

---

## 数据使用规范

1. **引用要求**: 使用数据需在论文中注明来源
2. **保密要求**: 微观调查数据需遵守保密协议
3. **清洗记录**: 记录所有数据处理步骤
4. **版本管理**: 保留原始数据和处理后数据
