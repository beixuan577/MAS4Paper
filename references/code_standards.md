# 代码规范与最佳实践

## 一、项目结构

```
project/
├── data/
│   ├── raw/           # 原始数据
│   ├── processed/     # 处理后数据
│   └── external/      # 外部数据
├── code/
│   ├── 01_data_cleaning.py
│   ├── 02_descriptive.py
│   ├── 03_regression.py
│   ├── 04_robustness.py
│   └── 05_figures.py
├── output/
│   ├── tables/
│   └── figures/
├── logs/
└── README.md
```

## 二、编码规范

### 1. 命名约定

```python
# 变量命名: 小写+下划线
gdp_growth = 0.05
inflation_rate = 0.02

# 常量命名: 大写+下划线
MAX_ITERATIONS = 1000
DEFAULT_ALPHA = 0.05

# 函数命名: 小写+下划线，动词开头
def calculate_growth_rate(data):
    pass

def run_regression(y, X, controls):
    pass

# 类命名: 大驼峰
class DataCleaner:
    pass
```

### 2. 文档字符串

```python
def run_regression(df, y_var, x_vars, controls, 
                   model_type='ols', robust=True):
    """
    执行回归分析
    
    Parameters
    ----------
    df : pd.DataFrame
        分析数据集
    y_var : str
        因变量名称
    x_vars : list
        自变量名称列表
    controls : list
        控制变量名称列表
    model_type : str, optional
        模型类型 ('ols', 'logit', 'probit')
    robust : bool, optional
        是否使用稳健标准误
    
    Returns
    -------
    results : dict
        包含回归结果、统计量等
        
    Example
    -------
    >>> results = run_regression(df, 'gdp_growth', ['fdi'], ['population'])
    >>> print(results['summary'])
    """
    pass
```

### 3. 日志记录

```python
import logging
from datetime import datetime

# 设置日志
logging.basicConfig(
    filename=f'logs/analysis_{datetime.now():%Y%m%d}.log',
    level=logging.INFO,
    format='%(asctime)s - %(levelname)s - %(message)s'
)

logger = logging.getLogger(__name__)

# 记录执行过程
logger.info(f"开始数据清洗，原始数据量: {len(df)}")
logger.info(f"缺失值处理完成，处理后数据量: {len(df_clean)}")
logger.warning(f"变量 {var} 存在 {missing_ratio:.2%} 缺失值")
logger.error(f"回归失败: {str(e)}")
```

## 三、可复现性保障

### 1. 随机种子

```python
import numpy as np
import random

SEED = 42
np.random.seed(SEED)
random.seed(SEED)

# 保存种子配置
with open('config/seed.txt', 'w') as f:
    f.write(f"SEED={SEED}")
```

### 2. 环境记录

```bash
# 导出依赖
pip freeze > requirements.txt

# 或使用conda
conda env export > environment.yml
```

### 3. 版本控制

```python
import pandas as pd
import statsmodels.api as sm

# 记录关键包版本
versions = {
    'pandas': pd.__version__,
    'statsmodels': sm.__version__,
}

with open('config/versions.txt', 'w') as f:
    for pkg, ver in versions.items():
        f.write(f"{pkg}=={ver}\n")
```

## 四、数据处理规范

### 1. 数据验证

```python
def validate_data(df, expected_columns, expected_types):
    """
    数据验证函数
    """
    # 检查列是否存在
    missing_cols = set(expected_columns) - set(df.columns)
    if missing_cols:
        raise ValueError(f"缺少列: {missing_cols}")
    
    # 检查数据类型
    for col, expected_type in expected_types.items():
        if df[col].dtype != expected_type:
            logger.warning(f"{col} 类型不匹配: {df[col].dtype} vs {expected_type}")
    
    # 检查缺失值
    missing_ratio = df.isnull().sum() / len(df)
    for col, ratio in missing_ratio.items():
        if ratio > 0.1:
            logger.warning(f"{col} 缺失值比例过高: {ratio:.2%}")
    
    return True
```

### 2. 数据清洗记录

```python
def log_cleaning_step(df_before, df_after, step_name, params=None):
    """
    记录数据清洗步骤
    """
    record = {
        'step': step_name,
        'timestamp': datetime.now().isoformat(),
        'rows_before': len(df_before),
        'rows_after': len(df_after),
        'rows_removed': len(df_before) - len(df_after),
        'params': params
    }
    
    with open('logs/cleaning_steps.jsonl', 'a') as f:
        f.write(json.dumps(record) + '\n')
    
    return record
```

## 五、结果输出规范

### 1. 表格输出

```python
def save_regression_table(results, filename, format='latex'):
    """
    保存回归表格
    """
    if format == 'latex':
        # LaTeX格式
        latex_table = results.as_latex()
        with open(f'output/tables/{filename}.tex', 'w') as f:
            f.write(latex_table)
    elif format == 'csv':
        # CSV格式
        results_df = pd.DataFrame(results)
        results_df.to_csv(f'output/tables/{filename}.csv', index=False)
```

### 2. 图表输出

```python
def save_figure(fig, filename, formats=['png', 'pdf']):
    """
    保存图表
    """
    for fmt in formats:
        fig.savefig(
            f'output/figures/{filename}.{fmt}',
            dpi=300,
            bbox_inches='tight'
        )
```

## 六、质量检查清单

```markdown
## 数据质量检查
- [ ] 数据完整性检查
- [ ] 缺失值处理记录
- [ ] 异常值处理记录
- [ ] 变量标签完整

## 代码质量检查
- [ ] 函数文档完整
- [ ] 关键步骤有日志
- [ ] 异常处理完整
- [ ] 参数可配置

## 结果质量检查
- [ ] 结果与预期一致
- [ ] 敏感性分析完成
- [ ] 图表清晰美观
- [ ] 表格格式规范
```
