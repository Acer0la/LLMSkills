# 翻译 checkpointsave 中文母版

- 目标与思路：读取全部工作规则、工作记录和工作架构，以 `SkillMasters/checkpointsave-中文.md` 为准，更新配对英文入口，保留结构、路径和行为意图。
- 已完成：更新 `Skills/checkpointsave/SKILL.md`，对齐启动条件、交接续做、记录精简度与结束提示；同步翻译 description，未修改用户已有的中文母版变更。
- 验证：UTF-8 严格解码、英文字符、frontmatter 和目录名称检查通过；`git diff --check` 通过，仅有 LF/CRLF 提示。当前技能创建器目录未提供校验脚本，使用静态检查。
- 后续与边界：本次修改一个英文 Skill 并新增本记录，无新增模块或持久化格式；未同步全局安装副本，未创建提交。后续仍以中文母版为维护起点。
- 结束提示：检查点已记录。
