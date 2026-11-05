# 下一批公开 PR 清单

本批**没有**对公开 XCMAX 或 Kellai 开 PR，也没有改公开 CI、停用任务或删除文件。下面的步骤必须按顺序做，未知项不能进入删除批次。

## 1. 先切断 A03 回写

共同目录（只存在于公开冻结树，本仓没有正文）：

- `成都修茈科技有限公司/MODstore_deploy/modstore_server/data/runtime_sync/self_maintenance_governance_actions.jsonl`
- `成都修茈科技有限公司/MODstore_deploy/modstore_server/data/runtime_sync/self_maintenance_loop_runs.jsonl`

回写脚本（台账 `A03C-*`，本批未改）：

- `成都修茈科技有限公司/MODstore_deploy/scripts/sync-runtime-to-source.sh`
- `成都修茈科技有限公司/MODstore_deploy/scripts/install-sync-runtime-to-source-cron.sh`

安装器默认在每小时第 15 分钟以 `--commit` 运行。尚未证明某台主机已经装上或正在跑。Eden 先确认实例、任务和输出，再按批准改落点。`.gitignore` 清不掉已跟踪文件，也挡不住强制添加。

## 2. 替换消费者之后才能删公开文件

素材与能力索引（仍在公开仓，本批未改）：

- `ARCHIVE_POINTER.md`
- `FHD/docs/evidence/ARCHIVE_POINTER.md`
- `成都修茈科技有限公司/capabilities/EVIDENCE_ARCHIVE_POINTER.md`
- `成都修茈科技有限公司/data/capabilities/evidence-index.json`
- `成都修茈科技有限公司/data/capabilities/evidence-materialization.json`
- `成都修茈科技有限公司/scripts/evidence_assets.py`
- `成都修茈科技有限公司/site/data/public-site.json`

边界与凭据登记（本批不改）：

- `FHD/docs/SSOT_INDEX.md`
- `FHD/config/ssot.yaml`
- `FHD/docs/security/LOCAL_DATA_POLICY.md`
- `.github/security/credential-incidents.json`
- `.github/security/gitleaks-disposition/registry.json`
- `FHD/docs/security/CREDENTIAL_INCIDENT_CLOSEOUT.md`
- `scripts/ci/check_private_data.py`
- `scripts/ci/guard_customer_data.py`
- `scripts/ci/test_guard_customer_data.py`
- `FHD/tests/test_mods/test_synthetic_attendance_fixtures.py`
- `.github/workflows/gitleaks.yml`
- `.github/gitleaks-config.toml`

公开 PR 和 fork CI 不得读取私有原件或凭据。不要把本台账或受限路径清单贴进公开 PR 描述。

## 3. 精确删除，而不是整目录删除

只删除台账里已经 `verified`、消费者已替换、并且 Eden 再次书面批准移除的**具体路径**。

- Kellai 合同 22 份：单独提交 / PR。必要时再更新 XCMAX 里客来来子模块的 gitlink。
- XCMAX：按路径删除，不使用目录通配。
- A04 证据树仍是 `pending_classify`，不进入删除清单。
- A06 合成样本保持 `retained_public`。
- A07 里 `pending` 的拓扑/邮箱文件，未批准前不从公开仓删除，也不要补进本仓。
- A02 除 4 个已复制的生成器外，正文在受限存储落地并读回之前，不从公开仓删除。
- A03 在回写链确认停用或改道之前，不从公开仓删除。

公开 PR 要能单独恢复。不要在同一变更里重写历史、强推或改产品版本。

## 4. 合并前再读保护规则

实施时重新读取 XCMAX `main` 的实时规则。清单记录过的检查名包括：guard-temp-scripts、arch-fitness、security-scan、gitleaks、analyze (python)、analyze (javascript-typescript)、SSOT Drift Gate、Release gate (hard block)、backend-test、frontend-test、mutation-smoke。不绕过保护。

若冻结提交之后 `main` 又前进，先比对增量，再决定删除清单。不要把本冻结点的旧对象混进新的删除列表。
