# 方法依据与适配

本文件用于理解和调整 Skill 的设计依据。运行任务的具体要求见 `SKILL.md` 和 `text-governance.md`；普通执行不必额外读取本文件或访问外部网页。

下列管理与系统工程方法提供设计思路。将其用于 Agent 的任务理解与执行，是本 Skill 的适配方案；理论来源不证明该方案已对模型行为产生效果。来源于 2026-09-24 核读。

## QFD：保持需求与实现的联系

QFD 将顾客需求与设计、执行活动联系起来。质量屋是工具之一，建立矩阵本身不等于实施 QFD。

本 Skill 据此保持“用户要求—结果质量—实际活动—支持证据”的联系，检查各项活动能否共同完成完整工作。每一条实现关系仍需要依据和验证；填满对应关系不能证明有效。理解潜在目的不授权覆盖用户明确要求，优先级分析也不能抵消必须满足的条件。

来源：[QFD Institute：How QFD Works](https://www.qfdi.org/how-qfd-works)、[Quick Facts about QFD](https://www.qfdi.org/qfd-quick-facts)。

## 双环学习：修正支配决定的假设

Argyris 区分宣称遵循的原则与实际支配行动的原则，并讨论对定义、解决问题的方式本身进行检验。

本 Skill 据此要求：当整体理解被否定或同类失败反复发生时，依据实际记录检查共同假设和完成标准，修正全部受影响决定，而不只调整一次动作。该借鉴用于可观察的行为和决定，不据此推断模型具有人类心理动机。

来源：[Chris Argyris：Teaching Smart People How to Learn，原文重印](https://center-for-leadership.org/wp-content/uploads/2016/09/2_ArgyrisTeachingSmartPeopleHowtoLearn.pdf)。

## PDSA：以预期和观察形成学习

Deming Institute 将 PDSA 说明为通过计划、执行、研究和调整获得学习的循环，强调比较预期与实际结果，并据此修正理论。

本 Skill 据此在关键设计中明确预期，在执行后研究差异支持或否定哪项假设。未知有效性由实际工作检验，不用重复运行或事后降低标准替代学习。用户目标的改变仍由相应授权和确认决定。

来源：[The W. Edwards Deming Institute：PDSA Cycle](https://deming.org/explore/pdsa/)。

## 需求追溯与验证／确认：使证据能够否定方案

NASA 系统工程方法区分产品是否符合规定与产品是否满足用户预期用途，并将需求与设计、验证及变更联系起来。

本 Skill 据此分别检查具体规定的落实和整体结果的用途，保持双向可追溯关系。追溯不能只记录位置，还需要判断实现是否保存了要求的完整含义。采用可独立核对的原始需求、材料和实际结果，不强制设置第二个 Agent、审批委员会或大型数据库。

来源：[NASA：Product Realization](https://www.nasa.gov/reference/5-0-product-realization/)、[Crosscutting Technical Management](https://www.nasa.gov/reference/6-0-crosscutting-technical-management/)。

## 对 Skill 效果的判断

格式、引用完整性和安装一致性只能证明相应技术事实。实际效果要观察不同任务中是否准确落实需求，能否识别表面符合检查但没有完成任务的方案，能否在反馈后改变受影响决定，以及多轮执行和恢复后是否仍保存有效要求。

Skill 使用相同模型完成判断，不提供自动消除误解的保证。是否有效由上述行为和产出证据判断，不由规则数量、理论名称或自我评价决定。独立行为验证按任务已有授权组织，本文件不自动授权新建任务、调用 Agent 或扩大材料范围。
