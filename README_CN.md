[English Documentation](README.md) | [中文文档](README_CN.md)
# NineData 社区版

本文详细介绍 NineData 社区版，包括社区版的产品定位以及和企业版的多维度对比，帮助您快速了解社区版。

### 什么是 NineData 社区版?

NineData 社区版是**玖章算术**推出的**永久免费**、**一键安装**的数据管理解决方案，专为开发者、初创团队、教育机构及个人用户设计。包含 NineData 的**数据库 DevOps**、**数据复制**、**数据库对比**三个核心功能。

- **数据库 DevOps**：数据库 DevOps 具有数据源管理、数据查询、SQL 规范、SQL 审核、审批流程等强大功能，帮助用户快速完成多种环境的数据管理任务，助力企业数字化转型。

- **数据复制**：NineData 数据复制支持多种同异构数据源之间的离线、实时数据复制。适合数据迁移、数据库扩缩容、数据库版本升级、异地容灾、异地多活、数据仓库及数据湖数据集成等多种业务场景。

- **数据库对比**：NineData 数据库对比功能支持对两个数据源之间的内容进行一致性对比，不一致的情况下支持自动生成变更 SQL，实现数据与结构的一致性。

NineData 社区版是一个完全离线运行的**本地化部署**版本，无需连接任何云端服务或访问 NineData 网站，所有数据与操作 **100% 留存于您的本地环境**。特别适用于无法访问外网的内网环境，完美匹配小规模企业、个人项目或学习测试等场景。

在部署上，NineData 社区版基于 Docker 技术，用户通过一条简单的命令即可在本地电脑完成安装，无论有无经验皆可快速完成部署。

### 核心价值

✅  **永久免费，高效易用**

社区版免费使用，10 分钟部署上线，全程可视化操作。

✅ **支持云虚拟机或本地部署**

可部署在云上或者本地私有网络，满足敏感业务的数据合规要求。

✅ **数据管理更安全更高效**   

15 年经验沉淀，专业的数据库 DevOps 解决方案，让研发与 DBA 协同更高效，数据更安全。

✅ **高性能实时数据迁移同步**   

基于自研 CDC 技术，专业解决数据库迁移、同步、容灾等业务需求，支持每秒数万 TPS 实时数据复制。

### 社区版 vs 企业版（原 NineData 专属集群）

|   **对比维度**    |           **社区版**            |            **企业版**            |
| :---------------: | :-----------------------------: | :------------------------------: |
|   **核心定位**    |   开发者/初创团队/个人开发者    |       中大型企业/生产环境        |
|   **部署方式**    |         Docker 单机部署         |    Docker 单机部署/分布式集群    |
| **数据库 DevOps** | 10 个数据源（功能与专业版一致） |    按许可证动态扩展（无限制）    |
|   **数据复制**    |  10 个任务（含 2 个增量任务）   |    按许可证动态扩展（无限制）    |
|   **数据对比**    |          上限 10 任务           |              无上限              |
|  **部署复杂度**   |        ⭐⭐⭐⭐⭐ 单命令部署         | ⭐⭐⭐⭐ 具备升降配、增加节点等能力  |
|   **资源消耗**    |              单机               |  集群（跨机房容灾 + 异地多活）   |
|   **技术支持**    |          文档 + 微信群          | 7x24 专属技术支持 + SLA 服务保障 |
|     **费用**      |            永久免费             |             按需付费             |

### 部署方式

**前提条件**

- 服务器中已安装 Docker。
- 服务器配置至少为 4 核 CPU / 16 GB 内存 / 200 GB 磁盘空间。
- CPU 为 Intel x86_64 平台。

**操作步骤**

1. 登录服务器的命令行窗口，执行如下命令：

   ```
   docker run -p 9999:9999 --privileged -v /opt/ninedata:/u01 --name ninedata -d swr.cn-east-3.myhuaweicloud.com/ninedata/ninedata:latest
   ```

   参数说明
   - `-p 9999:9999`：NineData 通过 9999 端口提供服务，此参数将容器的 9999 端口（冒号后）映射到服务器（冒号前），确保客户端浏览器可以直接访问到 NineData 服务。
   - `--privileged`：赋予容器运行和访问的系统权限。
   - `-v /opt/ninedata:/u01`：将服务器的 `/opt/ninedata` 目录挂载到容器的 `/u01` 目录，用于存放数据。
   - `--name ninedata`：设置容器名称为 ninedata，可自行指定其他容器名称。
   - `-d swr.cn-east-3.myhuaweicloud.com/ninedata/ninedata:latest`：NineData 的镜像地址，用于拉取 NineData 的镜像文件。

   NineData 提供了多地域镜像下载，您可以就近选择，替换上方命令中 `-d` 后面的镜像地址，以获取更快的下载速度。

   - 华北-北京：swr.cn-north-4.myhuaweicloud.com/ninedata/ninedata:latest

   - 华东-上海：swr.cn-east-3.myhuaweicloud.com/ninedata/ninedata:latest

   - 华南-广州：swr.cn-south-1.myhuaweicloud.com/ninedata/ninedata:latest
   - NineData Docker Hub 官方地址：ninedata/ninedata:latest


2. 容器启动完成后，NineData 服务会自动在容器内部署并初始化服务，该过程预计需要 5 ~ 10 分钟。通过 `docker logs -f ninedata` 命令可以查看初始化进度，等待屏幕中打印出如下提示，即代表 NineData 服务已经顺利启动。

   ![image-20250310171459303](https://docs.ninedata.cloud/assets/images/image-20250310171459303-665e43ce5b19cdebe5096822db6132ba.png)

   如果在步骤一中指定了其他容器名称，则需要把上述命令中的 `ninedata` 更换成您实际的容器名。

3. 在浏览器中输入 NineData 的连接地址即可打开 NineData 控制台的登录页，NineData 服务默认端口号为 `9999`，初始管理员账号与密码均为 `admin`。首次登录后页面会弹出修改密码窗口，请立即更改管理员密码。

   ![image-20250310171539071](https://docs.ninedata.cloud/assets/images/image-20250310171539071-f968b89d265803e304be8b5814112dc5.png)

### NineData 社区版与主流工具全方位对比
**数据库 DevOps**
<div class='table_detail_wrapper'><table><thead>
  <tr>
    <th colspan="2">对比项目</th>
    <th>NineData 社区版</th>
    <th>Archery</th>
    <th>Yearning</th>
    <th>Navicat</th>
    <th>Flyway</th>
    <th>Liquibase</th>
  </tr></thead>
<tbody>
  <tr>
    <td rowspan="4">基础能力</td>
    <td>更新迭代频率</td>
    <td>高（持续交付，周度迭代）</td>
    <td>中（季度级更新、开源社区驱动）</td>
    <td>中（不定期更新、依赖社区贡献）</td>
    <td>中（每年大版本、季度小更新）</td>
    <td>中（定期功能增强，约半年一次）</td>
    <td>中（定期维护，约季度更新）</td>
  </tr>
  <tr>
    <td>部署模式</td>
    <td>Docker 部署</td>
    <td>Docker 部署</td>
    <td>Docker 部署</td>
    <td>桌面应用</td>
    <td>CLI 集成 Java 集成</td>
    <td>CLI 集成 Java 集成</td>
  </tr>
  <tr>
    <td>支持数据源</td>
    <td>国产数据库、数仓、多云数据库（如AWS、阿里云等）、MySQL、PG、Oracle、SQL Server、Db2 等</td>
    <td>MySQL、PG、Redis 等</td>
    <td>MySQL、PG</td>
    <td>MySQL、PG、Oracle、SQL Server 等</td>
    <td>MySQL、PG、Oracle 等主流数据库</td>
    <td>主流数据库（类似 Flyway）</td>
  </tr>
  <tr>
    <td>登录方式</td>
    <td>账号密码/第三方登录/SSO(LDAP)</td>
    <td>Web 账号/LDAP/OAuth</td>
    <td>Web 账号/LDAP</td>
    <td>本地账号/许可证</td>
    <td>无（命令行）</td>
    <td>无（命令行/代码）</td>
  </tr>
  <tr>
    <td rowspan="5">SQL IDE</td>
    <td>支持语言</td>
    <td>中英文</td>
    <td>中文为主</td>
    <td>中文</td>
    <td>多语言</td>
    <td>英文</td>
    <td>英文</td>
  </tr>
  <tr>
    <td>SQL 窗口</td>
    <td>支持（强）</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持（强）</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>对象可视化管理</td>
    <td>支持</td>
    <td>部分支持（表结构）</td>
    <td>有限</td>
    <td>支持（图形化）</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>查询结果集操作</td>
    <td>导出、编辑</td>
    <td>导出、编辑</td>
    <td>导出</td>
    <td>导出、编辑、图表</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>会话隔离</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="9">SQL 审核与发布</td>
    <td>SQL 变更发布</td>
    <td>工单+自动化流程</td>
    <td>工单审批+执行</td>
    <td>工单审批</td>
    <td>直接执行</td>
    <td>直接执行迁移脚本</td>
    <td>直接执行脚本</td>
  </tr>
  <tr>
    <td>变更自动备份</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
    <td>手动备份</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>审批流程</td>
    <td>多级审批，可对接外部审批流程</td>
    <td>多级审批</td>
    <td>简单审批</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Online DDL</td>
    <td>原生支持</td>
    <td>依赖 PT-OSC 等工具</td>
    <td>依赖外部工具</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>Online DML</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>内置 SQL 规范</td>
    <td>多种数据库类型 200+ 内置规则/自定义</td>
    <td>MySQL 部分规则</td>
    <td>MySQL 部分规则</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>移动审批</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>发布流程编排</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>SQL 代码审核</td>
    <td>强（自动化审核）</td>
    <td>一般（自定义规则）</td>
    <td>一般（内置规则）</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="4">数据安全</td>
    <td>敏感数据保护</td>
    <td>智能数据分类分级，完善的数据脱敏 + 加密</td>
    <td>支持手动设置，但可轻易绕过</td>
    <td>支持手动设置，但可轻易绕过</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>权限授权模式</td>
    <td>RBAC + ABAC、管理员授权 + 主动申请</td>
    <td>RBAC、管理员授权 + 主动申请</td>
    <td>RBAC、管理员授权</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>权限模型</td>
    <td>细粒度权限（库/表/敏感列/模块/操作）</td>
    <td>项目级隔离</td>
    <td>用户级权限</td>
    <td>本地权限</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>操作审计</td>
    <td>全链路审计</td>
    <td>完整日志</td>
    <td>基础日志</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="5">高级数据处理</td>
    <td>数据导入</td>
    <td>多格式导入，语法级别可控</td>
    <td>支持 CSV/SQL</td>
    <td>支持 CSV</td>
    <td>多种格式（Excel、CSV等）</td>
    <td>通过迁移脚本</td>
    <td>通过脚本</td>
  </tr>
  <tr>
    <td>数据导出</td>
    <td>多格式导出，文件加密、水印保护</td>
    <td>支持 CSV</td>
    <td>支持 CSV</td>
    <td>多种格式导出</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>数据归档与清理</td>
    <td>自动归档（MySQL、PG）</td>
    <td>手动（MySQL）</td>
    <td>X</td>
    <td>手动</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>数据追踪与回滚</td>
    <td>自动解析 Binlog 逆向生成</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>数据生成</td>
    <td>支持，仿真模版自定义</td>
    <td>X</td>
    <td>X</td>
    <td>支持测试数据生成</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="2">性能诊断</td>
    <td>慢 SQL 性能分析</td>
    <td>深度分析 + 优化建议（MySQL、PG、Oracle、Db2）</td>
    <td>支持（MySQL）</td>
    <td></td>
    <td>基础分析</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>会话管理</td>
    <td>查看/Kill会话</td>
    <td>查看/Kill会话</td>
    <td>查看会话</td>
    <td>查看/Kill会话</td>
    <td>X</td>
    <td>X</td>
  </tr>
  </tbody></table></div>

**数据复制**
<div class='table_detail_wrapper'><table><thead>
  <tr>
    <th colspan="2">对比项</th>
    <th>NineData</th>
    <th>Canal</th>
    <th>DataX</th>
    <th>FlinkCDC</th>
  </tr></thead>
<tbody>
  <tr>
    <td rowspan="4">基础功能</td>
    <td>支持数据源种类</td>
    <td>60+</td>
    <td>1</td>
    <td>30</td>
    <td>10+</td>
  </tr>
  <tr>
    <td>可视化数据源配置管理</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>用户管理</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>权限管理</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td rowspan="13">核心功能</td>
    <td>表结构迁移</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>非表对象迁移</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>全量数据迁移</td>
    <td>支持</td>
    <td>部分支持（大表不能成功迁移）</td>
    <td>支持</td>
    <td>支持</td>
  </tr>
  <tr>
    <td>增量数据同步（DML）</td>
    <td>支持</td>
    <td>支持</td>
    <td>X</td>
    <td>支持</td>
  </tr>
  <tr>
    <td>增量结构同步（DDL）</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>仅支持 ADD Column</td>
  </tr>
  <tr>
    <td>数据过滤</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
  </tr>
  <tr>
    <td>对象名映射</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
  </tr>
  <tr>
    <td>数据转换处理</td>
    <td>支持</td>
    <td>X</td>
    <td>支持</td>
    <td>支持</td>
  </tr>
  <tr>
    <td>结构对比</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>全量数据对比</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>增量数据对比</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>修改同步对象</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>可视化任务配置与管理</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>基本没有</td>
  </tr>
  <tr>
    <td rowspan="6">任务管理</td>
    <td>任务高可用异常自动容灾（任务级、服务器级）</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>支持</td>
  </tr>
  <tr>
    <td>任务暂停与恢复</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
    <td>支持</td>
  </tr>
  <tr>
    <td>任务限流</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>告警</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>可视化监控</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
  <tr>
    <td>数据SQL查询窗口</td>
    <td>支持</td>
    <td>X</td>
    <td>X</td>
    <td>X</td>
  </tr>
</tbody></table></div>
