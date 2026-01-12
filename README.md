https://xumingzhao0401-blip.github.io/wafer-thickness-viewer-html/
# Wafer Thickness Viewer (Web)

一个纯前端的晶圆厚度数据可视化工具（Wafer Thickness Viewer），支持 **CSV 导入、坐标点生成器、顶视图热力图、3D 分布、统计指标、以及一键导出 PPT 报告**。  
项目可直接通过 GitHub Pages 在线使用，无需安装 Python/Streamlit。

👉 在线地址：<你的 GitHub Pages 链接>  
📦 仓库：<仓库名>

---

## 功能特性

- **数据导入**
  - 支持导入 CSV（要求包含列：`x, y, thickness`）
  - thickness 支持单位选择（μm / Å），内部统一换算为 μm
- **数据集管理**
  - 多数据集切换、重命名、删除
  - 可导出当前数据集 CSV
- **坐标生成器（Generator Mode）**
  - 多种测量点位模板/图案生成
  - 生成后可在网页内表格录入 thickness
  - 表格支持类似 Excel 的粘贴体验：可一次性粘贴一列数值，自动向下填充
  - 强制规则：**中心点必须有点、靠近 edge 必须有点**（自动补点）
- **可视化**
  - 顶视图 Heatmap（插值 + 点位显示）
  - 3D Surface 分布图（支持纵向夸张倍数与视觉比例）
  - 支持 SPEC 上下限平面显示（可选）
- **统计**
  - Mean / Std / CoV / Peak-to-Peak / WIWNU / 3σ / 6σ 等指标
- **报告导出**
  - 一键导出单页 PPTX（含顶视图 + 3D 图 + Raw Data + Statistics）

---

## 输入数据格式（CSV）

CSV 需要包含以下列名（区分大小写不敏感）：

- `x`：X 坐标（mm）
- `y`：Y 坐标（mm）
- `thickness`：厚度（可选 μm 或 Å，导入时选择单位）

示例：

```csv
x,y,thickness
0,0,1.0000
10,0,1.0200
0,10,0.9800
-10,0,1.0100
0,-10,0.9900
