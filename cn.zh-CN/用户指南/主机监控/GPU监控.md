# GPU监控 {#concept_ysn_byq_32b .concept}

本文为您介绍如何通过云监控控制台和API查询GPU监控数据。

## 监控指标说明 {#section_hcc_4mr_32b .section}

GPU相关监控指标提供如下三个维度的数据：GPU、实例、分组。

-   **GPU维度监控指标** 

    GPU维度的监控指标采集每个GPU层面的监控数据，GPU维度的监控指标如下表所示：

    |MetricName|单位|名称|dimensions|
    |:---------|:-|:-|:---------|
    |gpu\_memory\_freespace|Byte|GPU维度显存空闲量|instanceId,gpuId|
    |gpu\_memory\_totalspace|Byte|GPU维度显存总量|instanceId,gpuId|
    |gpu\_memory\_usedspace|Byte|GPU维度显存使用量|instanceId,gpuId|
    |gpu\_gpu\_usedutilization|%|GPU维度GPU使用率|instanceId,gpuId|
    |gpu\_encoder\_utilization|%|GPU维度编码器使用率|instanceId,gpuId|
    |gpu\_decoder\_utilization|%|GPU维度解码器使用率|instanceId,gpuId|
    |gpu\_gpu\_temperature|℃|GPU维度GPU温度|instanceId,gpuId|
    |gpu\_power\_readings\_power\_draw|W|GPU维度GPU功率|instanceId,gpuId|
    |gpu\_memory\_freeutilization|%|GPU维度显存空闲率|instanceId,gpuId|
    |gpu\_memory\_useutilization|%|GPU维度显存使用率|instanceId,gpuId|

-   **实例维度监控指标** 

    实例维度监控指标对单个ECS实例上的多个GPU监控数据做最大值、最小值、平均值的聚合，便于查询实例层面的整体使用情况。

    |MetricName|单位|名称|dimensions|
    |:---------|:-|:-|:---------|
    |instance\_gpu\_decoder\_utilization|%|实例维度GPU解码器使用率|instanceId|
    |instance\_gpu\_encoder\_utilization|%|实例维度GPU编码器使用率|instanceId|
    |instance\_gpu\_gpu\_temperature|℃|实例维度GPU温度|instanceId|
    |instance\_gpu\_gpu\_usedutilization|%|实例维度GPU使用率|instanceId|
    |instance\_gpu\_memory\_freespace|Byte|实例维度GPU显存空闲量|instanceId|
    |instance\_gpu\_memory\_freeutilization|%|实例维度GPU显存空闲率|instanceId|
    |instance\_gpu\_memory\_totalspace|Byte|实例维度GPU显存总量|instanceId|
    |instance\_gpu\_memory\_usedspace|Byte|实例维度GPU显存使用量|instanceId|
    |instance\_gpu\_memory\_usedutilization|%|实例维度GPU显存使用率|instanceId|
    |instance\_gpu\_power\_readings\_power\_draw|W|实例维度GPU功率|instanceId|

-   **分组维度监控指标** 

    分组维度监控指标对单个应用分组里的多个ECS 实例的监控数据做最大值、最小值、平均值的聚合，便于查询集群层面的整体使用情况。

    |MetricName|单位|名称|dimensions|
    |:---------|:-|:-|:---------|
    |group\_gpu\_decoder\_utilization|%|分组维度GPU解码器使用率|groupId|
    |group\_gpu\_encoder\_utilization|%|分组维度GPU编码器使用率|groupId|
    |group\_gpu\_gpu\_temperature|℃|分组维度GPU温度|groupId|
    |group\_gpu\_gpu\_usedutilization|%|分组维度GPU使用率|groupId|
    |group\_gpu\_memory\_freespace|Byte|分组维度GPU显存空闲量|groupId|
    |group\_gpu\_memory\_freeutilization|%|分组维度GPU显存空闲率|groupId|
    |group\_gpu\_memory\_totalspace|Byte|分组维度GPU显存总量|groupId|
    |group\_gpu\_memory\_usedspace|Byte|分组维度GPU显存使用量|groupId|
    |group\_gpu\_memory\_usedutilization|%|分组维度GPU显存使用率|groupId|
    |group\_gpu\_power\_readings\_power\_draw|W|分组维度GPU功率|groupId|


## 通过云监控控制台查询GPU监控数据 {#section_s23_l3y_ggb .section}

您在购买ECS的GPU计算型实例后，只需安装[GPU驱动](../../../../intl.zh-CN/实例/选择实例规格/GPU计算型/创建GPU计算型实例.md#)和云监控插件，即可查看GPU相关监控图表、配置监控图表或设置报警规则。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15604056036845_zh-CN.png)

**查看监控图表**

1.  登录[云监控控制台](https://cms-intl.console.aliyun.com)。
2.  单击左侧导航栏中的**主机监控**，进入主机监控页面。
3.  在实例列表中，单击实例名称，进入实例详情页面，单击**GPU监控**页签，切换至GPU监控页签，可查看GPU相关监控图表。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15604056036696_zh-CN.png)

**配置监控图表**

1.  登录[云监控控制台](https://cms-intl.console.aliyun.com)。
2.  单击左侧导航栏中**Dashboard**下的**自定义大盘**，进入**当前监控大盘**页面。
3.  单击**创建监控大盘**，弹出**创建视图组**对话框，输入监控大盘名称后，单击**创建**按钮即可。
4.  单击右上角的**添加图表**，进入添加图表页面。
5.  **选择图表类型**：从折线图、面积图、TopN表格、热力图和饼图中选择您需要的图表类型。
6.  **选择监控项**：在监控项下拉列表中，选择您需要的监控指标，配置完成后，点击**发布**即可。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/15305/15604056036698_zh-CN.png)

**设置报警规则**

为新增GPU监控指标添加报警规则，建议您通过创建模板后将模板应用于分组的方式批量添加GPU报警规则，请参考[报警模板最佳实践](../../../../intl.zh-CN/最佳实践/报警模板最佳实践.md#)。

## 通过API查询GPU监控数据 {#section_iq4_gnr_32b .section}

-   通过API查询GPU监控数据，请参考[DescribeMetricList](../../../../intl.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricList.md#)。
-   参数说明：Namespace参数的取值为acs\_ecs\_dashboard，MetricName及Dimensions的取值，请参考上述表格中的GPU指标。

