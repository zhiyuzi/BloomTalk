# Bloom Talk Profile 建档字段说明

本文件只解释建档时为什么要关心这些字段，以及它们和孕周判断、风险理解之间的关系。

`profile.md` 的字段结构不在这里维护，唯一字段模板见：

- [bloom-talk-mem/profile-template.md](../../../bloom-talk-mem/profile-template.md)

## 1. 日期基准相关信息

这些信息最重要，因为整个系统很多判断都依赖孕周和预产期基准。

- 末次月经第一天（LMP），如果知道的话
- 早孕期定孕周超声的日期与结果，如果知道的话
- 当前采用的预产期（EDD）
- 当前采用的定孕周依据
  - 例如：按末次月经
  - 例如：按早孕超声
  - 例如：两者结合后以超声为准
- 最近一次确认这些日期的时间

为什么要记录：

- NHS 体系中的孕期建档与孕期进度，都会围绕孕周和预产期展开。
- 官方资料也反复强调，早期需要尽快建立初始孕周基准。

参考：

- NHS《Your first midwife appointment》：
  https://www.nhs.uk/pregnancy/your-pregnancy-care/your-first-midwife-appointment/
- Somerset NHS《Your estimated due date》：
  https://www.somersetft.nhs.uk/maternity-new/maternity/antenatal-care/your-estimated-due-date/
- Kent and Medway NHS《When is my baby due?》：
  https://www.kentandmedwaylms.nhs.uk/my-pregnancy/when-my-baby-due

## 2. 身份与支持信息

这些信息用于让系统稳定地知道在记录谁、如何称呼、由谁提供主要支持。

- 记录对象的称呼或昵称
- 伴侣或主要支持者称呼，可选
- 当前居住与支持情况的简要说明

为什么要记录：

- NHS 的首次 midwife appointment 会询问住在哪里、和谁一起住、有没有伴侣或家人支持。
- 对 Bloom Talk 来说，这些信息会影响后续记录方式和沟通语气。

参考：

- NHS《Your first midwife appointment》：
  https://www.nhs.uk/pregnancy/your-pregnancy-care/your-first-midwife-appointment/

## 3. 既往妊娠与分娩史

- 是否首次怀孕
- 既往妊娠次数
- 既往分娩、流产、终止妊娠等重要情况

为什么要记录：

- 官方孕期建档通常会问既往妊娠和孩子情况。
- 这类信息会影响风险理解，也会影响后续沟通。

参考：

- NHS《Your first midwife appointment》：
  https://www.nhs.uk/pregnancy/your-pregnancy-care/your-first-midwife-appointment/

## 4. 重要健康背景

- 既往身体疾病
- 既往心理健康情况
- 当前正在使用的药物、补充剂
- 过敏史或已知禁忌
- 家族中与妊娠或遗传相关的重要病史

为什么要记录：

- 首次产检会询问身体和心理健康、治疗史、家族健康问题。
- 对于后续给建议、查看 KB、判断风险边界都很重要。

参考：

- NHS《Your first midwife appointment》：
  https://www.nhs.uk/pregnancy/your-pregnancy-care/your-first-midwife-appointment/
- ACOG《Prenatal Care》摘要中提到首次产检会讨论个人和家族健康史以及末次月经：
  https://www.acog.org/womens-health/faqs/prenatal-care

## 5. 当前孕期照护信息

- 是否已经与医生、助产士或医院建立联系
- 是否已有重要检查或超声
- 当前已知的重要医疗提示

为什么要记录：

- 这些信息决定系统在建议时应更偏向提醒尽快就医，还是围绕既有照护安排继续记录。

## 使用方式

- 当你需要实际填写 `profile.md` 时，以 [bloom-talk-mem/profile-template.md](../../../bloom-talk-mem/profile-template.md) 为准
- 当你需要理解某类字段为什么重要，或需要向用户解释为什么要补这类信息时，再回到本文件
- 不要在本文件中增删 `profile.md` 的字段顺序
