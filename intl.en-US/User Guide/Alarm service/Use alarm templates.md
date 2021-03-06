# Use alarm templates {#concept_bss_b45_vdb .concept}

This topic describes how to simplify the creation and management of alarm rules by using alarm templates.

## Scenarios {#section_fp5_gxp_pgb .section}

If you have multiple cloud resources \(such as ECS instances, RDS services, SLB instances, and OSS buckets\), we recommend that you use alarm templates to save alarm rules for these various resources. With having created alarm templates, you can directly apply the templates when creating alarm rules. This process can help you to simplify the creation and management of alarm rules, improving your overall O&M efficiency.

By default, CloudMonitor provides an initialized alarm template that contains common metrics for products such as ECS, RDS, SLB, and OSS, so that you can quickly and easily start to use alarm templates.

## Before you begin {#section_o4n_ksq_pgb .section}

Alarm templates are used in combination with application groups. Therefore, we recommend that you create application groups for your resources before you use alarm templates in the creation of related alarm rules. For more information about how to create application groups, see [Create application groups](reseller.en-US/User Guide/Application groups/Create application groups.md#).

## Create an alarm template {#section_ttg_s45_vdb .section}

**Note:** 

-   Alarm temples can be applied only to application groups.
-   Each Alibaba Cloud account can contain up to 100 alarm templates.
-   Each alarm template can contain up to 30 metrics.
-   The alarm template function is only a shortcut to create multiple alarm rules. Alarm rules are not bound to alarm templates. After an alarm template is modified, alarm rules generated by using this template will remain unchanged. To modify the alarm rules for different application groups in batches, you must apply the modified template to each application group.

Procedure

1.  Log on to the [CloudMonitor console](https://partners-intl.console.aliyun.com/#/cms).
2.  In the left-side navigation pane, choose **Alarms** \> **Alarm Templates**.
3.  Click **Create Alarm Template** to go to the **Create Alarm Template** page.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/6226/15498785582647_en-US.png)

4.  Enter a **Template Name** and **Description** in the **Basic Information** area.
5.  Set an alarm rule. To add more alarm rules, click **Add Rules**.
6.  Click **Add**.

## Use an alarm template {#section_kcs_dy5_vdb .section}

-   Use an alarm template when you create an application group

    When you create an application group for your resources, you can select an existing alarm template in the **MonitorAlarm** area. After you have successfully created the application group, CloudMonitor generates alarm rules for this group based on the selected alarm template.

-   Apply an alarm template directly to an existing application group

    If you have created an application group but have not created alarm rules for the group, you can create an alarm template and then quickly apply the template to the group.


