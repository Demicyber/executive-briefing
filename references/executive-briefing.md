# Executive Briefing Document

> **INTERNAL USE ONLY** - AWS Confidential
>
> Prepares AWS executives for high-level customer engagements. This is the **Call Plan equivalent for executive-level meetings** — when the milestone is an EBC or internal leadership briefing, EBC replaces Call Plan. All other lifecycle logic (EP → EBC → meeting → PMR → EP) remains the same.
>
> ✅ *After generating, agent always asks the account team to review and revise.*

<!-- GLOBAL AGENT LOGIC:

## 定位
EBC 是 Call Plan 的高管版本。当 EP Roadmap 中的 milestone 是 Executive Briefing Center (EBC) 或内部高管汇报（如 AWS VP/SVP 加入客户拜访）时，生成 EBC 而非 Call Plan。

关系链：EP Next Milestone (方向/目标) → EBC (高管怎么准备) → PMR (会后复盘 → 回写 EP)

与 Call Plan 的区别：
- 受众不同：Call Plan 给 AM/SA 团队用，EBC 给 AWS 高管用
- 信息密度不同：高管时间少，EBC 必须在 2-3 页内给足决策信息
- 侧重不同：EBC 重在 "高管需要知道什么才能有效参与"，不是执行细节
- Asks 不同：EBC 的 asks 是利用高管身份/对等关系才能问的问题

核心原则：
1. 高管时间宝贵 — 每句话都必须有信息价值，零废话
2. 高管看全局 — 给战略上下文，不给操作细节
3. 高管做高管的事 — asks 必须是利用 peer-level 关系才能做的动作
4. 准备 ≠ 控制 — EBC 让高管 informed，但实际对话由高管自然主导

## 数据源
| 来源 | 说明 |
|---|---|
| EP 自动拉取 | Opportunity Snapshot (deal context), Key Stakeholders (customer attendees), Win Strategy, Engagement Roadmap (当前 milestone 位置), Estimate & Contingency |
| Account Information skill | 客户公司信息、AWS 账户数据、spend 数据 |
| CXO Personas + Contact Profiling | 客户高管背景、沟通风格、决策模式 |
| 销售补充 | 会议背景、具体 asks、最新关系动态、内部政治 |
| Agent 生成 | 基于以上整合为 executive-ready 的简洁文档 |

## 生成流程
1. 触发：EP milestone 类型为 EBC / 高管会议，或销售请求高管准备材料
2. Agent 从 EP + Account Info 拉取框架信息
3. Agent 检查上一份 PMR（如有）：unresolved gaps、未完成 action items
4. Agent 生成 EBC 初稿
5. AM/Sales Leader review → confirm 或修改
6. Agent 检查修改项 → 触发双向同步（与 EP 保持一致）

## 双向同步规则
与 Call Plan 相同 — AM 在 EBC 修改的内容，agent 必须检查 EP 对应字段是否需要同步：
- 修改了 attendee stance/info → EP Key Stakeholders
- 改了 meeting objectives → EP Next Milestone Detail
- 发现新竞争情报 → EP Win Strategy
- 加了新 stakeholder → EP Key Stakeholders（新增）

## PMR 接口
EBC 结束后同样走 PMR 闭环。以下字段被 PMR 拉取：
- Meeting Objectives → PMR 对比实际 outcome
- Asks → PMR 评估哪些 ask 得到了回应
- Next Steps (如有) → PMR 对比实际约定

## 写作风格要求
- Exec-ready：2-3 页，高管在去会议的路上能读完
- 用完整句子叙述，不是碎片式要点罗列
- 该有判断的地方给判断（"我们认为…"），不只是罗列事实
- 竞争敏感信息标注来源可信度
-->

---

## 1. Meeting Logistics

<!-- AGENT GUIDANCE:
📥 数据源：销售提供 + EP 自动拉取（opportunity name, stage）

写法标准：
- 高管只需要 30 秒扫完就知道：什么时候、去哪、跟谁、为什么
- "Who requested and why" 必须给上下文 — 高管要知道自己为什么被请来
- AWS Team 要标注每个人的 purpose — 高管不想到场后才发现角色不清
-->

| Field | Details |
|---|---|
| **Date / Time / Format** | {YYYY-MM-DD / HH:MM-HH:MM timezone / In-person or VTC / Location} |
| **Opportunity Name** | `{auto from EP}` |
| **Current Sales Stage** | `{auto from EP}` |
| **AWS Attendees** | {Executive name (role in meeting), Account Manager, other AWS attendees} |

**Who requested this meeting and why?**

> {e.g., "Account team requested the meeting to leverage CEO peer-level relationship to unlock CTO access (currently blocked for 3 weeks). This is milestone #3 in our Engagement Roadmap — without executive intervention, deal timeline slips 4+ weeks."}

| Role | Name / Contact | Purpose in This Meeting |
|---|---|---|
| **Account Manager** | {name, @alias, phone} | `{Lead prep, manage logistics, close next steps}` |
| **Sales Leader / VP** | {name, @alias, phone} | `{Executive sponsor, peer-level credibility}` |
| **Executive Sponsor** | {name, title} | `{Specific ask: e.g., "CEO-to-CEO commitment on joint innovation agenda"}` |

---

## 2. Customer Attendee Background

<!-- AGENT GUIDANCE:
📥 数据源：EP Key Stakeholders + CXO Personas + Contact Profiling + Account Information + 销售补充

定位：让高管在 2 分钟内了解 "我面对的是什么人、他们在乎什么、我跟他们聊的时候要注意什么"

写法标准：
- 每人一段聚焦描述，不超过 150 字
- 必须包含 stance（Holden 5 级）+ evidence — 高管要知道对方是友是敌
- Communication Style 要具体到行为指导（"先给数据再谈战略"而不是"analytical type"）
- 对 executive attendees：从 CXO Personas 提取最相关维度（按本次会议目标筛选）
- 对所有人：Contact Profiling 补充个人行为特征
- 销售 input 永远优先于 profile defaults

维度（每人覆盖）：
1. Position & Tenure — 当前角色、汇报线、关键职业轨迹
2. Stance & Evidence — Holden 5 级 + 判断依据（不接受无 evidence 的标签）
3. What They Care About — 跟本次会议最相关的 1-2 个 pain/priority
4. Communication Approach — 怎么跟他聊最有效 + 什么要避免
5. Relationship History — 跟 AWS 的互动历史、正面/负面经历

质量标准：
- ❌ "CTO, supportive, likes innovation"（标签式，无 actionable info）
- ✅ "王总 (CTO), 入职 14 个月（从 Google Cloud 跳来），Supporter — 主动索要了三份技术白皮书但尚未公开站台。工程师出身，要 benchmark 开场不要 PPT。核心关注：董事会要求的 Q4 降本 20% 目标。注意：他的前任做了 Azure 决策，他公开转向 AWS 有政治风险。"
-->

> *💡 Agent generates from EP Key Stakeholders + CXO Personas + Contact Profiling. Each attendee gets a focused paragraph. Sales confirms and adds relationship nuances.*

**{Attendee Name}** — {Title}

> *{Position & Tenure. Stance (Holden 5级) + evidence. What they care about (跟本次会议目标相关). Communication approach. Relationship history with AWS.}*

*Repeat for each customer attendee.*

### Company Profile

<!-- AGENT GUIDANCE:
📥 数据源：Account Information skill + web research

写法标准：
- 高管需要 60 秒了解 "这是什么公司、多大、什么阶段、最近有什么大事"
- 只写跟本次会议相关的上下文，不是公司百科全书
- 如果公司有最近的重大事件（财报、并购、裁员、高管变动），必须提

维度：
1. Positioning & Industry Standing — 干什么的、排第几
2. Scale & Impact — 营收、用户规模、市场份额
3. Technology Profile — 云采纳阶段、AI 态度、核心技术栈
4. Strategic Priorities & Key Events — 当前战略方向 + 近期大事
5. Recent Leadership Changes — 近 6 个月 C-suite/board 变动
-->

> *{公司定位. 规模. 技术 profile. 战略方向. 近期重大事件.}*

---

## 3. Meeting Objectives

<!-- AGENT GUIDANCE:
📥 数据源：EP Next Milestone Detail (Target Outcome) + 销售明确的 asks → Agent 转化为 executive-ready format

定位：这是 EBC 的核心 — 高管需要知道 "我去了要达成什么、怎么开口、不能踩什么坑"

与 Call Plan Section 2 的区别：
- Call Plan 写给执行团队 — 更细、有双视角
- EBC 写给高管 — 更简、重在 asks 和 talking points
- EBC 的 asks 必须是利用 peer-level 身份/关系才能有效提出的

Success Definition 写法：
- 一句话回答 "这次去了之后，如果达成什么我们就算成功？"
- 必须是可验证的客户动作，不是"建立关系"

Strategic Alignment 写法：
- 连接到 EP 全局策略 — 这个 milestone 在 roadmap 里的位置
- 如果高管知道 big picture，他的对话会更有方向感

Objective 写法标准：
- Objective/Outcome：动词开头的具体动作
- Context：高管需要知道的背景（为什么要这个、什么在阻碍、竞争对手在做什么）
- Talking Points：口语化的表达方式，高管拿来就能用
- Asks：必须是高管级别才能问的问题（CEO 对 CEO 承诺、预算方向、战略合作意向）
  - ❌ "了解他们的技术需求"（AM/SA 就能问）
  - ✅ "请对方 CEO 确认：如果 POC 达标，是否愿意在下季度董事会上支持 $3M 预算审批？"

质量标准：
- 每个 objective 必须有明确的"高管才能做的事"
- Talking points 是对话式的，不是 bullet points 独白
- Context 要坦诚（包括风险和不确定性），高管讨厌被 surprise
- 2-3 个 objectives 足够，不要超过 3 个
-->

> *💡 Agent drafts objectives based on EP Next Milestone Detail. Account team reviews. Each objective must leverage executive-level authority or peer relationship.*

### Success Definition

> {一句话：什么算成功？e.g., "客户 CEO 当场承诺参加下月的 EBC 并带 CFO 一起来，明确这是评估 AWS 战略合作的正式步骤。"}

### Strategic Alignment

> {这次会议在整体策略里的位置。e.g., "这是 Engagement Roadmap 的第 3 步。前两次技术交流已确认方案可行，但 CTO 以下的人推不动预算审批。需要 CEO peer-level 对话来打开高管层通道。"}

### Objective 1: {动词开头的简述}

| Element | Content |
|---|---|
| **Objective / Outcome** | {Action-oriented: e.g., "获得客户 CEO 对联合创新议程的口头承诺，包括指定内部负责人和 Q3 启动时间。"} |
| **Context** | {背景 + 风险 + 竞争: e.g., "技术团队已验证方案可行，但预算审批卡在 CFO 层面 3 周。Azure 同期安排了他们的 VP 拜访客户 CEO。如果我们不在本月建立 CEO-level 连接，可能被竞争对手抢先锁定高管关系。"} |
| **Talking Points** | {口语化: e.g., "「我们跟贵司技术团队合作了两个月，结果非常积极。我今天来是想聊聊：如果技术验证通过，双方高管层面怎么一起推动这件事落地？」"} |
| **Asks** | {高管级: e.g., "1) 请 CEO 确认：如果 POC 结果达标，他是否愿意在 Q3 董事会上支持预算审批？2) 请 CEO 指定一个人作为这个项目的内部 executive owner。"} |

### Objective 2: {动词开头的简述}

| Element | Content |
|---|---|
| **Objective / Outcome** | {e.g., "识别并化解 CFO 对投资回报的核心顾虑，确保预算审批不会被搁置。"} |
| **Context** | {e.g., "CFO 上月在内部会议中质疑了云迁移的 ROI。我们有同行业案例数据但还没机会呈现给他。需要 AWS VP 以 peer-level credibility 分享。"} |
| **Talking Points** | {e.g., "「我理解在这个规模的投资上要算清楚账。我们服务的另一家同等规模的零售企业，迁移后第一年就实现了 30% 的运维成本下降。我可以安排他们的 CTO 跟您做个 reference call。」"} |
| **Asks** | {e.g., "1) 请 CFO 分享他的 ROI 关切具体在哪几个维度 2) 如果我们提供定制 TCO 分析，他是否愿意安排 30 分钟 review？"} |

*Add Objective 3 only if truly needed. 2 is usually enough for a 60-min executive meeting.*

---

## 4. AWS Account Background

<!-- AGENT GUIDANCE:
📥 数据源：Account Information skill + EP Opp Snapshot + EP Win Strategy

定位：让高管了解 "这个客户跟 AWS 的关系全貌" — spend、增长势头、问题、竞争

写法标准：
- 数字要准确、有来源（不能说"大概"）
- Account Summary 用叙述段落，不是碎片要点
- Competitive Landscape 要坦诚 — 高管讨厌到了现场才发现竞争对手的事
- 如果有 active escalation 或 service issue，必须提！高管被客户当面提起而自己不知道 = 灾难
-->

| Field | Details |
|---|---|
| **Geo / Segment** | {e.g., GCR / Enterprise} |
| **Current AWS Spend** | {e.g., $20M (FY2025)} |
| **Expected Spend** | {e.g., $25M (FY2026)} |
| **Commit / PPA Status** | {e.g., Exceeded $2.1M PPA 12 months early; renewal in progress} |

### Account Summary

<!-- AGENT GUIDANCE:
用一段话覆盖：
1. AWS Usage — 什么 workload 在 AWS 上，核心服务，迁移状态
2. Commercial — PPA 状态、续约时间线、spend 趋势
3. Recent Wins / Momentum — 近 3-6 个月正面进展
4. Issues / Concerns — ⚠️ 活跃的 escalation、服务事故、未解决的投诉（高管必须知道！）
5. Competitive Landscape — 其他云厂商的存在感、我们的 win theme

质量标准：
- ❌ 只列好消息不提问题（高管被 surprise = 信任崩塌）
- ✅ 坦诚呈现全貌，包括风险和未解决问题
-->

> *{AWS usage overview. Commercial status. Recent momentum. Active issues/risks. Competitive landscape summary.}*

---

## 5. Appendix

<!-- AGENT GUIDANCE:
Appendix 是 optional 的深度参考 — 高管可能不看，但如果被问到细节可以翻阅。
- Previous Meeting Notes：上次高管参与的会议要点 + 遗留 action items 状态
- Customer Success Stories：跟客户情况匹配的 1-2 个案例（同行业、同规模、同挑战）
- Competitive Intel：比 Account Summary 更详细的竞争分析

质量标准：
- 案例必须有量化结果（"降低 30% 成本"不是"效果很好"）
- 竞争情报标注信息来源和可信度
- Previous Meeting Notes 如果有未完成 action items → 高亮，高管可能被问到
-->

### A. Previous Meeting Notes & Action Items

> {上次高管级会议的要点 + action items 状态（✅ Done / 🔄 In Progress / ❌ Overdue）}

### B. Relevant Customer Success Stories

> *1-2 case studies that mirror the customer's situation. Must include: industry, challenge, solution, quantified outcome, timeline.*

### C. Competitive Intelligence

> *Per competitor:*
> - **Products in use** — What the competitor provides to this customer today
> - **Contract status** — Active terms, renewal timeline, lock-in factors
> - **Customer satisfaction** — Known sentiment
> - **Our differentiators** — Specific advantages (not generic)
> - **Displacement / coexistence strategy**

---

*Executive Briefing Template | Version: 2.0 | INTERNAL USE ONLY*
