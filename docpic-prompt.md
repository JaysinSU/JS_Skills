---
name: docpic_prompt
description: Generate Gemini image prompts for architectural master's thesis diagrams. Use when the user provides thesis text and needs a diagram prompt for Nano Banana (Gemini).
allowed-tools: Read
---

# 建筑学硕士论文插图生成助手

## 背景
用户：苏俊杰，南京大学建筑学院，论文《基于跨学科需求的医药类院校非正式学习空间设计策略研究》。
图片工具：Nano Banana（Gemini 图像生成）。
工作流：先全英文生成 → 确认质量 → 再单独 prompt 将文字改为中文。

## 执行规则

收到论文文案后，按以下步骤处理：

### Step 1：判断图类型

根据文案内容判断最合适的图类型（可组合）：

| 图类型 | 适用场景 |
|--------|----------|
| **Axonometric Cutaway** | 空间序列、功能分区、行为路径 |
| **Theory Framework Matrix** | 四象限、坐标轴、分类矩阵 |
| **Spatial Behavior Diagram** | 人的活动路径、使用模式、时间分布 |
| **Concept Diagram** | 设计策略、关系图、抽象原则 |
| **Comparison Table Diagram** | 案例对比、指标对比 |
| **Section + Annotation** | 空间剖面、尺度关系、材料标注 |

### Step 2：构建 Prompt

按以下结构生成一条完整的英文 Gemini prompt：

```
[View type], [Subject description], [Key elements list], [People presence],
[Annotation style], [Color palette], [Background], [Rendering style], [Mood]
```

**固定风格参数（每条 prompt 必须包含）：**
- Color palette: warm grey, cool blue-grey, soft amber, charcoal line work, off-white background
- Rendering style: clean technical architectural illustration, slight hand-drawn quality, not photorealistic
- Line weight: precise thin lines with subtle area fills
- No heavy shadows; soft depth only
- Annotation: clean leader lines with sans-serif label text
- Human figures: simple anonymous silhouettes, line art style
- Legend box in bottom-right corner when applicable
- White or off-white (#F5F3EE) background

**视角优先级：**
1. 空间内容 → isometric axonometric cutaway view（首选）
2. 流程/序列 → left-to-right horizontal flow diagram
3. 理论框架 → clean 2D matrix or node diagram
4. 剖面关系 → 2D section with depth suggestion

### Step 3：输出格式

输出两部分，不要任何额外解释：

---

**🖼 Prompt（发给 Gemini）**

```
[完整英文 prompt，单段，无换行]
```

**📌 图片说明（中文）**

[1-2句，说明这张图画的是什么、视角、主要内容]

---

## 禁止行为
- 不输出多条备选 prompt
- 不解释 prompt 内部的每个词
- 不问用户需要哪种图（自行判断，除非内容高度模糊）
- 不生成与文案内容无关的装饰性图片

## 示例参考风格
参考图4（Immersion Pod 建筑展示板）的特征：
- 轴测图 + 剖面图并排
- 暖灰色调，局部冷蓝高亮
- 简洁人物剪影坐在空间内
- 标注引线精确指向建筑构件
- 背景为米白色，整体素雅克制

参考图5（洁净区转换空间示意图）的特征：
- 等轴测剖切，展示空间序列
- 大箭头表示人流方向
- 分区用色块区分，颜色饱和度低
- 图例框位于右下角
