# shutter-remake

用于 Codex 的透气窗售后 Skill，支持订单12列汇总和 Damage Report 中英对照Excel。

## 本版规则

- 订单数据仅来自「每日」「全部」，禁止使用其他分表或历史缓存补值。
- B/C/D按确认格式生成：`ABC Remake`、`ABC - Example Customer Remake - RM12345`、`RM12345(NA12345)`。示例为虚构数据。
- 没有已有RM记录时，仍可从已确认原订单生成名称和编号，并注明来源。
- 客户列为空但订单名有明确客户简称前缀时提取前缀，避免B列漏填或C列重复前缀。
- 用户请求仅订单汇总时，不处理Damage Report。

## 安装和更新

仓库结构保持为：

```text
README.md
.gitignore
shutter-remake/
  SKILL.md
  references/
    order-summary.md
    damage-report.md
```

新安装：将仓库中的`shutter-remake`文件夹放入本机Codex的skills目录，通常是`~/.codex/skills/`。也可让skill-installer安装GitHub仓库中的`shutter-remake`子目录。

更新已有安装：备份后用仓库中的技能文件更新同名目录，避免在旧目录里再嵌套一层`shutter-remake`。自定义位置安装时沿用原目录或目录链接。

## 调用示例

```text
请调用 $shutter-remake，订单号为NA12345、NA12346，仅执行订单汇总。
```

```text
请调用 $shutter-remake，处理指定目录中的Damage Report，生成中英对照Excel。
```

实际文档读写和OCR需要运行环境提供相应工具。本仓库是技能规则，不包含客户业务文件或固定路径脚本。

## 上传 GitHub

解压发布包，将本README、`.gitignore`和`shutter-remake`文件夹放在仓库根目录。更新同名旧技能文件，保持上述路径，便于已有安装链接继续使用。本包不包含真实订单、客户名称、报表或聊天记录。
