# 受限存储（尚未指定）

Eden 还没有指定日志、客户原件和法务原件的受限存储位置与保留期。在指定之前，下列材料的状态保持 `vault_or_store_required`。

这些正文**不得**进入公开 Git，也**不得**进入本私有 Git。台账只保留路径、大小、Git 对象 ID 和文件级 SHA-256，不摘录秘密值、证件号、会话令牌或日志字段。

## 必须排除的类别

1. **A03 真实运行记录**（2 个 jsonl）。内容含环境、用户/管理员字段、命令和 stdout/stderr 尾部。优先放到账号隔离的运行存储。公开仓将来只保留 schema 和合成样例。
2. **A02 软著原件和派生副本**（生成器除外）。DOCX、PDF、PNG、完整源码 TXT 优先进受控法务存储。本批 4 个生成器已另做内容浏览并按 `migrate_private_git` 处理，不在下表。
3. **已签署的法律原件**。本批合同稿的签章栏是空白下划线，未发现居民身份证号，因此 22 份草稿的决定是 `migrate_private_git`，不进入本表。若后续发现湿签、签章扫描或证件号，该文件改为 `vault_or_store_required`，并停止提交其正文。
4. **真正的秘密**（私钥、口令、访问令牌、云密钥）。发现即停止提交，台账记 `vault_or_store_required`，并且不记录秘密值或其可猜测哈希。

## 当前 vault_or_store_required 行

| asset_id | group | bytes | git_blob | source_path |
| --- | --- | --- | --- | --- |
| `A02-001` | A02 | 8429 | `3f575bedaf76d18da60f86baa84ad4c90efc9f2f` | `FHD/docs/legal/software-copyright/README.md` |
| `A02-002` | A02 | 3706947 | `d8a80ea970ef73f4f656b9749c61ae7b7f0c50c1` | `FHD/docs/legal/software-copyright/V10-申请材料-20260901/文档鉴别材料-用户手册.docx` |
| `A02-003` | A02 | 793 | `aded920ea4f5d8992f4866b739cc3a2b2407eeb5` | `FHD/docs/legal/software-copyright/V10-申请材料-20260901/源代码统计报告.md` |
| `A02-004` | A02 | 110713 | `91c7a913372a297650f7febe4dbdc4b44605f1d4` | `FHD/docs/legal/software-copyright/V10-申请材料-20260901/程序鉴别材料-前后30页.txt` |
| `A02-005` | A02 | 13616052 | `6ec93d12f1ca2e6e089c803e108a16e72afd9fd7` | `FHD/docs/legal/software-copyright/V10-申请材料-20260901/程序鉴别材料-完整源代码.txt` |
| `A02-006` | A02 | 3151817 | `2e684e3682963619b1b7e886196b12f25a96ee84` | `FHD/docs/legal/software-copyright/V10-申请材料-20260901/程序鉴别材料.docx` |
| `A02-007` | A02 | 1315753 | `a255373ca407a16b3ea326aadc9ce7d5f6942f6c` | `FHD/docs/legal/software-copyright/前端源代码.txt` |
| `A02-009` | A02 | 1528047 | `102fb18520b7de6a45d468fac036a210f14983a6` | `FHD/docs/legal/software-copyright/后端源代码.txt` |
| `A02-010` | A02 | 2844492 | `a3cf80c4c1b79ce31d160170fbaef35f3404e756` | `FHD/docs/legal/software-copyright/完整源代码.txt` |
| `A02-012` | A02 | 6746 | `9f76da96c68d53d6d866d4a87c32a0f842b853a4` | `FHD/docs/legal/software-copyright/源代码统计报告.md` |
| `A02-015` | A02 | 4052444 | `2a866124c81358b46e31831fc32196ca6526ebed` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/XC企业版-文档鉴别材料.docx` |
| `A02-016` | A02 | 4250789 | `f30d789fa0fdffaf06361ce4d9350fe3b24f7c74` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/XC企业版-文档鉴别材料.pdf` |
| `A02-017` | A02 | 102999 | `3cecb2f8a956375f372e1f31741d5336d346c894` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/XC企业版-程序鉴别材料-前后30页.txt` |
| `A02-018` | A02 | 2844361 | `99e330cbe25d5752d030243ed456b491e81b685d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/XC企业版-程序鉴别材料-完整源代码.txt` |
| `A02-019` | A02 | 242236 | `207e9dae1a1fafe5a4c1080ef871361c0e88b3b0` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/XC企业版-程序鉴别材料.pdf` |
| `A02-020` | A02 | 506 | `dd0d6ce66e6f36489e1694c4993a9725bc1d6f05` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/XC企业版-补正上传说明.txt` |
| `A02-021` | A02 | 459211 | `69eb69c61cd5f609a5737ec25ab4f627f569ce6e` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/render-check/doc-page-01.png` |
| `A02-022` | A02 | 398146 | `1cb4715727fb81cc09f131ba34673b36beee860b` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/render-check/doc-page-02.png` |
| `A02-023` | A02 | 521522 | `0d3811b4a5aaf9cebb3f88c7f8c234c0d56baa3a` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/render-check/doc-page-03.png` |
| `A02-024` | A02 | 239794 | `e0c1e714d809f7b816289ed3116e335544c85161` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/render-check/doc-page-10.png` |
| `A02-025` | A02 | 129018 | `c3669e2b3187ce5f0ac879f06c3f46ff3e6a3c31` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/render-check/doc-page-11.png` |
| `A02-026` | A02 | 206707 | `f89646ac85337639b67831a15a5966f3a8ffbe27` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/render-check/program-page-01.png` |
| `A02-027` | A02 | 190428 | `1868f22562f150d86e696becff505946dbc4cd3c` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/render-check/program-page-last-60.png` |
| `A02-028` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/01-login.png` |
| `A02-029` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/02-home-chat.png` |
| `A02-030` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/03-products.png` |
| `A02-031` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/04-orders.png` |
| `A02-032` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/05-create-order.png` |
| `A02-033` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/06-shipment-records.png` |
| `A02-034` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/07-customers.png` |
| `A02-035` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/08-template-preview.png` |
| `A02-036` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/09-print.png` |
| `A02-037` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/10-label-editor.png` |
| `A02-038` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/11-data-sources.png` |
| `A02-039` | A02 | 335427 | `771435cd82fc7e335fbdeada15e8232fcf652f6d` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/12-mod-store.png` |
| `A02-040` | A02 | 335415 | `4238d7eb2168a13851cd79e342ed3876f1135b15` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/13-ai-groups.png` |
| `A02-041` | A02 | 335415 | `4238d7eb2168a13851cd79e342ed3876f1135b15` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/14-settings.png` |
| `A02-042` | A02 | 335415 | `4238d7eb2168a13851cd79e342ed3876f1135b15` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/15-desktop-runtime.png` |
| `A02-043` | A02 | 335415 | `4238d7eb2168a13851cd79e342ed3876f1135b15` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/16-tools.png` |
| `A02-044` | A02 | 328282 | `da2e3c2b9f1361496d20fc1e1110c0e6c7ba0f99` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-01-业务对象.png` |
| `A02-045` | A02 | 381927 | `ced390f898631064a970be365a6648ce737e3259` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-02-组织管理.png` |
| `A02-046` | A02 | 315350 | `6bef2cd6a7a3cc902c29decc4766f417c22ae58e` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-03-业务单据.png` |
| `A02-047` | A02 | 324944 | `e056ce27a8299c163127c9b521b0e8842d912134` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-04-业务记录.png` |
| `A02-048` | A02 | 318896 | `bab511793d18182375b98618ee6e2053d3f4b426` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-05-资源库.png` |
| `A02-049` | A02 | 277942 | `0f5501e116045b7b5faa90b1f04b433097b48aef` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-06-数据来源.png` |
| `A02-050` | A02 | 280831 | `c2cc3563e2b565426004e61f3257e29eaaaae214` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-07-模板与打印.png` |
| `A02-051` | A02 | 251081 | `a80a56313a092956473d022879799a58cefe2824` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-08-打印机列表.png` |
| `A02-052` | A02 | 417257 | `b046dd248e0b91b62a85ec89b6ec9681bb559372` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-09-模板库.png` |
| `A02-053` | A02 | 159417 | `02a6fe07259fc753a5ea84f21dab7c1d9370b36c` | `FHD/docs/legal/software-copyright/补正材料-XC企业版-20260704/screenshots/click-10-系统设置.png` |
| `A03-001` | A03 | 18756 | `d92e6275176d6c88d2f309b50428efc47fb34fb9` | `成都修茈科技有限公司/MODstore_deploy/modstore_server/data/runtime_sync/self_maintenance_governance_actions.jsonl` |
| `A03-002` | A03 | 3196252 | `efc6d94b9ae0f9d938481a67b0a77c28f2962665` | `成都修茈科技有限公司/MODstore_deploy/modstore_server/data/runtime_sync/self_maintenance_loop_runs.jsonl` |

合计 51 行。SHA-256 以 `ledger/MIGRATION_LEDGER.csv` 的 `src_sha256` 为准，此处不重复一份以免两处漂移。

## 本批搁置、但还不是 vault 结论

A07 中 13 个文件含生产地址字面量或个人告警邮箱，决定为 `pending`，没有复制。A04 顶层桶为 `pending_classify`。A00 回执为 `desensitized_session_evidence` / `pending`，令牌值未写入任何提交。A01 的两个导出脚本（`A01R-*`）和 A03 回写脚本（`A03C-*`）也未复制。

指定受限存储后，需要另做读回：存储身份、权限、字节数和 SHA-256。本文件不虚构存储 URL。
