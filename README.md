# harmony-umeng

本仓库面向 HarmonyOS 7.0.0／API 26，预期职责为友盟初始化、统计与分享。

当前已建立仓库治理与空 HAR 工程骨架，功能开发保持暂停。根工程仅注册 `library` 模块，`library/Index.ts` 仅含 `export {};`；没有公开 API、组件、业务逻辑、示例应用或可安装 HAP。`AppScope/` 仅提供当前 SDK 要求的工程级元数据，不注册应用模块或 Ability。

## 打开与本机构建

使用配套 API 26 SDK 的 DevEco Studio 打开本仓库根目录。工程 `targetSdkVersion`、`compatibleSdkVersion` 和 Hvigor `modelVersion` 均为 `26.0.0`。在本仓库根目录执行：

```sh
devecocli build --modules library --build-mode release
```

输出位于 `library/build/default/outputs/default/library.har`，构建产物和本机缓存不入库。该命令用于验证空 HAR 的工程配置与打包，不证明库功能、应用消费或设备行为。HAR 本身不能安装到设备。

包名为 `@unif/harmony-umeng`，`0.0.0` 仅为未发布工程占位版本。空包不发布，不提供安装命令；首次正式发行须重新核对采用的 RN 版本、中心仓历史与实际公开能力。

## 开发与验证边界

先阅读 [AGENTS.md](AGENTS.md)。恢复功能开发须有明确授权，并按所属契约核对已有能力、公开入口及实际消费者；不以空工程代替功能实现。

当前 CI 只配置工作流语法检查与 PR 标题类型检查。本地可执行 `actionlint`；完整云端 SDK 构建、OHPM 自动发布及发布凭据尚未接入。配置文件存在不表示远端 CI 已通过或仓库保护已经生效。

源码检查、自动化、空 HAR 构建、真实宿主消费、设备运行和业务验收分别记录。空骨架构建通过不作为功能验收或发布依据。

## 规范与许可来源

治理文件依据 [unif-design/.github@2a6e991697447f91127664eafb7aea80d5751194](https://github.com/unif-design/.github/blob/2a6e991697447f91127664eafb7aea80d5751194/ONBOARDING.md) 的通用规则做原生鸿蒙适配，未采用其 RN／npm 发布接线。

工程配置与忽略规则参考 [harmony-icons@63e74a8b8cf8b086870d83be4cf00fc8e221bf1a](https://github.com/unif-design/harmony-icons/tree/63e74a8b8cf8b086870d83be4cf00fc8e221bf1a) 的真实 API 26 工程，模块列表限定为本库 `library`。

本仓库及 HAR 模块采用 MIT 许可，文本继承自 [react-native-umeng@ba251ab7b1bef9d71faa8f6b61ed13fcab116959](https://github.com/unif-design/react-native-umeng/blob/ba251ab7b1bef9d71faa8f6b61ed13fcab116959/LICENSE)，完整保留原版权声明，见 [LICENSE](LICENSE)。

问题与需求通过本仓库 Issue 模板提交；安全问题按 [SECURITY.md](SECURITY.md) 私密报告。
