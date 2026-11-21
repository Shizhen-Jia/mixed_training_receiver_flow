# 初始计划提交说明

本次对应截图中的 **Initial Plan / Project Outline**。提交文件是 [`plans/initial_plan.md`](plans/initial_plan.md)，当前状态是计划阶段。作业由 SJ00425 自行提交。

## GitHub 与提交链接

仓库：[Shizhen-Jia/mixed_training_receiver_flow](https://github.com/Shizhen-Jia/mixed_training_receiver_flow)

答案框使用的计划文件链接：

```text
https://github.com/Shizhen-Jia/mixed_training_receiver_flow/blob/main/plans/initial_plan.md
```

评分前，先将本地文件 push 到该仓库的 `main` 分支，并确认仓库为 **public**。退出登录或使用无痕窗口打开[计划文件](https://github.com/Shizhen-Jia/mixed_training_receiver_flow/blob/main/plans/initial_plan.md)，确认内容可以公开读取。本说明提供目标链接，不代表已经完成 push 或公开访问验证。

## 评分与上交

1. 打开课程的 [LLM grader](https://llmgrader-e6o7.onrender.com/c/hwdesign/)，选择 Project Outline 对应题目。
2. 保留题目预设的高推理模型，将 timeout 设置为 **至少 100 秒**。
3. 在答案框粘贴计划文件的完整 GitHub 链接，点击 Grade，检查反馈；如有修改，先重新 push，再评分。
4. 按课程 [dashboard 提交流程](https://sdrangan.github.io/llmgrader/docs/student/dashboard.html) 下载 submission ZIP，并上传到对应 Gradescope 作业。确认课程页面的当前具体要求。

仅生成本地文件、仅 push GitHub、或仅点击 Grade 都不代表已完成最终上交。本文件不记录账号凭据或评分回执；这些资料可保存在被 Git 忽略的 `.local/` 或 `submission/` 目录。

## 截图要求对应位置

| 要求 | 完成位置 |
|---|---|
| GitHub repo / 计划链接 | 上方实际仓库与 `main/plans/initial_plan.md` 链接；评分前完成 push 和公开访问检查 |
| Project team | 初始计划第 1 节：SJ00425，sole contributor |
| IP definition / 数学 / 硬件加速原因 | 初始计划第 2 节 |
| 子模块与 PS/PL 分工 | 初始计划第 3 节模块表 |
| AXI4-Stream / FIFO / 共享内存及载荷 | 初始计划第 3 节接口表 |
| 比较两到三种架构方案 | 初始计划第 3 节方案 A/B/C |
| 避免单一大型模块 | M03 子模块、M04 reductions、M06 及控制/重放模块拆分 |

团队成员按本人实际情况填写，不添加虚构队员。所有性能数字明确标为初始预算，未声称已有硬件实测结果。
