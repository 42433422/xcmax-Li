# 受限存储

Eden 在 2026-11-05 指定：**本批没有单独的保险库。** xcmax-Li 这个私有 Git 仓就是 A02 软著材料和 A03 冻结运行记录的存储位置。

对应正文在 `sources/xcmax/` 下，按公开冻结树的相对路径存放。逐文件决定、字节数和 SHA-256 以 `ledger/MIGRATION_LEDGER.csv` 为准。读回通过后，这些行的决定是 `migrate_private_git`，状态是 `verified`。

本文件不再把上述两组标成 `vault_or_store_required`。公开仓里的删除由其他代理处理，本代理不开公开删除 PR。

## 仍然不能进 Git 的东西

`.gitignore` 继续挡住意外提交：

- `*.pem`、`*.key`、`*.p12`、`*.pfx`、私钥文件名
- `.env` 与 `.env.*`
- 文件名中含 `secret` 或 `credential` 的路径
- `runtime_sync/` 与 `self_maintenance_*.jsonl` 的**新**文件

已经 force-add 的两份冻结 jsonl 是获批例外，保持已跟踪。忽略规则清不掉已跟踪文件，也挡不住再次 `git add -f`。新的运行记录、密钥文件和未批准路径仍然不要提交。

台账和本说明不摘录 jsonl 字段、口令、令牌或证件号。

## 本批已放入私有 Git 的原受限项

- **A02**：软著目录里原先 49 份原件和派生副本（生成器 4 份在上一批已经复制）。路径前缀 `sources/xcmax/FHD/docs/legal/software-copyright/`。
- **A03**：两份 `self_maintenance_*.jsonl`，路径前缀 `sources/xcmax/成都修茈科技有限公司/MODstore_deploy/modstore_server/data/runtime_sync/`。
- **附带复制、但不启用**：A03 的两个回写脚本，以及 Kellai 的 `docs/export_contracts.py` 与 `docs/build_wecom_legal_docs.py`。脚本只作存档，没有安装，也没有执行。

A04 证据树、A00 回执和 A07 里含生产地址或个人邮箱的文件仍是 `pending` / `pending_classify`，不在这次入库范围内。
