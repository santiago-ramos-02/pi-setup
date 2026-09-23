# Optional Pi skills

Each folder is a self-contained skill bundle. A skill is guidance and supporting material that Pi can load when relevant; it is not a background service or a global requirement. Choose individual folders and copy them into `~/.pi/agent/skills/<skill-name>` (Windows: `%USERPROFILE%\.pi\agent\skills\<skill-name>`).

For example, copy `unslop` by following the commands in the root README, replacing the destination skill name as needed. Restart Pi to reload skills. Existing skills are not modified by copying a differently named skill.

- [`diagram-design`](diagram-design/README.md): create and revise technical and product diagrams.
- [`impeccable`](impeccable/README.md): frontend design, implementation, and visual quality workflows.
- [`playwright`](playwright/README.md): browser automation and UI verification through Playwright CLI.
- [`unslop`](unslop/README.md): edit writing to remove formulaic or artificial-sounding phrasing.

Review each skill's license and upstream source before redistributing its files. These copies are pinned snapshots, not self-updating installations.
