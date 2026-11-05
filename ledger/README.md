# 迁移台账

`MIGRATION_LEDGER.csv` 是 xcmax-Li 上这批迁移的**唯一权威逐文件记录**。

Word、PDF 和聊天里的阅读副本（包括《XCMAX 私有资料迁移执行清单》PDF）只方便人工阅读。它们不能改写、补全或否决本 CSV 里的路径、对象 ID、字节数、哈希、决定和状态。公开仓的 SSOT 只登记已经审查过的边界规则和安全摘要，不代替本台账。

## 固定来源

| 仓库 | 固定提交 | 说明 |
| --- | --- | --- |
| `42433422/XCMAX` | `56d42cf519192ed8bfaf4f9cb2891252de484cb8` | 公开 main 的冻结点。不用更新的 tip。 |
| `42433422/kellai` | `564b2a6988636d988961549275939e0523dfb9ed` | 公开 main 的冻结点。XCMAX 子模块 gitlink 指向此提交。 |

没有把任一公开仓的完整历史镜像进本仓。

## 编码

CSV 为 UTF-8 BOM。用 Excel 打开时，把 `asset_id`、`freeze_sha`、`git_blob`、`source_path`、`src_sha256`、`dst_sha256` 列设为文本。空白单元格表示还没有该项事实，不表示通过。

`git_blob` 是 Git 对象 ID。`src_sha256` / `dst_sha256` 是文件字节的 SHA-256。两者不能互填。

## 状态

建议顺序：`inventoried` → `classified` → `copied` → `verified` →（后续才有）`consumers_updated` → `public_head_removed` → `accepted`。

本批实际用到的状态：

- `classified`：已决定迁入私有 Git，字节尚未写入本仓。
- `copied`：字节已写入工作区且与源 SHA-256 一致，尚未从本仓 HEAD 读回。
- `verified`：从本仓 HEAD 读回的字节与 `src_sha256`、`dst_sha256` 一致。
- `vault_or_store_required`：曾表示正文不能进 Git。Eden 已把本批 A02 与 A03 改存到本私有仓，那些行现在是 `migrate_private_git`。真正的密钥文件（`.pem`、`.env`、未获批的新运行记录）仍然用这个状态，并且不提交。
- `pending` / `pending_classify`：未批准复制，也未批准从公开仓删除。
- `retained_public`：继续留在公开仓。本批不删除、不复制。

`verified` 只覆盖本 CSV 里状态确实是 `verified` 的行。不能把 3,317 份候选或 16,956 份全树文件说成已经 `accepted`。

## 受众和权属

当前受众：Eden（`42433422`）本人。负责人：Eden。更宽的协作者和保留期还没有指定。Eden 已指定本私有仓作为 A02 与 A03 这一批的存储，见 `RESTRICTED_STORE.md`。
