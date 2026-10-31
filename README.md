# NexAdmin 官方插件仓库（monorepo）

NexAdmin 后台框架的官方插件源码集中在此，每个顶级目录一个插件，结构统一为
`plugin.yaml + backend/ + web/`（与 `nexadmin plugin install` 的输入格式一致）。

| 插件 | 版本 | 版式 | 说明 |
| --- | --- | --- | --- |
| assistant | 1.1.0 | pro | AI 助手（命名会话持久化） |
| audit | 1.0.0 | pro | 数据变更审计（字段级前后对比、脱敏） |
| codegen | 1.1.0 | free | 代码生成器（读业务表或向导建表，生成模块、页面与迁移） |
| crm | 0.1.0 | free | 客户主数据与线索商机台账 |
| cron | 1.0.0 | free | 定时任务（5 段 cron、重试、执行日志） |
| formbuilder | 1.0.0 | pro | 表单构建器（可视化设计、版本化发布、xlsx 导出） |
| i18n-editor | 1.0.0 | pro | 多语言词条在线编辑与版本回滚 |
| identity | 1.0.0 | pro | 身份源（LDAP/AD 登录、CAS 单点登录） |
| imports | 0.1.0 | free | 通用 CSV / XLSX 导入中心 |
| ldap | 0.1.0 | free | LDAP/AD 登录适配 |
| maps | 0.1.0 | free | 地图服务（高德 / 百度 / 谷歌，按需启用） |
| report | 1.0.0 | pro | 报表中心 + 数据大屏 |
| saml | 0.1.0 | pro | SAML 2.0 单点登录 |
| scim | 1.0.0 | pro | SCIM 2.0 用户同步 |
| security | 1.0.0 | pro | 高级安全（TOTP、强制策略、IP 黑白名单） |
| totp | 0.1.0 | free | 两步验证（RFC 6238，兼容 Google Authenticator） |
| website | 0.6.0 | pro | 企业官网（服务端渲染 + 内容管理） |

## 发布

在 nexadmin 主仓库改插件源码后，用 `plugin pack` 产出的包内容同步对应目录到这里，
提交并打 tag（如 `cron-v1.0.1`）。主仓库的 `config/plugin-market.yaml` 用
`repo + subdir + ref` 指向本仓库，客户在后台「插件市场」一键安装/升级。

## 授权

pro 插件源码公开，运行需要发行方签发的授权文件（ed25519 签名 + 运行期闸门），
购买与签发流程见主仓库 `nexadmin-vendor/运营手册.md`。源码可见 ≠ 可用。

## 第三方插件上架

见运营手册「接入第三方插件作者」与「插件市场统一管理」：作者提交 → 审核 → 目录登记 →
发行方代签授权与收款。本仓库不接受未经审核的第三方提交。
