# Lightning概述 {#concept_fvd_fqt_z2b .concept}

MaxCompute Lightning是MaxCompute产品的交互式查询服务，支持以PostgreSQL协议及语法连接访问Maxcompute项目，让您使用熟悉的工具以标准 SQL查询分析MaxCompute项目中的数据，快速获取查询结果。

您可使用主流BI工具（如Tableau、帆软等）或SQL客户端轻松连接到MaxCompute项目，开展BI分析或即席查询。或者利用MaxCompute Lightning的快速查询特性，将项目表数据封装成API对外服务，无需数据迁移就能够支持更丰富的应用场景。

MaxCompute Lightning提供无服务器计算（Serverless）的服务方式，您无需管理任何基础设施，只需为运行的查询付费。

## 关键特性 {#section_fwm_w3j_z2b .section}

-   兼容PostgreSQL

    MaxCompute Lightning提供兼容PostgreSQL协议的JDBC/ODBC接口，所有支持PostgreSQL数据库的工具或应用使用默认驱动都可以轻松地连接到MaxCompute项目。您也可以使用更广泛的PostgreSQL生态工具来分析MaxCompute的数据。

-   显著提升性能

    针对MaxCompute表的快速查询进行了优化，特别是在小数据集、并发场景下有更好的性能表现。从而能够支撑更丰富的应用场景，如固定报表、API开放等。

-   统一的权限管理

    作为MaxCompute产品内的服务，通过MaxCompute Lightning连接到MaxCompute项目的访问完全遵循Maxcompute项目的权限体系，在访问用户权限范围内安全地查询数据。

-   开箱即用，按查询付费

    MaxCompute Lightning是在MaxCompute已有的计算资源之外提供的无服务器的计算服务，您不需要设置、管理或运维MaxCompute Lightning资源，通过MaxCompute Lightning连接后即可开展查询。

    使用MaxCompute Lightning时，只需为每次查询所实际处理的数据量付费，不查询时不产生费用。


## 系统结构 {#section_qqv_mjj_z2b .section}

作为Maxcompute的交互式查询服务，MaxCompute Lightning提供了配套的接入访问域名地址\(Endpoint\)，客户端工具及应用通过PostgreSQL驱动连接访问Lightning JDBC/ODBC接口服务，在MaxCompute项目统一的权限体系下安全地访问项目数据。

通过该服务接口连接并提交的查询任务，都将使用MaxCompute Lightning的Serverless计算资源以保障交互式查询的服务质量。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/20113/154164334011152_zh-CN.jpg)

## 应用场景 {#section_vdv_zjj_z2b .section}

-   即席查询（Ad Hoc）

    利用MaxCompute Lightning面向小规模数据集（百GB规模内）查询性能优化的特性，使用者可以直接对MaxCompute表开展低时延的查询操作，而不需要再把数据再导入到其它各种系统进行加速（比如ADS、RDS），节约资源和管理成本。

    场景特点：查询的数据对象自由不固定，逻辑相对复杂，期望快速获取查询结果并调整查询逻辑，对查询时延的要求在几十秒内。使用者往往是掌握SQL技能的数据分析师，希望使用熟悉的客户端工具来开展查询分析。

-   Reporting报表分析

    对MaxCompute项目中通过ETL加工汇总后的结果数据制作分析报表，提供给管理者和业务人员定期查看。

    场景特点：查询的数据对象通常为聚合后的结果数据， 数据量较小、查询逻辑固定且较简单。时延要求低：秒级返回（例如大部分查询不超过5秒，不同查询根据其数据规模和查询复杂度有较大差异）。

-   面向在线应用的消费场景

    直接将MaxCompute项目中的数据封装成为restful api，支撑在线应用。

    场景特点：利用MaxCompute Lightning作为加速查询引擎，结合阿里云Dataworks的[数据服务组件](cn.zh-CN/使用指南/数据服务/数据服务概览.md#)，零开发、无运维地将MaxCompute的表数据开放为API服务。


## 使用限制 {#section_h22_j3n_sfb .section}

-   Lightning[常见限制](cn.zh-CN/用户指南/Lightning/Lightning常见问题.md#)
-   [DDL、DML、查询及UDF限制](cn.zh-CN/用户指南/Lightning/约束与限制.md#)

