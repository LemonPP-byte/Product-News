# Horizon 系统改造实施总结

## 改造时间
2026-03-05

## 改造目标
从"产品新闻聚合"升级为"选品情报系统"，聚焦小众、有趣的产品，减少球鞋/时尚类内容，增加众筹产品和全球市场覆盖。

---

## ✅ 已完成的改造

### 1. Reddit 信息源调整

**禁用的频道（减少球鞋/时尚）：**
- ❌ r/streetwear - 街头时尚
- ❌ r/sneakers - 球鞋文化
- ❌ r/MakeupAddiction - 美妆产品

**新增的频道（小众/有趣产品）：**
- ✅ r/INEEEEDIT - 必买独特产品
- ✅ r/IneeeedIt - 人们想要的有趣产品
- ✅ r/InterestingAsFuck - 令人着迷的产品和创新
- ✅ r/SpecializedTools - 小众专业工具
- ✅ r/DesignPorn - 卓越产品设计

**保留的频道：**
- r/ProductHunters
- r/shutupandtakemymoney
- r/DidntKnowIWantedThat
- r/ProductPorn
- r/BuyItForLife
- r/Entrepreneur
- r/ecommerce
- r/AmazonSeller
- r/dropship
- r/gadgets

### 2. RSS 信息源调整

**禁用的源：**
- ❌ Hypebeast - 街头文化/球鞋/时尚

**新增的源（众筹平台）：**
- ✅ Kickstarter Popular - 热门众筹项目
- ✅ Kickstarter Design - 设计类众筹
- ✅ Kickstarter Tech - 科技类众筹

**新增的源（设计创新）：**
- ✅ Yanko Design - 创新产品设计
- ✅ Design Milk - 现代设计产品

**新增的源（小众产品）：**
- ✅ This Is Why I'm Broke - 独特有趣产品
- ✅ Uncommon Goods Blog - 小众产品

**保留的源：**
- Product Hunt
- Gadget Flow
- Trendy Gadget
- The Gadgeteer
- Engadget
- The Verge
- TechCrunch Hardware
- Cool Hunting

### 3. AI 评分标准优化

**新的评分维度：**
1. **商业潜力 (35%)** - 提高权重，更关注利润和供应链
2. **增长趋势 (30%)** - 新增维度，关注搜索趋势、社交媒体、众筹数据
3. **产品独特性 (20%)** - 强调差异化、创新、小众吸引力
4. **市场验证 (15%)** - 用户评价、销售数据、多区域潜力

**评分调整规则：**

扣分项：
- 球鞋/运动鞋：-2 分
- 基础街头服饰（无创新）：-1 分
- 过度饱和市场：-1 分

加分项：
- 众筹产品（Kickstarter/Indiegogo）：+1 分
- 小众/独特/有趣产品：+1 分
- 解决实际问题的产品：+1 分
- 多区域市场潜力：+1 分
- TikTok/社交媒体病毒式传播：+1 分

**新增标签：**
- #众筹产品
- #小众产品
- #TikTok爆品
- #区域市场

---

## 📊 预期效果

**改造前：**
- 球鞋/时尚：~40%
- 科技产品：~30%
- 其他：~30%

**改造后（目标）：**
- 小众/独特产品：~35%
- 众筹创新产品：~25%
- 科技/家居产品：~20%
- 区域市场机会：~15%
- 其他：~5%

---

## 🚀 下一步计划

### Phase 2: 需要开发的功能（未实施）

1. **TikTok 产品追踪**
   - 集成 Minea API 或 Sell The Trend
   - 追踪 TikTok Shop 爆品
   - 覆盖全球市场

2. **Amazon Best Sellers 爬虫**
   - 多区域：US, DE, UK, JP
   - 重点品类：Home & Kitchen, Electronics

3. **中国市场数据源**
   - 小红书热门产品
   - 淘宝/天猫热销榜

4. **东南亚市场**
   - TikTok Shop Southeast Asia
   - Shopee/Lazada 热销产品

5. **Google Trends 集成**
   - 追踪产品搜索趋势
   - 识别增长最快的产品

6. **Indiegogo 众筹**
   - 添加 Indiegogo RSS 或 API

---

## 🧪 测试建议

运行系统并检查结果：

```bash
cd /Users/admin/Horizon
export PATH="$HOME/.local/bin:$PATH"
uv run horizon --hours 24
```

查看生成的报告：
```bash
open data/summaries/horizon-$(date +%Y-%m-%d)-zh.md
```

**验证指标：**
- ✅ 球鞋/时尚类产品明显减少
- ✅ 众筹产品（Kickstarter）出现在结果中
- ✅ 小众/有趣产品比例增加
- ✅ 评分更关注商业潜力和独特性

---

## 📝 配置文件位置

- 主配置：`/Users/admin/Horizon/data/config.json`
- AI Prompts：`/Users/admin/Horizon/src/ai/prompts.py`

---

## 💡 使用建议

1. **观察 1-2 天的结果**，看新配置是否符合预期
2. **根据实际效果调整**：
   - 如果某些 Reddit 频道质量不高，可以禁用
   - 如果某些 RSS 源内容太多，可以降低优先级
3. **逐步添加新数据源**，避免一次性改动过大
4. **关注 AI 评分**，确保小众产品得到合理评分

---

**改造完成时间：** 2026-03-05
**状态：** Phase 1 完成，Phase 2 待开发
