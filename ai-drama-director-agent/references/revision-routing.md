# 质量返修路由

## 剧本

问题：弱前提、因果断裂、动机缺口、情节逻辑、对白薄弱、尾钩无效、无铺垫反转。

返回 `$ai-drama-scriptwriting`，通常重跑 Character、Scene、Storyboard、Video、Editing、Quality。

## 人物

问题：身份/脸部漂移、服装、行为或声音不一致。

返回 `$ai-drama-character`，通常重跑 Storyboard、Video、Editing、Quality；若只修生成参数且人物设定不变，可从 Video 开始。

## 场景

问题：地点漂移、道具连续性、光线、空间逻辑。

返回 `$ai-drama-scene`，通常重跑 Storyboard、Video、Editing、Quality。

## 分镜

问题：摄影语言、镜头任务、轴线/连续性、表演不匹配、镜头节奏。

返回 `$ai-drama-storyboard`，重跑 Video、Editing、Quality。

## 视频生成

问题：运动/生成伪影、模型失败、物理错误、视觉不稳定。

返回 `$ai-drama-video`，重跑 Editing、Quality。

## 后期

问题：剪辑节奏、字幕、混音、转场、色彩、导出。

返回 `$ai-drama-editing`，重跑 Quality。

## 发布

问题：标题、封面、平台适配、行动号召。

在成片 Quality 已通过的前提下，仅返回 `$ai-drama-publishing`。

## 决策规则

- 以最早出现问题的责任节点为返回点，并合并同轮所有受影响问题。
- 只让因上游修改而失效的下游重新执行。
- 记录 observed / inferred / unverified，避免把推测当证据。
- 每轮只改变足以验证原因的关键变量；复检失败再扩大范围。
