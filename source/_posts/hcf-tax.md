---
title: hcf-tax
date: 2020-08-28 17:10:30
tags:
---
# 数据库设计文档

**数据库名：** hcf_tax

**文档版本：** 1.0.0

**文档描述：** 数据库设计文档生成

| 表名                  | 说明       |
| :---: | :---: |
| [cux_ws_requests](#cux_ws_requests) | 交易数据接口表 |
| [databasechangelog](#databasechangelog) |  |
| [databasechangeloglock](#databasechangeloglock) |  |
| [manual_separation_header](#manual_separation_header) | 手工价税分离头表 |
| [manual_separation_line](#manual_separation_line) | 手工价税分离行表 |
| [pdman_db_version](#pdman_db_version) |  |
| [sys_dual](#sys_dual) | 系统预置表只能含一条数据 |
| [tax_acc_bal_inter_temp](#tax_acc_bal_inter_temp) | 科目余额接口导入表 |
| [tax_acc_balance_interface](#tax_acc_balance_interface) | 科目余额接口表（税务） |
| [tax_account_detail_interface](#tax_account_detail_interface) | 税务会计引擎接口表 |
| [tax_account_entry](#tax_account_entry) | 税务凭证数据表 |
| [tax_account_entry_status](#tax_account_entry_status) | 税务凭证数据表 |
| [tax_account_generate_rule](#tax_account_generate_rule) | 账务规则表 |
| [tax_account_rule_assign](#tax_account_rule_assign) | 账务规则分配表 |
| [tax_adjustment_interface](#tax_adjustment_interface) | 纳税调整数据接口表 |
| [tax_adjustment_interface_v270](#tax_adjustment_interface_v270) |  |
| [tax_all_version_detail](#tax_all_version_detail) | 底稿版本明细表 |
| [tax_all_version_detail_log](#tax_all_version_detail_log) | 底稿数据校验日志表 |
| [tax_balance_interface](#tax_balance_interface) | 资产负债表接口表 |
| [tax_balance_sheet](#tax_balance_sheet) | 资产负债表 |
| [tax_balance_sheet_temp](#tax_balance_sheet_temp) | 资产负债导入表 |
| [tax_bld_fa_info_basic](#tax_bld_fa_info_basic) | 资产接口正式数据表 |
| [tax_bld_fa_inventory](#tax_bld_fa_inventory) | 资产类别属性维护表 |
| [tax_bld_fa_property](#tax_bld_fa_property) | 资产关联房产表 |
| [tax_bld_property_info](#tax_bld_property_info) | 房产基础信息 |
| [tax_bld_property_info_20200707](#tax_bld_property_info_20200707) |  |
| [tax_bld_property_num](#tax_bld_property_num) | 资产关联房产表 |
| [tax_bld_rate](#tax_bld_rate) | 城镇土地使用税税率定义表 |
| [tax_bld_rent_info](#tax_bld_rent_info) | 租金登记信息表 |
| [tax_bld_rent_receipt_plan](#tax_bld_rent_receipt_plan) | 租金计划收款表 |
| [tax_bld_rent_temp](#tax_bld_rent_temp) | 租金登记信息导入表 |
| [tax_category](#tax_category) | 税种定义表 |
| [tax_cit_information](#tax_cit_information) | 税号对应企业所得税信息表 |
| [tax_cit_shareholder](#tax_cit_shareholder) | 企业所得税信息表_股东信息 |
| [tax_client](#tax_client) | 客户表 |
| [tax_client_app_temp](#tax_client_app_temp) | 客户导入表 |
| [tax_client_application](#tax_client_application) | 客户申请表 |
| [tax_client_application_other](#tax_client_application_other) | 客户申请其他信息表 |
| [tax_client_interface](#tax_client_interface) | 客户信息接口表 |
| [tax_client_interface_record](#tax_client_interface_record) | 客户接口记录表 |
| [tax_client_line](#tax_client_line) | 客户信息行表 |
| [tax_client_other](#tax_client_other) | 客户申请其他信息表 |
| [tax_commodity](#tax_commodity) | 商品编码 |
| [tax_declare_form_calcondition](#tax_declare_form_calcondition) | 纳税申报取值条件表 |
| [tax_declare_form_calitem](#tax_declare_form_calitem) | 纳税申报计算中间表 |
| [tax_declare_form_detail](#tax_declare_form_detail) | 税费申报表明细 |
| [tax_declare_form_header](#tax_declare_form_header) | 税费申报表 |
| [tax_declare_form_line](#tax_declare_form_line) | 税费申报表列表 |
| [tax_declare_form_set](#tax_declare_form_set) | 纳税申报设置表 |
| [tax_department](#tax_department) | 税务机关管理表 |
| [tax_department_v270](#tax_department_v270) |  |
| [tax_dimension](#tax_dimension) | 税务维度 |
| [tax_dimension_i18n](#tax_dimension_i18n) | 维度I18n表 |
| [tax_dimension_item](#tax_dimension_item) | 维值定义 |
| [tax_dimension_item_ass_com](#tax_dimension_item_ass_com) | 维值关联公司表 |
| [tax_dimension_item_ass_dep](#tax_dimension_item_ass_dep) | 维值关联部门表 |
| [tax_dimension_item_i18n](#tax_dimension_item_i18n) | 维值I18n表 |
| [tax_dimension_item_temp](#tax_dimension_item_temp) | 维值定义导入临时表 |
| [tax_draft_bld_a](#tax_draft_bld_a) | 房产税底稿表02 |
| [tax_draft_bld_b](#tax_draft_bld_b) | 房产税底稿表从价01 |
| [tax_draft_cell_data](#tax_draft_cell_data) | 底稿单元格数据 |
| [tax_draft_data](#tax_draft_data) | 底稿数据表 |
| [tax_draft_lut](#tax_draft_lut) | 土地使用税底稿表 |
| [tax_draft_spt_account1](#tax_draft_spt_account1) | 营业账簿底稿 |
| [tax_draft_spt_contract](#tax_draft_spt_contract) | 合同类底稿 |
| [tax_draft_spt_funding](#tax_draft_spt_funding) | 资金类营业账簿 |
| [tax_draft_tax_type](#tax_draft_tax_type) | 底稿税种类型表 |
| [tax_draft_template](#tax_draft_template) | 底稿模板 |
| [tax_draft_template_assign](#tax_draft_template_assign) | 底稿模板分配表 |
| [tax_draft_template_columns](#tax_draft_template_columns) | 底稿浮动行模板填报字段 |
| [tax_draft_template_detail](#tax_draft_template_detail) | 底稿模板明细表 |
| [tax_draft_template_dv](#tax_draft_template_dv) | 底稿浮动行模板默认值表 |
| [tax_draft_template_rule](#tax_draft_template_rule) | 底稿模板规则 |
| [tax_draft_template_script](#tax_draft_template_script) | 底稿版本规则表 |
| [tax_draft_template_script_a](#tax_draft_template_script_a) | 模板规则分配表 |
| [tax_exempt_income_interface](#tax_exempt_income_interface) | 免税收入接口表 |
| [tax_fa_info_int_temp](#tax_fa_info_int_temp) | 核算系统资产信息接口导入表 |
| [tax_fa_info_interface](#tax_fa_info_interface) | 核算系统资产信息接口 |
| [tax_file_detail](#tax_file_detail) | 税务档案资料明细表 |
| [tax_file_header](#tax_file_header) | 税务档案资料头表 |
| [tax_file_payer_permission](#tax_file_payer_permission) | 税务资料查看权限表 |
| [tax_file_send_detail](#tax_file_send_detail) | 税务资料邮寄申请明细表 |
| [tax_file_send_header](#tax_file_send_header) | 税务资料邮寄申请头表 |
| [tax_iit_ba_info_inter_temp](#tax_iit_ba_info_inter_temp) | 个税基础信息导入表 |
| [tax_iit_basic_infor_interface](#tax_iit_basic_infor_interface) | 个税基础信息接口表 |
| [tax_input_invoice_head](#tax_input_invoice_head) | 进项发票信息头表 |
| [tax_input_invoice_line](#tax_input_invoice_line) | 进项发票行表 |
| [tax_input_itinerary_detail](#tax_input_itinerary_detail) | 进项机票行程单详情表 |
| [tax_input_lemon_detail](#tax_input_lemon_detail) | 进项二手车发票详情表 |
| [tax_input_motor_detail](#tax_input_motor_detail) | 进项机动车发票详情表 |
| [tax_input_passenger_detail](#tax_input_passenger_detail) | 进项客运发票详情表 |
| [tax_input_quota_detail](#tax_input_quota_detail) | 进项定额发票详情表 |
| [tax_input_requests_certification_line](#tax_input_requests_certification_line) |  |
| [tax_input_requests_check_line](#tax_input_requests_check_line) | 税务进项接口日志信息表 |
| [tax_input_requests_header](#tax_input_requests_header) | 税务进项接口日志头表 |
| [tax_input_requests_info](#tax_input_requests_info) | 税务进项接口日志信息表 |
| [tax_input_taxi_detail](#tax_input_taxi_detail) | 进项出租车票详情表 |
| [tax_input_toll_detail](#tax_input_toll_detail) | 进项通行费详情表 |
| [tax_input_trainticket_detail](#tax_input_trainticket_detail) | 进项火车票详情表 |
| [tax_input_transfer_interface](#tax_input_transfer_interface) | 进项转出数据接口表 |
| [tax_input_transport_detail](#tax_input_transport_detail) | 进项货运发票详情表 |
| [tax_input_vat_detail](#tax_input_vat_detail) | 进项增值税发票详情表 |
| [tax_investor_info](#tax_investor_info) | 投资信息表 |
| [tax_invoice_applicant](#tax_invoice_applicant) | 申请人开票申请信息表 |
| [tax_invoice_apply_header](#tax_invoice_apply_header) | 交易流水开票申请头表 |
| [tax_invoice_apply_line](#tax_invoice_apply_line) | 交易流水开票申请行表 |
| [tax_invoice_line_expense](#tax_invoice_line_expense) | 发票行报销记录表 |
| [tax_lut_land_basic_info](#tax_lut_land_basic_info) | 土地基础信息表 |
| [tax_lut_land_info_t](#tax_lut_land_info_t) | 土地基础信息导入临时表 |
| [tax_lut_reduction_info](#tax_lut_reduction_info) | 土地使用税税收优惠信息表 |
| [tax_profit_interface](#tax_profit_interface) | 利润表接口表 |
| [tax_profit_sheet](#tax_profit_sheet) | 利润表 |
| [tax_profit_sheet_temp](#tax_profit_sheet_temp) | 利润导入表表 |
| [tax_qr_code_statics_header](#tax_qr_code_statics_header) | 静态二维码管理头表 |
| [tax_qr_code_statics_line](#tax_qr_code_statics_line) | 静态二维码管理行表 |
| [tax_rate](#tax_rate) | 税率定义表 |
| [tax_register_app_temp](#tax_register_app_temp) | 税务登记导入表 |
| [tax_register_apply](#tax_register_apply) | 税务登记申请表 |
| [tax_register_basic](#tax_register_basic) | 税务登记基础信息表 |
| [tax_requests_ocr_line](#tax_requests_ocr_line) | 税务发票OCR识别接口日志行表 |
| [tax_revenue_reduct](#tax_revenue_reduct) | 国债、基金减免税收入来源表数据表 |
| [tax_revenue_reduct_temp](#tax_revenue_reduct_temp) | 国债、基金减免税收入来源表接口表 |
| [tax_risk_degree](#tax_risk_degree) | 税务风险程度表 |
| [tax_risk_index](#tax_risk_index) | 税务风险预警指标定义表 |
| [tax_risk_inspection](#tax_risk_inspection) | 税务风险检查情况统计表 |
| [tax_risk_result](#tax_risk_result) | 风险指标结果表 |
| [tax_risk_scope](#tax_risk_scope) | 风险预警指标适用范围表 |
| [tax_small_taxes_info](#tax_small_taxes_info) | 税号对应小税种信息表 |
| [tax_spt_con_interface_temp](#tax_spt_con_interface_temp) | 印花税合同导入表 |
| [tax_spt_contract_interface](#tax_spt_contract_interface) | 印花税合同接口表 |
| [tax_spt_contract_interface_log](#tax_spt_contract_interface_log) | 印花税合同接口记录表 |
| [tax_sys_code](#tax_sys_code) | 系统代码 |
| [tax_sys_code_value](#tax_sys_code_value) | 系统代码值 |
| [tax_sys_company](#tax_sys_company) | 公司表 |
| [tax_sys_currency_rate](#tax_sys_currency_rate) | 汇率表 |
| [tax_sys_lov](#tax_sys_lov) | lov定义 |
| [tax_sys_res_center](#tax_sys_res_center) | 责任中心表 |
| [tax_taxpayer_invoicing](#tax_taxpayer_invoicing) | 关联开票人表 |
| [tax_taxpayer_org](#tax_taxpayer_org) | 税号对应机构分配表 |
| [tax_time_period](#tax_time_period) | 税务期间表 |
| [tax_value_added_tax_info](#tax_value_added_tax_info) | 税号对应增值税信息表 |
| [tax_vat_account_entry](#tax_vat_account_entry) | 临时分录表 |
| [tax_vat_cancel_apply_header](#tax_vat_cancel_apply_header) | 发票作废申请头表 |
| [tax_vat_cancel_apply_line](#tax_vat_cancel_apply_line) | 发票作废申请行表 |
| [tax_vat_deemed_sales_detail](#tax_vat_deemed_sales_detail) | 视同销售数据明细表 |
| [tax_vat_input_header](#tax_vat_input_header) | 进项发票头表 |
| [tax_vat_input_line](#tax_vat_input_line) | 进项发票行表 |
| [tax_vat_invoice](#tax_vat_invoice) | 发票头表 |
| [tax_vat_invoice_head](#tax_vat_invoice_head) | 发票头表 |
| [tax_vat_invoice_info](#tax_vat_invoice_info) | 税号发票管理配置信息表 |
| [tax_vat_invoice_item](#tax_vat_invoice_item) | 发票行表 |
| [tax_vat_invoice_line](#tax_vat_invoice_line) | 发票行表 |
| [tax_vat_invoice_line_dist](#tax_vat_invoice_line_dist) | 发票分配行表 |
| [tax_vat_invoice_line_expense](#tax_vat_invoice_line_expense) | 发票行报销记录表 |
| [tax_vat_invoice_period](#tax_vat_invoice_period) | 发票期间控制表 |
| [tax_vat_invoice_rule](#tax_vat_invoice_rule) | 开票规则定义表 |
| [tax_vat_invoicing_dimension](#tax_vat_invoicing_dimension) | 开票权限信息表 |
| [tax_vat_invoicing_site](#tax_vat_invoicing_site) | 开票点信息表 |
| [tax_vat_manual_header](#tax_vat_manual_header) | 手工开票申请头表 |
| [tax_vat_manual_line](#tax_vat_manual_line) | 手工开票申请行表 |
| [tax_vat_output_detail](#tax_vat_output_detail) | 销项明细表 |
| [tax_vat_output_detail_wait](#tax_vat_output_detail_wait) | 手工价税分离数据临时表 |
| [tax_vat_output_temp](#tax_vat_output_temp) | 销项发票导入表 |
| [tax_vat_reverse_apply_header](#tax_vat_reverse_apply_header) | 发票红冲申请头表 |
| [tax_vat_reverse_apply_line](#tax_vat_reverse_apply_line) | 发票红冲申请行表 |
| [tax_vat_reverse_header](#tax_vat_reverse_header) | 发票红冲申请头表（方正版本用） |
| [tax_vat_reverse_inf_header](#tax_vat_reverse_inf_header) | 红字信息表申请头表 |
| [tax_vat_reverse_inf_line](#tax_vat_reverse_inf_line) | 红字信息申请行表 |
| [tax_vat_reverse_line](#tax_vat_reverse_line) | 发票红冲申请行表（方正版本用） |
| [tax_vat_rule_dimension](#tax_vat_rule_dimension) | 拓展维度表 |
| [tax_vat_separate_rule](#tax_vat_separate_rule) | 价税分离规则 |
| [tax_vat_separate_rule_add](#tax_vat_separate_rule_add) | 价税分离规则拓展表 |
| [tax_vat_separate_rule_temp](#tax_vat_separate_rule_temp) | 价税分离规则导入表 |
| [tax_vat_tran_interface_record](#tax_vat_tran_interface_record) | 恒生交易数据接口表中间表 |
| [tax_vat_tran_invoice_apply_header](#tax_vat_tran_invoice_apply_header) | 交易流水开票申请头表 |
| [tax_vat_tran_invoice_apply_line](#tax_vat_tran_invoice_apply_line) | 交易流水开票申请行表 |
| [tax_vat_tran_invoice_detail](#tax_vat_tran_invoice_detail) | 待开票交易流水明细表 |
| [tax_vat_tran_write_off](#tax_vat_tran_write_off) | 核销正式表 |
| [tax_vat_trans_detail](#tax_vat_trans_detail) | 交易明细表 |
| [tax_vat_trans_interface](#tax_vat_trans_interface) | 交易接口表 |
| [tax_vat_trans_interface_temp](#tax_vat_trans_interface_temp) | 交易接口表导入临时表 |
| [tax_version_manage_inform](#tax_version_manage_inform) | 版本管理基础信息表 |
| [tax_version_table](#tax_version_table) | 版本管理关联表单信息表 |
| [tax_work_order_interface](#tax_work_order_interface) | 税务会计引擎接口表 |
| [vat_input_certificates_base](#vat_input_certificates_base) | 纳税主体认证基础信息表 |
| [vat_input_certificates_head](#vat_input_certificates_head) | 进项发票底库头表 |
| [vat_input_certificates_inf_h](#vat_input_certificates_inf_h) | 进项发票底库接口头表 |
| [vat_input_certificates_inf_l](#vat_input_certificates_inf_l) | 进项发票底库接口行表 |
| [vat_input_certificates_line](#vat_input_certificates_line) | 进项发票底库行表 |
| [vat_input_invoice_hx_logs](#vat_input_invoice_hx_logs) | 进项发票日志表 |

**表名：** <a id="cux_ws_requests">cux_ws_requests</a>

**说明：** 交易数据接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | request_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 请求日期  |
|  3   | request_wsdl_url |   varchar   | 1000 |   0    |    Y     |  N   |       | 请求URL  |
|  4   | function_name |   varchar   | 50 |   0    |    Y     |  N   |       | 方法名  |
|  5   | request_code |   varchar   | 50 |   0    |    Y     |  N   |       | 请求代码1：发票开具2：发票打印3：清单打印4：发票作废5：发票批量查询HZXXSC：红字信息表上传HZXXXZ：红字信息表下载  |
|  6   | document_number |   varchar   | 300 |   0    |    Y     |  N   |       | 单据编号  |
|  7   | status_code |   varchar   | 30 |   0    |    Y     |  N   |       | 请求状态，0：失败1：已请求2：已完成  |
|  8   | status_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 状态变更日期  |
|  9   | return_status |   varchar   | 100 |   0    |    Y     |  N   |       | 返回状态，0表示?成功，其他表示失败  |
|  10   | responsed_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 响应日期  |
|  11   | request_xml |   longtext   | 2147483647 |   0    |    Y     |  N   |       | 请求内容  |
|  12   | response_xml |   longtext   | 2147483647 |   0    |    Y     |  N   |       | 响应内容  |
|  13   | error_msg |   varchar   | 3000 |   0    |    Y     |  N   |       | 错误信息  |
|  14   | version_number |   int   | 10 |   0    |    Y     |  N   |       | 版本号  |
|  15   | created_by |   bigint   | 20 |   0    |    Y     |  N   |       | 创建用户id  |
|  16   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  17   | last_updated_by |   bigint   | 20 |   0    |    Y     |  N   |       | 最后更新用户id  |
|  18   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  19   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  20   | invoice_apply_seq |   varchar   | 100 |   0    |    Y     |  N   |       | 发票申请序列号（申请编号+两位流水号）  |

**表名：** <a id="databasechangelog">databasechangelog</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  2   | AUTHOR |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  3   | FILENAME |   varchar   | 255 |   0    |    N     |  N   |       |   |
|  4   | DATEEXECUTED |   datetime   | 19 |   0    |    N     |  N   |       |   |
|  5   | ORDEREXECUTED |   int   | 10 |   0    |    N     |  N   |       |   |
|  6   | EXECTYPE |   varchar   | 10 |   0    |    N     |  N   |       |   |
|  7   | MD5SUM |   varchar   | 35 |   0    |    Y     |  N   |       |   |
|  8   | DESCRIPTION |   varchar   | 255 |   0    |    Y     |  N   |       |   |
|  9   | COMMENTS |   varchar   | 255 |   0    |    Y     |  N   |       |   |
|  10   | TAG |   varchar   | 255 |   0    |    Y     |  N   |       |   |
|  11   | LIQUIBASE |   varchar   | 20 |   0    |    Y     |  N   |       |   |
|  12   | CONTEXTS |   varchar   | 255 |   0    |    Y     |  N   |       |   |
|  13   | LABELS |   varchar   | 255 |   0    |    Y     |  N   |       |   |
|  14   | DEPLOYMENT_ID |   varchar   | 10 |   0    |    Y     |  N   |       |   |

**表名：** <a id="databasechangeloglock">databasechangeloglock</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   int   | 10 |   0    |    N     |  Y   |       |   |
|  2   | LOCKED |   bit   | 1 |   0    |    N     |  N   |       |   |
|  3   | LOCKGRANTED |   datetime   | 19 |   0    |    Y     |  N   |       |   |
|  4   | LOCKEDBY |   varchar   | 255 |   0    |    Y     |  N   |       |   |

**表名：** <a id="manual_separation_header">manual_separation_header</a>

**说明：** 手工价税分离头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  3   | responsibility_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心ID  |
|  4   | applicant_id |   bigint   | 20 |   0    |    N     |  N   |       | 申请人ID  |
|  5   | apply_number |   varchar   | 100 |   0    |    N     |  N   |       | 申请编号  |
|  6   | apply_type |   varchar   | 100 |   0    |    Y     |  N   |       | 申请单类型  |
|  7   | apply_status |   varchar   | 100 |   0    |    Y     |  N   |       | 申请状态  |
|  8   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  11   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  13   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  14   | currency_code |   varchar   | 100 |   0    |    N     |  N   |       | 币种  |
|  15   | remark |   varchar   | 100 |   0    |    Y     |  N   |       | 备注  |
|  16   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       | 附件  |
|  17   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据OID  |
|  18   | form_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 表单OID  |
|  19   | applicant_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 申请人OID  |

**表名：** <a id="manual_separation_line">manual_separation_line</a>

**说明：** 手工价税分离行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | manual_separation_header_id |   bigint   | 20 |   0    |    N     |  N   |       | 手工价税分离头ID  |
|  3   | line_number |   varchar   | 100 |   0    |    N     |  N   |       | 行号  |
|  4   | exchange_rate |   decimal   | 21 |   2    |    Y     |  N   |       | 汇率  |
|  5   | amount |   decimal   | 21 |   2    |    Y     |  N   |       | 交易金额  |
|  6   | tran_num |   varchar   | 100 |   0    |    Y     |  N   |       | 原交易流水号  |
|  7   | tran_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 原交易流水行号  |
|  8   | accounting_type |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  9   | remark |   varchar   | 100 |   0    |    Y     |  N   |       | 备注  |
|  10   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  11   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  12   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  13   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  14   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  15   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  16   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  17   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  18   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  19   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  20   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  21   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  22   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  23   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  24   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  27   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  28   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  29   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  30   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  31   | source_system |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统  |
|  32   | data_status |   varchar   | 100 |   0    |    N     |  N   |       | 来源数据价税状态  |
|  33   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户ID  |
|  34   | tran_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |

**表名：** <a id="pdman_db_version">pdman_db_version</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | DB_VERSION |   varchar   | 256 |   0    |    Y     |  N   |       |   |
|  2   | VERSION_DESC |   varchar   | 1024 |   0    |    Y     |  N   |       |   |
|  3   | CREATED_TIME |   varchar   | 32 |   0    |    Y     |  N   |       |   |

**表名：** <a id="sys_dual">sys_dual</a>

**说明：** 系统预置表只能含一条数据

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   varchar   | 200 |   0    |    N     |  Y   |       |   |

**表名：** <a id="tax_acc_bal_inter_temp">tax_acc_bal_inter_temp</a>

**说明：** 科目余额接口导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | ledger_name |   varchar   | 300 |   0    |    Y     |  N   |       | 分类账描述  |
|  3   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  4   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 币种代码  |
|  5   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  6   | segment1_des |   varchar   | 100 |   0    |    Y     |  N   |       | 公司名称  |
|  7   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 成本中心代码  |
|  8   | segment2_des |   varchar   | 100 |   0    |    Y     |  N   |       | 成本中心名称  |
|  9   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目代码  |
|  10   | segment3_des |   varchar   | 100 |   0    |    Y     |  N   |       | 科目名称  |
|  11   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 子目代码  |
|  12   | segment4_des |   varchar   | 100 |   0    |    Y     |  N   |       | 子目名称  |
|  13   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 产品代码  |
|  14   | segment5_des |   varchar   | 100 |   0    |    Y     |  N   |       | 产品名称  |
|  15   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 项目代码  |
|  16   | segment6_des |   varchar   | 100 |   0    |    Y     |  N   |       | 项目名称  |
|  17   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 内部往来段代码  |
|  18   | segment7_des |   varchar   | 100 |   0    |    Y     |  N   |       | 内部往来段名称  |
|  19   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段1代码  |
|  20   | segment8_des |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段1名称  |
|  21   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段2代码  |
|  22   | segment9_des |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段2名称  |
|  23   | begin_balance_dr |   varchar   | 100 |   0    |    Y     |  N   |       | 期初借方余额  |
|  24   | begin_balance_cr |   varchar   | 100 |   0    |    Y     |  N   |       | 期初贷方余额  |
|  25   | begin_balance |   varchar   | 100 |   0    |    Y     |  N   |       | 期初余额  |
|  26   | period_net_dr |   varchar   | 100 |   0    |    Y     |  N   |       | 本期借方发生额  |
|  27   | period_net_cr |   varchar   | 100 |   0    |    Y     |  N   |       | 本期贷方发生额  |
|  28   | end_balance_dr |   varchar   | 100 |   0    |    Y     |  N   |       | 期末借方余额  |
|  29   | end_balance_cr |   varchar   | 100 |   0    |    Y     |  N   |       | 期末贷方余额  |
|  30   | end_balance |   varchar   | 100 |   0    |    Y     |  N   |       | 期末余额  |
|  31   | ledger_period_status |   varchar   | 100 |   0    |    Y     |  N   |       | 账套期间状态（打开、关闭）  |
|  32   | acc_direction |   varchar   | 100 |   0    |    Y     |  N   |       | 记账方向  |
|  33   | import_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 数据来源  |
|  34   | import_sys |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统  |
|  35   | sys_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期（存表日期）  |
|  36   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  37   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  38   | error_detail |   varchar   | 1000 |   0    |    Y     |  N   |       | 错误信息  |
|  39   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  40   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  41   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  42   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  43   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  44   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  45   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_acc_balance_interface">tax_acc_balance_interface</a>

**说明：** 科目余额接口表（税务）

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | ledger_name |   varchar   | 300 |   0    |    Y     |  N   |       | 分类账描述  |
|  3   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  4   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 币种代码  |
|  5   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  6   | segment1_des |   varchar   | 100 |   0    |    Y     |  N   |       | 公司名称  |
|  7   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 成本中心代码  |
|  8   | segment2_des |   varchar   | 100 |   0    |    Y     |  N   |       | 成本中心名称  |
|  9   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目代码  |
|  10   | segment3_des |   varchar   | 100 |   0    |    Y     |  N   |       | 科目名称  |
|  11   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 子目代码  |
|  12   | segment4_des |   varchar   | 100 |   0    |    Y     |  N   |       | 子目名称  |
|  13   | ledger_period_status |   varchar   | 100 |   0    |    Y     |  N   |       | 账套期间状态（打开、关闭）  |
|  14   | acc_direction |   varchar   | 100 |   0    |    Y     |  N   |       | 记账方向  |
|  15   | import_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 数据来源  |
|  16   | import_sys |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统  |
|  17   | sys_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期（存表日期）  |
|  18   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  19   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  20   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  21   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  22   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  23   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户  |
|  24   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 产品代码  |
|  25   | segment5_des |   varchar   | 100 |   0    |    Y     |  N   |       | 产品名称  |
|  26   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 项目代码  |
|  27   | segment6_des |   varchar   | 100 |   0    |    Y     |  N   |       | 项目名称  |
|  28   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 内部往来段代码  |
|  29   | segment7_des |   varchar   | 100 |   0    |    Y     |  N   |       | 内部往来段名称  |
|  30   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段1代码  |
|  31   | segment8_des |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段1名称  |
|  32   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段2代码  |
|  33   | segment9_des |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段2名称  |
|  34   | begin_balance_dr |   decimal   | 23 |   2    |    Y     |  N   |       | 期初借方余额  |
|  35   | begin_balance_cr |   decimal   | 23 |   2    |    Y     |  N   |       | 期初贷方余额  |
|  36   | begin_balance |   decimal   | 23 |   2    |    Y     |  N   |       | 期初余额  |
|  37   | period_net_dr |   decimal   | 23 |   2    |    Y     |  N   |       | 本期借方发生额  |
|  38   | period_net_cr |   decimal   | 23 |   2    |    Y     |  N   |       | 本期贷方发生额  |
|  39   | end_balance_dr |   decimal   | 23 |   2    |    Y     |  N   |       | 期末借方余额  |
|  40   | end_balance_cr |   decimal   | 23 |   2    |    Y     |  N   |       | 期末贷方余额  |
|  41   | end_balance |   decimal   | 23 |   2    |    Y     |  N   |       | 期末余额  |

**表名：** <a id="tax_account_detail_interface">tax_account_detail_interface</a>

**说明：** 税务会计引擎接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_id |   bigint   | 20 |   0    |    N     |  N   |       | 版本ID  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 税务ID  |
|  4   | version_code |   varchar   | 100 |   0    |    N     |  N   |       | 版本号  |
|  5   | version_name |   varchar   | 100 |   0    |    N     |  N   |       | 版本名称  |
|  6   | data_year |   varchar   | 30 |   0    |    N     |  N   |       | 年度  |
|  7   | declare_type |   varchar   | 30 |   0    |    N     |  N   |       | 周期精度  |
|  8   | declare_period |   varchar   | 100 |   0    |    N     |  N   |       | 申报周期  |
|  9   | date_from |   varchar   | 50 |   0    |    N     |  N   |       | 税款所属期起  |
|  10   | date_to |   varchar   | 50 |   0    |    N     |  N   |       | 税款所属期至  |
|  11   | account_date |   varchar   | 50 |   0    |    N     |  N   |       | 凭证日期  |
|  12   | account_period |   varchar   | 30 |   0    |    N     |  N   |       | 期间  |
|  13   | currency |   varchar   | 30 |   0    |    N     |  N   |       | 币种  |
|  14   | exchange_rate |   varchar   | 50 |   0    |    N     |  N   |       | 汇率  |
|  15   | exchange_rate_date |   varchar   | 50 |   0    |    N     |  N   |       | 汇率日期  |
|  16   | tax_category_type |   varchar   | 50 |   0    |    N     |  N   |       | 税种类型代码  |
|  17   | function_type |   varchar   | 50 |   0    |    N     |  N   |       | 功能类型代码  |
|  18   | transaction_type |   varchar   | 50 |   0    |    N     |  N   |       | 事务类型代码  |
|  19   | company_code |   varchar   | 50 |   0    |    N     |  N   |       | 公司代码  |
|  20   | resp_center_code |   varchar   | 50 |   0    |    N     |  N   |       | 成本中心代码  |
|  21   | account_code |   varchar   | 100 |   0    |    N     |  N   |       | 科目代码  |
|  22   | dr_cr |   varchar   | 30 |   0    |    N     |  N   |       | 借贷方向  |
|  23   | amount |   decimal   | 23 |   2    |    N     |  N   |       | 发生额  |
|  24   | fun_amount |   decimal   | 23 |   2    |    N     |  N   |       | 本币发生额  |
|  25   | account_memo |   varchar   | 100 |   0    |    N     |  N   |       | 凭证摘要  |
|  26   | line_memo |   varchar   | 100 |   0    |    Y     |  N   |       | 行备注  |
|  27   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  28   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  29   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  30   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  31   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  32   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_account_entry">tax_account_entry</a>

**说明：** 税务凭证数据表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_system |   varchar   | 30 |   0    |    N     |  N   |       | 来源系统  |
|  3   | cal_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离规则  |
|  4   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户ID  |
|  5   | client_num |   varchar   | 100 |   0    |    Y     |  N   |       | 客户编号  |
|  6   | trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  7   | trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水行号  |
|  8   | source_data_status |   varchar   | 50 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  9   | accounting_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  10   | trans_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  11   | trans_period |   varchar   | 20 |   0    |    Y     |  N   |       | 交易期间  |
|  12   | period_year |   varchar   | 20 |   0    |    Y     |  N   |       | 年份  |
|  13   | period_quarter |   varchar   | 20 |   0    |    Y     |  N   |       | 季度  |
|  14   | org_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构ID  |
|  15   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构  |
|  16   | cost_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心ID  |
|  17   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心  |
|  18   | set_of_books_id |   bigint   | 20 |   0    |    Y     |  N   |       | 账套ID  |
|  19   | set_of_books_code |   varchar   | 100 |   0    |    Y     |  N   |       | 账套代码  |
|  20   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 交易币种  |
|  21   | amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币金额  |
|  22   | functional_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币金额  |
|  23   | sales |   decimal   | 21 |   2    |    Y     |  N   |       | 原币应税销售额  |
|  24   | fun_sales |   decimal   | 21 |   2    |    Y     |  N   |       | 本币应税销售额  |
|  25   | output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 原币销项税额  |
|  26   | fun_output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 本币销项税额  |
|  27   | adjust_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币调整金额  |
|  28   | fun_adjust_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币调整金额  |
|  29   | separate_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离科目id  |
|  30   | separate_account_code |   varchar   | 100 |   0    |    Y     |  N   |       | 价税分离科目代码  |
|  31   | dr_or_cr |   varchar   | 10 |   0    |    Y     |  N   |       | 增值税科目方向  |
|  32   | tax_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 增值税科目id  |
|  33   | tax_account_code |   varchar   | 100 |   0    |    Y     |  N   |       | 增值税科目代码  |
|  34   | tax_rate_code |   varchar   | 100 |   0    |    Y     |  N   |       | 税率代码  |
|  35   | tax_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 税率  |
|  36   | source_trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水号  |
|  37   | source_trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水行号  |
|  38   | trans_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 交易说明  |
|  39   | exchange_rate_type |   varchar   | 100 |   0    |    Y     |  N   |       | 汇率类型  |
|  40   | exchange_rate_quotation |   varchar   | 100 |   0    |    Y     |  N   |       | 标价方法  |
|  41   | exchange_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 汇率  |
|  42   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段1  |
|  43   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段2  |
|  44   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段3  |
|  45   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段4  |
|  46   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段5  |
|  47   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段6  |
|  48   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段7  |
|  49   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段8  |
|  50   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段9  |
|  51   | segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段10  |
|  52   | segment11 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段11  |
|  53   | segment12 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段12  |
|  54   | segment13 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段13  |
|  55   | segment14 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段14  |
|  56   | segment15 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段15  |
|  57   | segment16 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段16  |
|  58   | segment17 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段17  |
|  59   | segment18 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段18  |
|  60   | segment19 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段19  |
|  61   | segment20 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段20  |
|  62   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  63   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  64   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  65   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  66   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  67   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  68   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  69   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  70   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  71   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  72   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  73   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  74   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  75   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  76   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  77   | data_type |   varchar   | 20 |   0    |    Y     |  N   |       | 数据类型  |
|  78   | declare_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否申报  |
|  79   | invoice_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否开票  |
|  80   | gl_acc_entry_status |   varchar   | 20 |   0    |    Y     |  N   |       | 核算平台返回状态  |
|  81   | gl_acc_error_message |   varchar   | 100 |   0    |    Y     |  N   |       | 核算平台错误信息  |
|  82   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  83   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  84   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  85   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  86   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  87   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  88   | import_flag |   varchar   | 50 |   0    |    Y     |  N   |       | 导入标识  |
|  89   | batch_id |   varchar   | 50 |   0    |    Y     |  N   |       | 批次号  |

**表名：** <a id="tax_account_entry_status">tax_account_entry_status</a>

**说明：** 税务凭证数据表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_account_entry_id |   bigint   | 20 |   0    |    Y     |  N   |       | 凭证表id  |
|  3   | batch_id |   varchar   | 50 |   0    |    Y     |  N   |       | 批次号  |
|  4   | gl_acc_entry_status |   varchar   | 100 |   0    |    Y     |  N   |       | 核算平台返回状态  |
|  5   | gl_acc_error_message |   varchar   | 100 |   0    |    Y     |  N   |       | 核算平台错误信息  |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  8   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_account_generate_rule">tax_account_generate_rule</a>

**说明：** 账务规则表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | rule_code |   varchar   | 50 |   0    |    N     |  N   |       | 账务规则代码  |
|  3   | rule_name |   varchar   | 100 |   0    |    N     |  N   |       | 账务规则名称  |
|  4   | tax_category |   varchar   | 50 |   0    |    N     |  N   |       | 税种代码  |
|  5   | tax_category_type |   varchar   | 50 |   0    |    N     |  N   |       | 税种类型代码  |
|  6   | function_type |   varchar   | 30 |   0    |    N     |  N   |       | 功能类型，计提、支付  |
|  7   | transaction_type |   varchar   | 30 |   0    |    N     |  N   |       | 事务类型，计提，结转，缴纳，手工  |
|  8   | sql_value |   text   | 65535 |   0    |    N     |  N   |       | SQL取值逻辑  |
|  9   | memo |   varchar   | 300 |   0    |    Y     |  N   |       | 备注  |
|  10   | enable_flag |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_account_rule_assign">tax_account_rule_assign</a>

**说明：** 账务规则分配表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | rule_id |   bigint   | 20 |   0    |    N     |  N   |       | 账务规则id  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  4   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  5   | resp_center_id |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  8   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_adjustment_interface">tax_adjustment_interface</a>

**说明：** 纳税调整数据接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | requisition_number |   varchar   | 200 |   0    |    Y     |  N   |       | 报账单编号  |
|  3   | header_description |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单头摘要  |
|  4   | line_description |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单行摘要  |
|  5   | je_creation_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 记账日期  |
|  6   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构  |
|  7   | expense_type |   varchar   | 100 |   0    |    Y     |  N   |       | 费用项目  |
|  8   | adjustment_code |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税调整标识  |
|  9   | adjustment_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税调整金额  |
|  10   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税人ID  |
|  11   | taxpayer_name |   varchar   | 101 |   0    |    Y     |  N   |       | 纳税人名称  |
|  12   | import_flag |   varchar   | 102 |   0    |    Y     |  N   |       | 数据来源：默认系统接口  |
|  13   | import_sys |   varchar   | 103 |   0    |    Y     |  N   |       | 来源系统：默认“费控系统”  |
|  14   | sync_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期（获取时间）  |
|  15   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  16   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |
|  17   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  18   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  19   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  20   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |

**表名：** <a id="tax_adjustment_interface_v270">tax_adjustment_interface_v270</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  N   |       |   |
|  2   | requisition_number |   varchar   | 200 |   0    |    Y     |  N   |       | 报账单编号  |
|  3   | header_description |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单头摘要  |
|  4   | line_description |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单行摘要  |
|  5   | je_creation_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 记账日期  |
|  6   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构  |
|  7   | expense_type |   varchar   | 100 |   0    |    Y     |  N   |       | 费用项目  |
|  8   | adjustment_code |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税调整标识  |
|  9   | adjustment_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税调整金额  |
|  10   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税人ID  |
|  11   | taxpayer_name |   varchar   | 101 |   0    |    Y     |  N   |       | 纳税人名称  |
|  12   | import_flag |   varchar   | 102 |   0    |    Y     |  N   |       | 数据来源：默认系统接口  |
|  13   | import_sys |   varchar   | 103 |   0    |    Y     |  N   |       | 来源系统：默认“费控系统”  |
|  14   | sync_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期（获取时间）  |
|  15   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  16   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  17   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  18   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  19   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  20   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |

**表名：** <a id="tax_all_version_detail">tax_all_version_detail</a>

**说明：** 底稿版本明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_detail_name |   varchar   | 240 |   0    |    Y     |  N   |       | 底稿版本明细名称  |
|  3   | version_id |   bigint   | 20 |   0    |    N     |  N   |       | 底稿版本id  |
|  4   | draft_type |   varchar   | 10 |   0    |    N     |  N   |       | 版本类型  |
|  5   | template_id |   bigint   | 20 |   0    |    N     |  N   |       | 底稿模板id  |
|  6   | basic_id |   bigint   | 20 |   0    |    Y     |  N   |       | 源id  |
|  7   | data_status |   varchar   | 10 |   0    |    Y     |  N   |       | 状态  |
|  8   | edit_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 更新标识  |
|  9   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  10   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  11   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  12   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  13   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  14   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  15   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  16   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  17   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  18   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  19   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  20   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  21   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  22   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  23   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  24   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  27   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  28   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  31   | sub_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 分支机构纳税主体id  |
|  32   | tax_department_id |   bigint   | 20 |   0    |    Y     |  N   |       | 所属税务机关id  |

**表名：** <a id="tax_all_version_detail_log">tax_all_version_detail_log</a>

**说明：** 底稿数据校验日志表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 版本明细ID  |
|  3   | log_type |   varchar   | 20 |   0    |    Y     |  N   |       | 日志类型(校验-CHECK/计算-CALCULATION)  |
|  4   | position_code |   varchar   | 240 |   0    |    Y     |  N   |       | 位置编码  |
|  5   | log_desc |   varchar   | 360 |   0    |    N     |  N   |       | 日志描述  |
|  6   | log_message |   text   | 65535 |   0    |    Y     |  N   |       | 字段宽度  |
|  7   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  8   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  9   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  10   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  11   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  12   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  13   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  14   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  15   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  16   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  17   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  18   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  19   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  20   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  21   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  22   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  23   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  24   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  25   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  27   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  28   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_balance_interface">tax_balance_interface</a>

**说明：** 资产负债表接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | ledger_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账套名称  |
|  3   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  4   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  5   | item_code |   int   | 10 |   0    |    Y     |  N   |       | 项目代码(项目代码取报表栏次)  |
|  6   | item_name |   varchar   | 100 |   0    |    Y     |  N   |       | 项目名称（项目为报表各个项目名称）  |
|  7   | year_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本年累计数  |
|  8   | dispose_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 处理标识  |
|  9   | error_message |   varchar   | 100 |   0    |    Y     |  N   |       | 错误信息  |
|  10   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  14   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_balance_sheet">tax_balance_sheet</a>

**说明：** 资产负债表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  3   | ledger_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账套名称  |
|  4   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  5   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  6   | item_code |   varchar   | 100 |   0    |    Y     |  N   |       | 项目代码  |
|  7   | item_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 项目名称  |
|  8   | year_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本年累计数  |
|  9   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  10   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  12   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  13   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  14   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_balance_sheet_temp">tax_balance_sheet_temp</a>

**说明：** 资产负债导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  3   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  4   | ledger_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账套名称  |
|  5   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  6   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  7   | item_code |   varchar   | 100 |   0    |    Y     |  N   |       | 项目代码(项目代码取报表栏次)  |
|  8   | item_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 项目名称（项目为报表各个项目名称）  |
|  9   | year_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 本年累计数  |
|  10   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  11   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  12   | error_detail |   varchar   | 1000 |   0    |    Y     |  N   |       | 错误信息  |
|  13   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  14   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  15   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  16   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  17   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  18   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  19   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_bld_fa_info_basic">tax_bld_fa_info_basic</a>

**说明：** 资产接口正式数据表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | asset_number |   varchar   | 200 |   0    |    N     |  N   |       | 资产编号  |
|  3   | asset_name |   varchar   | 200 |   0    |    N     |  N   |       | 资产名称  |
|  4   | asset_category_code |   varchar   | 200 |   0    |    N     |  N   |       | 资产类别属性  |
|  5   | original_taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 资产匹配纳税主体ID  |
|  6   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 实际申报纳税主体ID  |
|  7   | fa_inventory_id |   bigint   | 20 |   0    |    N     |  N   |       | 资产类别ID  |
|  8   | fa_books |   varchar   | 100 |   0    |    Y     |  N   |       | 资产账簿  |
|  9   | fa_period |   varchar   | 100 |   0    |    Y     |  N   |       | 资产折旧期间  |
|  10   | original_cost |   decimal   | 21 |   2    |    N     |  N   |       | 原始成本  |
|  11   | cost |   decimal   | 21 |   2    |    N     |  N   |       | 当前成本  |
|  12   | asset_location |   varchar   | 1000 |   0    |    Y     |  N   |       | 资产所在地点  |
|  13   | source_system |   varchar   | 100 |   0    |    N     |  N   |       | 资产来源  |
|  14   | retirement_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 报废日期  |
|  15   | retirement_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 报废标识  |
|  16   | add_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 是否新增标识  |
|  17   | declare_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 应税标识/是否申报  |
|  18   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  19   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  20   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  21   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  22   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  23   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  24   | property_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 合并标识  |
|  25   | company_id |   bigint   | 20 |   0    |    N     |  N   |       | 归属机构ID  |
|  26   | cost_change_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 成本变化标识  |
|  27   | start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 启用日期  |

**表名：** <a id="tax_bld_fa_inventory">tax_bld_fa_inventory</a>

**说明：** 资产类别属性维护表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | fa_inventory_code |   varchar   | 200 |   0    |    N     |  N   |       | 资产类别代码  |
|  3   | fa_inventory_name |   varchar   | 1000 |   0    |    N     |  N   |       | 资产类别名称  |
|  4   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  5   | enable_begin_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 启用日期从  |
|  6   | enable_end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 启用日期至  |
|  7   | asset_category_code |   varchar   | 200 |   0    |    Y     |  N   |       | 资产类别属性  |
|  8   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  10   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  12   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  13   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  14   | property_flag |   tinyint   | 4 |   0    |    Y     |  N   |   1    | 房地产标志  |

**表名：** <a id="tax_bld_fa_property">tax_bld_fa_property</a>

**说明：** 资产关联房产表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | asset_id |   bigint   | 20 |   0    |    N     |  N   |       | 资产ID  |
|  3   | asset_num |   varchar   | 100 |   0    |    N     |  N   |       | 资产编号  |
|  4   | asset_category_code |   varchar   | 200 |   0    |    N     |  N   |       | 资产类别属性（应税类）  |
|  5   | fa_period |   varchar   | 100 |   0    |    Y     |  N   |       | 资产折旧期间  |
|  6   | property_id |   bigint   | 20 |   0    |    N     |  N   |       | 房产ID  |
|  7   | share_ratio |   decimal   | 21 |   2    |    N     |  N   |       | 分摊比例  |
|  8   | share_cost |   decimal   | 21 |   2    |    N     |  N   |       | 关联房产分摊价值  |
|  9   | declare_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 房产应税标识  |
|  10   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  11   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  12   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  15   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_bld_property_info">tax_bld_property_info</a>

**说明：** 房产基础信息

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | property_num |   varchar   | 200 |   0    |    Y     |  N   |       | 实际房产证号  |
|  4   | virtua_property_num |   varchar   | 200 |   0    |    Y     |  N   |       | 虚拟房产证号  |
|  5   | property_name |   varchar   | 200 |   0    |    N     |  N   |       | 房产名称  |
|  6   | nat_tax_auth |   bigint   | 20 |   0    |    Y     |  N   |       | 所属税务机关id  |
|  7   | property_location |   varchar   | 1000 |   0    |    Y     |  N   |       | 坐落详细地址  |
|  8   | covered_area |   decimal   | 21 |   2    |    Y     |  N   |       | 房产建筑面积  |
|  9   | property_usage_code |   varchar   | 30 |   0    |    Y     |  N   |       | 房产用途值列表  |
|  10   | declare_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 房产应税标识  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  17   | get_date |   varchar   | 50 |   0    |    Y     |  N   |       | 房产取得日期  |
|  18   | disabled_date |   varchar   | 50 |   0    |    Y     |  N   |       | 停止计税日期  |

**表名：** <a id="tax_bld_property_info_20200707">tax_bld_property_info_20200707</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  N   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | property_num |   varchar   | 200 |   0    |    Y     |  N   |       | 实际房产证号  |
|  4   | virtua_property_num |   varchar   | 200 |   0    |    Y     |  N   |       | 虚拟房产证号  |
|  5   | property_name |   varchar   | 200 |   0    |    N     |  N   |       | 房产名称  |
|  6   | nat_tax_auth |   bigint   | 20 |   0    |    Y     |  N   |       | 所属税务机关id  |
|  7   | property_location |   varchar   | 1000 |   0    |    Y     |  N   |       | 坐落详细地址  |
|  8   | get_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 房产取得日期  |
|  9   | covered_area |   decimal   | 21 |   2    |    Y     |  N   |       | 房产建筑面积  |
|  10   | property_usage_code |   varchar   | 30 |   0    |    Y     |  N   |       | 房产用途值列表  |
|  11   | disabled_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 停止计税日期  |
|  12   | declare_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 房产应税标识  |
|  13   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  14   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  15   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  16   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  17   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  18   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_bld_property_num">tax_bld_property_num</a>

**说明：** 资产关联房产表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | property_id |   bigint   | 20 |   0    |    Y     |  N   |       | 房产ID  |
|  3   | line_num |   varchar   | 30 |   0    |    N     |  N   |       | 序号  |
|  4   | property_num |   varchar   | 200 |   0    |    N     |  N   |       | 产权证书号  |
|  5   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  6   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  7   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  8   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  9   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  10   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_bld_rate">tax_bld_rate</a>

**说明：** 城镇土地使用税税率定义表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | city_code |   varchar   | 300 |   0    |    N     |  N   |       | 城市代码  |
|  3   | city_name |   varchar   | 300 |   0    |    N     |  N   |       | 城市名称  |
|  4   | land_level |   varchar   | 300 |   0    |    N     |  N   |       | 土地等级  |
|  5   | tax_ratio |   decimal   | 21 |   2    |    Y     |  N   |       | 计税税率  |
|  6   | level_range |   varchar   | 4000 |   0    |    Y     |  N   |       | 等级范围  |
|  7   | remarks |   varchar   | 4000 |   0    |    Y     |  N   |       | 备注  |
|  8   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  9   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  10   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  11   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  12   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  13   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  14   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_bld_rent_info">tax_bld_rent_info</a>

**说明：** 租金登记信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | property_id |   bigint   | 20 |   0    |    N     |  N   |       | 房产ID  |
|  4   | leasee_taxpayer_num |   varchar   | 200 |   0    |    Y     |  N   |       | 承租方纳税人识别号/身份  |
|  5   | leasee_name |   varchar   | 200 |   0    |    Y     |  N   |       | 承租人名称  |
|  6   | asset_num |   varchar   | 200 |   0    |    Y     |  N   |       | 资产编号  |
|  7   | asset_name |   varchar   | 200 |   0    |    Y     |  N   |       | 资产名称  |
|  8   | covered_area |   decimal   | 21 |   2    |    N     |  N   |       | 房产建筑面积  |
|  9   | rent_area |   decimal   | 21 |   2    |    N     |  N   |       | 出租面积  |
|  10   | contract_num |   varchar   | 200 |   0    |    Y     |  N   |       | 合同编号  |
|  11   | contract_name |   varchar   | 200 |   0    |    Y     |  N   |       | 合同名称  |
|  12   | rent_begin_date |   timestamp   | 19 |   0    |    N     |  N   |       | 合同租赁日期起  |
|  13   | rent_end_date |   timestamp   | 19 |   0    |    N     |  N   |       | 合同租赁日期止  |
|  14   | contract_amount |   decimal   | 21 |   2    |    N     |  N   |       | 合同不含税金额  |
|  15   | rent_receipt_amount |   decimal   | 21 |   2    |    N     |  N   |       | 租金收入  |
|  16   | termi_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 提前终止日期  |
|  17   | manual_flag |   varchar   | 30 |   0    |    N     |  N   |       | 是否手工分期  |
|  18   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  19   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  20   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  21   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  22   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  23   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_bld_rent_receipt_plan">tax_bld_rent_receipt_plan</a>

**说明：** 租金计划收款表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | line_num |   bigint   | 20 |   0    |    N     |  N   |       | 序号  |
|  3   | rent_id |   bigint   | 20 |   0    |    N     |  N   |       | 租金登记信息ID  |
|  4   | rent_period |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  5   | share_ratio |   decimal   | 21 |   2    |    N     |  N   |       | 比例  |
|  6   | receipt_plan_amount |   decimal   | 21 |   2    |    N     |  N   |       | 计划收款金额  |
|  7   | receipt_amount |   decimal   | 21 |   2    |    N     |  N   |       | 实际收款金额  |
|  8   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  10   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  12   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  13   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_bld_rent_temp">tax_bld_rent_temp</a>

**说明：** 租金登记信息导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  3   | property_id |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  4   | leasee_taxpayer_num |   varchar   | 200 |   0    |    Y     |  N   |       | 承租方纳税人识别号/身份  |
|  5   | leasee_name |   varchar   | 200 |   0    |    Y     |  N   |       | 承租人名称  |
|  6   | asset_num |   varchar   | 200 |   0    |    Y     |  N   |       | 资产编号  |
|  7   | asset_name |   varchar   | 200 |   0    |    Y     |  N   |       | 资产名称  |
|  8   | covered_area |   decimal   | 21 |   2    |    Y     |  N   |       |   |
|  9   | rent_area |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  10   | contract_num |   varchar   | 200 |   0    |    Y     |  N   |       | 合同编号  |
|  11   | contract_name |   varchar   | 200 |   0    |    Y     |  N   |       |   |
|  12   | rent_begin_date |   timestamp   | 19 |   0    |    Y     |  N   |       |   |
|  13   | rent_end_date |   timestamp   | 19 |   0    |    Y     |  N   |       |   |
|  14   | contract_amount |   decimal   | 21 |   2    |    Y     |  N   |       |   |
|  15   | rent_receipt_amount |   decimal   | 21 |   2    |    Y     |  N   |       |   |
|  16   | termi_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 提前终止日期  |
|  17   | manual_flag |   varchar   | 30 |   0    |    Y     |  N   |       |   |
|  18   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  19   | batch_number |   varchar   | 36 |   0    |    Y     |  N   |       | 批次号  |
|  20   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  21   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  22   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  23   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  24   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  25   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  27   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_category">tax_category</a>

**说明：** 税种定义表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_category_code |   varchar   | 30 |   0    |    N     |  N   |       | 税种代码  |
|  3   | tax_category_name |   varchar   | 100 |   0    |    N     |  N   |       | 税种名称  |
|  4   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  10   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_cit_information">tax_cit_information</a>

**说明：** 税号对应企业所得税信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | declare_type |   varchar   | 100 |   0    |    Y     |  N   |       | 申报模式  |
|  4   | declare_level |   varchar   | 100 |   0    |    Y     |  N   |       | 申报层级  |
|  5   | parent_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 上级纳税主体ID  |
|  6   | listed_company_type |   varchar   | 100 |   0    |    Y     |  N   |       | 企业类型  |
|  7   | advance_declare_period |   varchar   | 100 |   0    |    Y     |  N   |       | 预缴申报周期  |
|  8   | advance_declare_type |   varchar   | 100 |   0    |    Y     |  N   |       | 预缴申报方式  |
|  9   | tax_apportion_flag |   tinyint   | 4 |   0    |    Y     |  N   |   1    | 是否参与税款分摊  |
|  10   | head_office_ratio |   decimal   | 21 |   2    |    Y     |  N   |       | 预缴-总机构分摊比例  |
|  11   | head_office_f_ratio |   decimal   | 21 |   2    |    Y     |  N   |       | 预缴-总机构财政集中分配比例  |
|  12   | branch_ratio |   decimal   | 21 |   2    |    Y     |  N   |       | 预缴-分支机构分摊比例  |
|  13   | head_office_f_ratio_clear |   decimal   | 21 |   2    |    Y     |  N   |       | 汇缴-总机构财政集中分配比例  |
|  14   | head_office_ratio_clear |   decimal   | 21 |   2    |    Y     |  N   |       | 汇缴-总机构分摊比例  |
|  15   | branch_ratio_clear |   decimal   | 21 |   2    |    Y     |  N   |       | 汇缴-分支机构分摊比例  |
|  16   | employees_number |   bigint   | 20 |   0    |    Y     |  N   |       | 期末从业人数  |
|  17   | total_assets |   bigint   | 20 |   0    |    Y     |  N   |       | 资产总额（万元）  |
|  18   | west_deve_prefere_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否享受西部大开发优惠政策  |
|  19   | small_micro_business_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否小微企业  |
|  20   | high_tech_enterprises_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否高薪技术企业  |
|  21   | company_tax_red_range |   decimal   | 21 |   2    |    Y     |  N   |       | 企业减征幅度  |
|  22   | industry_code |   varchar   | 300 |   0    |    Y     |  N   |       | 所属行业明细代码  |
|  23   | company_type |   varchar   | 300 |   0    |    Y     |  N   |       | 上市公司类型  |
|  24   | accounting_standards |   varchar   | 100 |   0    |    Y     |  N   |       | 适用的会计准则或会计制度  |
|  25   | non_monetary_assets_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否发生非货币性资产投资递延事项  |
|  26   | technology_shares_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否发生技术入股递延纳税事项  |
|  27   | asset_transfer_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否发生资产（股权）划转特殊纳税事项  |
|  28   | chinese_holding_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否居民企业为境外中资控股  |
|  29   | equity_investment_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否从事股权投资业务  |
|  30   | foreign_transactions_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否存在境外关联交易  |
|  31   | limits_industry_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否从事国家限制和禁止行业  |
|  32   | company_restructuring_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否发生企业重组  |
|  33   | company_restructuring_type |   varchar   | 300 |   0    |    Y     |  N   |       | 企业重组交易类型  |
|  34   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  35   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  36   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  37   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  38   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  39   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  40   | tax_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税率表ID  |

**表名：** <a id="tax_cit_shareholder">tax_cit_shareholder</a>

**说明：** 企业所得税信息表_股东信息

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | num |   bigint   | 20 |   0    |    Y     |  N   |       | 序号  |
|  4   | shareholder_name |   varchar   | 300 |   0    |    Y     |  N   |       | 股东名称  |
|  5   | id_type |   varchar   | 100 |   0    |    Y     |  N   |       | 证件类型  |
|  6   | id_number |   varchar   | 300 |   0    |    Y     |  N   |       | 证件号码  |
|  7   | investment_ratio |   decimal   | 21 |   2    |    Y     |  N   |       | 投资比例  |
|  8   | investment_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 权益性投资收益金额  |
|  9   | nationality |   varchar   | 4000 |   0    |    Y     |  N   |       | 国籍（注册地址）  |
|  10   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  11   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  12   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  15   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_client">tax_client</a>

**说明：** 客户表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | client_number |   varchar   | 100 |   0    |    Y     |  N   |       | 客户编号  |
|  3   | client_name |   varchar   | 100 |   0    |    N     |  N   |       | 客户名称  |
|  4   | client_type |   varchar   | 100 |   0    |    Y     |  N   |       | 客户类型  |
|  5   | credentials_type |   varchar   | 100 |   0    |    Y     |  N   |       | 证件类型  |
|  6   | credentials_number |   varchar   | 100 |   0    |    Y     |  N   |       | 证件号码  |
|  7   | contacts |   varchar   | 100 |   0    |    Y     |  N   |       | 联系人  |
|  8   | contacts_phone |   varchar   | 100 |   0    |    Y     |  N   |       | 联系人电话  |
|  9   | contacts_address |   varchar   | 100 |   0    |    Y     |  N   |       | 联系地址  |
|  10   | taxpayer_name |   varchar   | 400 |   0    |    Y     |  N   |       | 纳税人名称  |
|  11   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  12   | tax_qualification |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税资质  |
|  13   | address |   varchar   | 400 |   0    |    Y     |  N   |       | 地址  |
|  14   | phone |   varchar   | 100 |   0    |    Y     |  N   |       | 电话  |
|  15   | opening_bank |   varchar   | 300 |   0    |    Y     |  N   |       | 银行开户行  |
|  16   | account_number |   varchar   | 100 |   0    |    Y     |  N   |       | 银行账号  |
|  17   | email |   varchar   | 100 |   0    |    Y     |  N   |       | 邮箱  |
|  18   | cellphone |   varchar   | 100 |   0    |    Y     |  N   |       | 手机  |
|  19   | mail_address |   varchar   | 400 |   0    |    Y     |  N   |       | 邮寄地址  |
|  20   | addressee |   varchar   | 100 |   0    |    Y     |  N   |       | 收件人  |
|  21   | addressee_phone |   varchar   | 100 |   0    |    Y     |  N   |       | 收件人电话  |
|  22   | import_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 数据来源：手工、系统接口  |
|  23   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |
|  24   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  25   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  26   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  27   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  28   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_client_app_temp">tax_client_app_temp</a>

**说明：** 客户导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | client_name |   varchar   | 100 |   0    |    Y     |  N   |       | 客户名称  |
|  3   | client_type |   varchar   | 30 |   0    |    Y     |  N   |       | 客户类型  |
|  4   | credentials_type |   varchar   | 30 |   0    |    Y     |  N   |       | 证件类型  |
|  5   | credentials_number |   varchar   | 100 |   0    |    Y     |  N   |       | 证件号码  |
|  6   | contacts |   varchar   | 100 |   0    |    Y     |  N   |       | 联系人  |
|  7   | contacts_phone |   varchar   | 100 |   0    |    Y     |  N   |       | 联系人电话  |
|  8   | contacts_address |   varchar   | 100 |   0    |    Y     |  N   |       | 联系地址  |
|  9   | taxpayer_name |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人名称  |
|  10   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  11   | tax_qualification |   varchar   | 50 |   0    |    Y     |  N   |       | 纳税资质  |
|  12   | address |   varchar   | 1000 |   0    |    Y     |  N   |       | 地址  |
|  13   | phone |   varchar   | 50 |   0    |    Y     |  N   |       | 电话  |
|  14   | opening_bank |   varchar   | 200 |   0    |    Y     |  N   |       | 银行开户行  |
|  15   | account_number |   varchar   | 50 |   0    |    Y     |  N   |       | 银行账号  |
|  16   | email |   varchar   | 50 |   0    |    Y     |  N   |       | 邮箱  |
|  17   | cellphone |   varchar   | 50 |   0    |    Y     |  N   |       | 手机  |
|  18   | addressee |   varchar   | 50 |   0    |    Y     |  N   |       | 收件人  |
|  19   | addressee_phone |   varchar   | 50 |   0    |    Y     |  N   |       | 收件人电话  |
|  20   | mail_address |   varchar   | 50 |   0    |    Y     |  N   |       | 邮寄地址  |
|  21   | order_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  22   | batch_number |   varchar   | 36 |   0    |    Y     |  N   |       | 批次号  |
|  23   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  24   | error_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 错误标识  |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  27   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  28   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_client_application">tax_client_application</a>

**说明：** 客户申请表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | application_code |   varchar   | 100 |   0    |    N     |  N   |       | 申请编码  |
|  3   | transaction_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型  |
|  4   | transaction_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务状态  |
|  5   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构ID  |
|  6   | employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人ID  |
|  7   | client_number |   varchar   | 100 |   0    |    Y     |  N   |       | 客户编号  |
|  8   | client_name |   varchar   | 100 |   0    |    N     |  N   |       | 客户名称  |
|  9   | client_type |   varchar   | 20 |   0    |    Y     |  N   |       | 客户类型  |
|  10   | credentials_type |   varchar   | 20 |   0    |    Y     |  N   |       | 证件类型  |
|  11   | credentials_number |   varchar   | 100 |   0    |    Y     |  N   |       | 证件号码  |
|  12   | contacts |   varchar   | 100 |   0    |    Y     |  N   |       | 联系人  |
|  13   | contacts_phone |   varchar   | 100 |   0    |    Y     |  N   |       | 联系人电话  |
|  14   | contacts_address |   varchar   | 100 |   0    |    Y     |  N   |       | 联系地址  |
|  15   | taxpayer_name |   varchar   | 400 |   0    |    Y     |  N   |       | 纳税人名称  |
|  16   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  17   | tax_qualification |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税资质  |
|  18   | address |   varchar   | 400 |   0    |    Y     |  N   |       | 地址  |
|  19   | phone |   varchar   | 100 |   0    |    Y     |  N   |       | 电话  |
|  20   | opening_bank |   varchar   | 300 |   0    |    Y     |  N   |       | 银行开户行  |
|  21   | account_number |   varchar   | 100 |   0    |    Y     |  N   |       | 银行账号  |
|  22   | email |   varchar   | 100 |   0    |    Y     |  N   |       | 邮箱  |
|  23   | cellphone |   varchar   | 100 |   0    |    Y     |  N   |       | 手机  |
|  24   | mail_address |   varchar   | 400 |   0    |    Y     |  N   |       | 邮寄地址  |
|  25   | addressee |   varchar   | 100 |   0    |    Y     |  N   |       | 收件人  |
|  26   | addressee_phone |   varchar   | 100 |   0    |    Y     |  N   |       | 收件人电话  |
|  27   | import_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 数据来源：手工、系统接口  |
|  28   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |
|  29   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  30   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  31   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  32   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  33   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  34   | document_oid |   varchar   | 36 |   0    |    Y     |  N   |       | 单据OID  |
|  35   | form_oid |   varchar   | 36 |   0    |    Y     |  N   |       | 表单OID  |
|  36   | application_oid |   varchar   | 50 |   0    |    Y     |  N   |       | 申请人OID  |
|  37   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户id  |
|  38   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       | 附件  |

**表名：** <a id="tax_client_application_other">tax_client_application_other</a>

**说明：** 客户申请其他信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | application_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请id  |
|  3   | dimension_id |   bigint   | 20 |   0    |    Y     |  N   |       | 维度id  |
|  4   | dimension_value_id |   bigint   | 20 |   0    |    Y     |  N   |       | 维值id  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  10   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_client_interface">tax_client_interface</a>

**说明：** 客户信息接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | client_number_original |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统客户编号  |
|  3   | client_tax_name |   varchar   | 500 |   0    |    N     |  N   |       | 客户名称  |
|  4   | client_tax_type |   varchar   | 30 |   0    |    Y     |  N   |       | 客户类型（01:企业;02:个人）  |
|  5   | document_type |   varchar   | 50 |   0    |    Y     |  N   |       | 证件类型  |
|  6   | document_num |   varchar   | 200 |   0    |    Y     |  N   |       | 证件号码  |
|  7   | contacts |   varchar   | 100 |   0    |    Y     |  N   |       | 联系人  |
|  8   | contacts_phone |   varchar   | 30 |   0    |    Y     |  N   |       | 联系人电话  |
|  9   | contacts_add |   varchar   | 4000 |   0    |    Y     |  N   |       | 联系人地址  |
|  10   | taxpayer_name |   varchar   | 500 |   0    |    Y     |  N   |       | 纳税人名称  |
|  11   | client_tax_num |   varchar   | 30 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  12   | taxpayer_type |   varchar   | 30 |   0    |    Y     |  N   |       | 纳税人资质（01：一般纳税人:02：小规模纳税人）  |
|  13   | client_tax_add |   varchar   | 4000 |   0    |    Y     |  N   |       | 地址  |
|  14   | client_tax_tel |   varchar   | 30 |   0    |    Y     |  N   |       | 电话  |
|  15   | client_tax_bank |   varchar   | 500 |   0    |    Y     |  N   |       | 银行开户行  |
|  16   | client_tax_acc |   varchar   | 100 |   0    |    Y     |  N   |       | 银行账号  |
|  17   | client_email |   varchar   | 50 |   0    |    Y     |  N   |       | 邮箱（电子发票）  |
|  18   | client_phone |   varchar   | 30 |   0    |    Y     |  N   |       | 手机（电子发票）  |
|  19   | mail_address |   varchar   | 4000 |   0    |    Y     |  N   |       | 邮寄地址  |
|  20   | addressee |   varchar   | 30 |   0    |    Y     |  N   |       | 收件人  |
|  21   | addressee_phone |   varchar   | 30 |   0    |    Y     |  N   |       | 收件人电话  |
|  22   | org |   varchar   | 30 |   0    |    Y     |  N   |       | 归属机构（核算机构代码）  |
|  23   | project |   varchar   | 500 |   0    |    Y     |  N   |       | 项目  |
|  24   | import_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 数据来源：默认“系统接口”  |
|  25   | import_sys |   varchar   | 30 |   0    |    Y     |  N   |       | 来源系统：01：恒生系统，02：投行系统  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  27   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  28   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  31   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |
|  32   | import_success_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 导入成功标识  |
|  33   | error_reason |   varchar   | 300 |   0    |    Y     |  N   |       | 导入失败原因  |

**表名：** <a id="tax_client_interface_record">tax_client_interface_record</a>

**说明：** 客户接口记录表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | source_sys |   varchar   | 10 |   0    |    Y     |  N   |       | 来源系统01-恒生02-投行  |
|  2   | dw_date |   bigint   | 20 |   0    |    Y     |  N   |       | 数据日期  |
|  3   | trans_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据处理日期  |
|  4   | import_sum |   bigint   | 20 |   0    |    Y     |  N   |       | 导入记录数  |

**表名：** <a id="tax_client_line">tax_client_line</a>

**说明：** 客户信息行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户信息ID  |
|  3   | client_number_original |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统客户编号  |
|  4   | import_sys |   varchar   | 50 |   0    |    Y     |  N   |       | 来源系统  |
|  5   | process_batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 税务系统批次号  |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  8   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_client_other">tax_client_other</a>

**说明：** 客户申请其他信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | application_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请id  |
|  3   | dimension_id |   bigint   | 20 |   0    |    Y     |  N   |       | 维度id  |
|  4   | dimension_value_id |   bigint   | 20 |   0    |    Y     |  N   |       | 维值id  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  10   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_commodity">tax_commodity</a>

**说明：** 商品编码

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | commodity_code |   varchar   | 30 |   0    |    N     |  N   |       | 商品编码  |
|  3   | commodity_name |   varchar   | 100 |   0    |    N     |  N   |       | 货物或劳务名称  |
|  4   | commodity_abb |   varchar   | 100 |   0    |    Y     |  N   |       | 商品和服务分类简称  |
|  5   | remarks |   varchar   | 3000 |   0    |    Y     |  N   |       | 备注  |
|  6   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  7   | deleted |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 删除标识  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  13   | vat_management |   varchar   | 100 |   0    |    Y     |  N   |       | 增值税特殊管理  |
|  14   | preferential_policy |   tinyint   | 4 |   0    |    N     |  N   |   0    | 优惠政策标识  |
|  15   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_declare_form_calcondition">tax_declare_form_calcondition</a>

**说明：** 纳税申报取值条件表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   decimal   | 11 |   0    |    N     |  Y   |       |   |
|  2   | condition1 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件1  |
|  3   | condition2 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件2  |
|  4   | condition3 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件3  |
|  5   | condition4 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件4  |
|  6   | condition5 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件5  |
|  7   | condition6 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件6  |
|  8   | condition7 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件7  |
|  9   | condition8 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件8  |
|  10   | condition9 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件9  |
|  11   | condition10 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件10  |
|  12   | condition11 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件11  |
|  13   | condition12 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件12  |
|  14   | condition13 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件13  |
|  15   | condition14 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件14  |
|  16   | condition15 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件15  |
|  17   | condition16 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件16  |
|  18   | condition17 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件17  |
|  19   | condition18 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件18  |
|  20   | condition19 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件19  |
|  21   | condition20 |   varchar   | 300 |   0    |    Y     |  N   |       | 条件20  |
|  22   | tenant_id |   decimal   | 39 |   0    |    Y     |  N   |       | 租户id  |
|  23   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  24   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  25   | created_by |   decimal   | 39 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  27   | last_updated_by |   decimal   | 39 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_declare_form_calitem">tax_declare_form_calitem</a>

**说明：** 纳税申报计算中间表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   decimal   | 11 |   0    |    N     |  Y   |       |   |
|  2   | batch_id |   decimal   | 11 |   0    |    Y     |  N   |       | 批次号  |
|  3   | declare_form_id |   varchar   | 100 |   0    |    Y     |  N   |       | 申报表标识  |
|  4   | declare_form_set_id |   decimal   | 11 |   0    |    Y     |  N   |       | 申报表设置行ID  |
|  5   | coordinate |   varchar   | 300 |   0    |    Y     |  N   |       | 坐标  |
|  6   | coordinate_value |   varchar   | 4000 |   0    |    Y     |  N   |       | 坐标值  |
|  7   | tenant_id |   decimal   | 39 |   0    |    Y     |  N   |       | 租户id  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   decimal   | 39 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   decimal   | 39 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_declare_form_detail">tax_declare_form_detail</a>

**说明：** 税费申报表明细

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | declare_form_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申报表列表ID  |
|  3   | coordinate |   varchar   | 300 |   0    |    Y     |  N   |       | 坐标  |
|  4   | coordinate_value |   varchar   | 4000 |   0    |    Y     |  N   |       | 坐标值  |
|  5   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  6   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  7   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  8   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  9   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  10   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_declare_form_header">tax_declare_form_header</a>

**说明：** 税费申报表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | declare_number |   varchar   | 300 |   0    |    Y     |  N   |       | 申报表编号  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  4   | tax_category_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税种ID  |
|  5   | declare_form_type |   varchar   | 300 |   0    |    Y     |  N   |       | 申报表类型  |
|  6   | year |   varchar   | 100 |   0    |    Y     |  N   |       | 年份  |
|  7   | declare_cycle |   varchar   | 100 |   0    |    Y     |  N   |       | 申报周期  |
|  8   | declare_period |   varchar   | 100 |   0    |    Y     |  N   |       | 申报期间  |
|  9   | description |   varchar   | 3000 |   0    |    Y     |  N   |       | 说明  |
|  10   | create_mode |   varchar   | 100 |   0    |    Y     |  N   |       | 创建方式  |
|  11   | his_declare_from_id |   bigint   | 20 |   0    |    Y     |  N   |       | 历史申报表ID  |
|  12   | edition_type |   varchar   | 100 |   0    |    Y     |  N   |       | 版本状态  |
|  13   | audit_status |   varchar   | 100 |   0    |    Y     |  N   |       | 审批状态  |
|  14   | archive_status |   varchar   | 100 |   0    |    Y     |  N   |       | 归档状态  |
|  15   | archive_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 归档日期  |
|  16   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  17   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  18   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  19   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  20   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  21   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  22   | applicant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人ID  |
|  23   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据oid  |
|  24   | applicant_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 申请人OID  |
|  25   | form_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 表单oid  |
|  26   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  27   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       | 附件  |
|  28   | apply_type |   varchar   | 100 |   0    |    Y     |  N   |       | 事务类型（税费申报表申请）  |

**表名：** <a id="tax_declare_form_line">tax_declare_form_line</a>

**说明：** 税费申报表列表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | declare_from_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申报表ID  |
|  3   | template_code |   varchar   | 300 |   0    |    Y     |  N   |       | 模板代码  |
|  4   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_declare_form_set">tax_declare_form_set</a>

**说明：** 纳税申报设置表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   decimal   | 11 |   0    |    N     |  Y   |       |   |
|  2   | declare_form_id |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税申报表标识  |
|  3   | coordinate |   varchar   | 300 |   0    |    Y     |  N   |       | 坐标  |
|  4   | calsequence |   decimal   | 39 |   0    |    Y     |  N   |       | 计算顺序  |
|  5   | cal_type |   varchar   | 300 |   0    |    Y     |  N   |       | 计算类型（item根据where条件取值、cal根据项计算）  |
|  6   | cal_res_item |   varchar   | 4000 |   0    |    Y     |  N   |       | 计算结果项（item使用，mapper查询的结果项）  |
|  7   | cal_condition |   varchar   | 4000 |   0    |    Y     |  N   |       | 计算条件（item使用，mapper查询的where条件）  |
|  8   | cal_declare_form_id |   varchar   | 100 |   0    |    Y     |  N   |       | 计算取值表（cal使用）  |
|  9   | cal_sign |   varchar   | 100 |   0    |    Y     |  N   |       | 计算方向（cal使用，1、-1）  |
|  10   | cal_item |   varchar   | 3000 |   0    |    Y     |  N   |       | 计算项（cal使用，提前计算的项值）  |
|  11   | tenant_id |   decimal   | 39 |   0    |    Y     |  N   |       | 租户id  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   decimal   | 39 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   decimal   | 39 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_department">tax_department</a>

**说明：** 税务机关管理表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_department_code |   varchar   | 30 |   0    |    N     |  N   |       | 税务机关代码  |
|  3   | tax_department |   varchar   | 100 |   0    |    Y     |  N   |       | 税务机关名称  |
|  4   | tax_department_address |   varchar   | 100 |   0    |    N     |  N   |       | 税务机关地址  |
|  5   | telephone |   varchar   | 50 |   0    |    Y     |  N   |       | 联系方式  |
|  6   | enable_flag |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  8   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_department_v270">tax_department_v270</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  N   |       |   |
|  2   | tax_department_code |   varchar   | 30 |   0    |    N     |  N   |       | 税务机关代码  |
|  3   | tax_department |   varchar   | 100 |   0    |    Y     |  N   |       | 税务机关名称  |
|  4   | tax_department_address |   varchar   | 100 |   0    |    N     |  N   |       | 税务机关地址  |
|  5   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  6   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  7   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  8   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  10   | enable_flag |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  11   | telephone |   varchar   | 50 |   0    |    Y     |  N   |       | 联系方式  |
|  12   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_dimension">tax_dimension</a>

**说明：** 税务维度

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | dimension_sequence |   bigint   | 20 |   0    |    N     |  N   |       | 维度序号  |
|  3   | dimension_code |   varchar   | 300 |   0    |    N     |  N   |       | 维度代码  |
|  4   | dimension_name |   varchar   | 300 |   0    |    N     |  N   |       | 维度名称  |
|  5   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  6   | remarks |   varchar   | 400 |   0    |    Y     |  N   |       | 备注  |
|  7   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  13   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除1：删除0：未删除  |

**表名：** <a id="tax_dimension_i18n">tax_dimension_i18n</a>

**说明：** 维度I18n表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  N   |       | 主键ID  |
|  2   | lang_code |   varchar   | 20 |   0    |    Y     |  N   |       | 语言  |
|  3   | dimension_name |   varchar   | 100 |   0    |    N     |  N   |       | 维度名称  |

**表名：** <a id="tax_dimension_item">tax_dimension_item</a>

**说明：** 维值定义

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | dimension_id |   bigint   | 20 |   0    |    N     |  N   |       | 维度ID  |
|  3   | dimension_item_code |   varchar   | 300 |   0    |    N     |  N   |       | 维值代码  |
|  4   | dimension_item_name |   varchar   | 300 |   0    |    N     |  N   |       | 维值名称  |
|  5   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  6   | visible_user_scope |   varchar   | 400 |   0    |    Y     |  N   |       | 可见人员范围  |
|  7   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  13   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除1：删除0：未删除  |

**表名：** <a id="tax_dimension_item_ass_com">tax_dimension_item_ass_com</a>

**说明：** 维值关联公司表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | dimension_item_id |   bigint   | 20 |   0    |    N     |  N   |       | 维值ID  |
|  3   | company_id |   bigint   | 20 |   0    |    N     |  N   |       | 公司ID  |
|  4   | company_code |   varchar   | 30 |   0    |    N     |  N   |       | 公司代码  |
|  5   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  8   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_dimension_item_ass_dep">tax_dimension_item_ass_dep</a>

**说明：** 维值关联部门表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | dimension_item_id |   bigint   | 20 |   0    |    N     |  N   |       | 维值ID  |
|  3   | department_id |   bigint   | 20 |   0    |    N     |  N   |       | 部门ID  |
|  4   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_dimension_item_i18n">tax_dimension_item_i18n</a>

**说明：** 维值I18n表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  N   |       | 主键ID  |
|  2   | lang_code |   varchar   | 20 |   0    |    Y     |  N   |       | 语言  |
|  3   | dimension_item_name |   varchar   | 100 |   0    |    N     |  N   |       | 维值名称  |

**表名：** <a id="tax_dimension_item_temp">tax_dimension_item_temp</a>

**说明：** 维值定义导入临时表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | dimension_item_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  3   | dimension_item_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  4   | dimension_id |   bigint   | 20 |   0    |    Y     |  N   |       | 维度ID  |
|  5   | enabled |   tinyint   | 4 |   0    |    Y     |  N   |   1    | 启用标志  |
|  6   | enabled_str |   varchar   | 30 |   0    |    Y     |  N   |       | 是否启用标识  |
|  7   | batch_number |   varchar   | 50 |   0    |    Y     |  N   |       | 导入批次号  |
|  8   | order_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  9   | error_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 错误标识  |
|  10   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_bld_a">tax_draft_bld_a</a>

**说明：** 房产税底稿表02

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | VERSION_DETAIL_ID |   bigint   | 20 |   0    |    N     |  N   |       | 版本明细ID  |
|  3   | LINE_TYPE |   varchar   | 10 |   0    |    N     |  N   |       | 行类型  |
|  4   | LINE_NUM |   int   | 10 |   0    |    N     |  N   |       | 行号  |
|  5   | TAXPAYER_NUMBER |   varchar   | 360 |   0    |    Y     |  N   |       | 申报主体税号  |
|  6   | TAXPAYER_NAME |   varchar   | 360 |   0    |    Y     |  N   |       | 申报主体名称  |
|  7   | AUTHORITY_ID |   decimal   | 21 |   0    |    N     |  N   |       | 所属税务机关id  |
|  8   | AUTHORITY_NAME |   varchar   | 360 |   0    |    Y     |  N   |       | 所属税务机关  |
|  9   | ASSET_NUM |   varchar   | 360 |   0    |    Y     |  N   |       | 房源编号  |
|  10   | PROPERTY_NAME |   varchar   | 360 |   0    |    Y     |  N   |       | 房源名称  |
|  11   | PROPERTY_NUM |   varchar   | 360 |   0    |    Y     |  N   |       | 房产所有权证号  |
|  12   | PROPERTY_USAGE |   varchar   | 360 |   0    |    Y     |  N   |       | 房产用途  |
|  13   | PROPERTY_LOCATION |   varchar   | 1000 |   0    |    Y     |  N   |       | 房产坐落地址  |
|  14   | LAND_PARCEL_NUM |   varchar   | 360 |   0    |    Y     |  N   |       | 房产对应地号  |
|  15   | COVERED_AREA |   decimal   | 21 |   2    |    Y     |  N   |       | 房屋建筑面积  |
|  16   | RENT_AREA |   decimal   | 21 |   2    |    Y     |  N   |       | 出租面积  |
|  17   | TENANT_NAME |   varchar   | 360 |   0    |    Y     |  N   |       | 承租方名称  |
|  18   | TENANT_TAXPER_NUMBER |   varchar   | 360 |   0    |    Y     |  N   |       | 承租方纳税人识别号/身份证  |
|  19   | RENTAL_INCOME |   decimal   | 21 |   2    |    Y     |  N   |       | 合同租金总收入  |
|  20   | CURRENT_TAX_INCOME |   decimal   | 21 |   2    |    Y     |  N   |       | 本期租金计税收入  |
|  21   | ADJUSTMENT_AMOUNT |   decimal   | 21 |   2    |    Y     |  N   |       | 调整金额  |
|  22   | BLD_B_RATE |   decimal   | 21 |   2    |    Y     |  N   |       | 从租房产税税率  |
|  23   | ADJUSTMENT_TAX_AMOUNT |   decimal   | 21 |   2    |    Y     |  N   |       | 本期从租房产税调整税额  |
|  24   | PRICE_TAX_AMOUNT |   decimal   | 21 |   2    |    Y     |  N   |       | 本期从租房产税税额  |
|  25   | RELIEF_CODE |   varchar   | 360 |   0    |    Y     |  N   |       | 减免性质代码  |
|  26   | CURRENT_TAX_RELIEF |   decimal   | 21 |   2    |    Y     |  N   |       | 本期减免税额  |
|  27   | PERIOD_PAIND_BLD |   decimal   | 21 |   2    |    Y     |  N   |       | 本期已缴税额  |
|  28   | TAKE_REFUND_TAX |   decimal   | 21 |   2    |    Y     |  N   |       | 本期应补(退)税额  |
|  29   | SMALL_REDUCTION_TAX |   decimal   | 21 |   2    |    Y     |  N   |       | 本期增值税小规模纳税人减征额  |
|  30   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  31   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  32   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  33   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  34   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  35   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_bld_b">tax_draft_bld_b</a>

**说明：** 房产税底稿表从价01

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | VERSION_DETAIL_ID |   bigint   | 20 |   0    |    N     |  N   |       | 版本明细ID  |
|  3   | LINE_TYPE |   varchar   | 10 |   0    |    N     |  N   |       | 行类型  |
|  4   | LINE_NUM |   int   | 10 |   0    |    N     |  N   |       | 行号  |
|  5   | TAXPAYER_NUMBER |   varchar   | 360 |   0    |    N     |  N   |       | 申报主体税号  |
|  6   | TAXPAYER_NAME |   varchar   | 360 |   0    |    N     |  N   |       | 申报主体名称  |
|  7   | AUTHORITY_ID |   decimal   | 21 |   0    |    N     |  N   |       | 所属税务机关id  |
|  8   | AUTHORITY_NAME |   varchar   | 360 |   0    |    N     |  N   |       | 所属税务机关  |
|  9   | ASSET_NUM |   varchar   | 360 |   0    |    N     |  N   |       | 房源编号  |
|  10   | PROPERTY_NAME |   varchar   | 360 |   0    |    N     |  N   |       | 房源名称  |
|  11   | PROPERTY_NUM |   varchar   | 360 |   0    |    N     |  N   |       | 房产所有权证号  |
|  12   | PROPERTY_USAGE |   varchar   | 360 |   0    |    N     |  N   |       | 房产用途  |
|  13   | PROPERTY_LOCATION |   varchar   | 1000 |   0    |    N     |  N   |       | 房产坐落地址  |
|  14   | LAND_PARCEL_NUM |   varchar   | 360 |   0    |    Y     |  N   |       | 房产对应地号  |
|  15   | COVERED_AREA |   decimal   | 21 |   2    |    N     |  N   |       | 房屋建筑面积  |
|  16   | RENT_AREA |   decimal   | 21 |   2    |    N     |  N   |       | 出租面积  |
|  17   | PROPERTY_VALUE |   decimal   | 21 |   2    |    N     |  N   |       | 房产原值  |
|  18   | ADJUSTMENT_AMOUNT |   decimal   | 21 |   2    |    Y     |  N   |       | 调整金额  |
|  19   | RENT_PROPERTY_VALUE |   decimal   | 21 |   2    |    Y     |  N   |       | 出租房产原值  |
|  20   | BLD_TAX_BASIS |   decimal   | 21 |   2    |    Y     |  N   |       | 房产税计税基础  |
|  21   | TAX_RATE |   decimal   | 21 |   2    |    N     |  N   |       | 计税比例  |
|  22   | BLD_A_RATE |   decimal   | 21 |   4    |    N     |  N   |       | 从价房产税税率  |
|  23   | PRICE_TAX_AMOUNT |   decimal   | 21 |   2    |    Y     |  N   |       | 年度从价房产税税额  |
|  24   | ADJUSTMENT_TAX_AMOUNT |   decimal   | 21 |   2    |    N     |  N   |       | 本期从价房产税调整税额  |
|  25   | MONTH_TAX_AMOUNT |   decimal   | 21 |   2    |    N     |  N   |       | 本期从价房产税税额  |
|  26   | RELIEF_CODE |   varchar   | 360 |   0    |    Y     |  N   |       | 减免性质代码  |
|  27   | CURRENT_TAX_RELIEF |   decimal   | 21 |   2    |    Y     |  N   |       | 本期减免税额  |
|  28   | PERIOD_PAIND_BLD |   decimal   | 21 |   2    |    Y     |  N   |       | 本期已缴从价房产税  |
|  29   | TAKE_REFUND_TAX |   decimal   | 21 |   2    |    Y     |  N   |       | 本期应补(退)税额  |
|  30   | DATE_FROM |   varchar   | 360 |   0    |    Y     |  N   |       | 期间从  |
|  31   | DATE_TO |   varchar   | 360 |   0    |    Y     |  N   |       | 期间至  |
|  32   | MONTH_COUNTER |   decimal   | 21 |   2    |    Y     |  N   |       | 月份数  |
|  33   | SMALL_REDUCTION_TAX |   decimal   | 21 |   2    |    Y     |  N   |       | 本期增值税小规模纳税人减征额  |
|  34   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  35   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  36   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  37   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  38   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  39   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_cell_data">tax_draft_cell_data</a>

**说明：** 底稿单元格数据

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | data_year |   int   | 10 |   0    |    Y     |  N   |       | 年份  |
|  3   | tax_category_type |   varchar   | 360 |   0    |    N     |  N   |       | 税种类型  |
|  4   | version_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 底稿模板明细id  |
|  5   | row_code |   varchar   | 20 |   0    |    N     |  N   |       | 行编码  |
|  6   | col_code |   varchar   | 20 |   0    |    N     |  N   |       | 列编码  |
|  7   | position_code |   varchar   | 20 |   0    |    N     |  N   |       | 位置编码  |
|  8   | value_type |   varchar   | 10 |   0    |    N     |  N   |       | 值类型  |
|  9   | number_value |   decimal   | 39 |   18    |    Y     |  N   |       |   |
|  10   | date_value |   timestamp   | 19 |   0    |    Y     |  N   |       | 日期类型  |
|  11   | string_value |   varchar   | 500 |   0    |    Y     |  N   |       | 字符类型  |
|  12   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  14   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  15   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  17   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_data">tax_draft_data</a>

**说明：** 底稿数据表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | data_year |   int   | 10 |   0    |    Y     |  N   |       | 年度  |
|  3   | tax_category_type |   varchar   | 360 |   0    |    N     |  N   |       | 税种类型  |
|  4   | version_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 底稿模板明细id  |
|  5   | row_code |   varchar   | 20 |   0    |    Y     |  N   |       | 位置编码  |
|  6   | c10 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  7   | c20 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  8   | c30 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  9   | c40 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  10   | c50 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  11   | c60 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  12   | c70 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  13   | c80 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  14   | c90 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  15   | c100 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  16   | c110 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  17   | c120 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  18   | c130 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  19   | c140 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  20   | c150 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  21   | c160 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  22   | c170 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  23   | c180 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  24   | c190 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  25   | c200 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  26   | c210 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  27   | c220 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  28   | c230 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  29   | c240 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  30   | c250 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  31   | c260 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  32   | c270 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  33   | c280 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  34   | c290 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  35   | c300 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  36   | c310 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  37   | c320 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  38   | c330 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  39   | c340 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  40   | c350 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  41   | c360 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  42   | c370 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  43   | c380 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  44   | c390 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  45   | c400 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  46   | c410 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  47   | c420 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  48   | c430 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  49   | c440 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  50   | c450 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  51   | c460 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  52   | c470 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  53   | c480 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  54   | c490 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  55   | c500 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  56   | c510 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  57   | c520 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  58   | c530 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  59   | c540 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  60   | c550 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  61   | c560 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  62   | c570 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  63   | c580 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  64   | c590 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  65   | c600 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  66   | c610 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  67   | c620 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  68   | c630 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  69   | c640 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  70   | c650 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  71   | c660 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  72   | c670 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  73   | c680 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  74   | c690 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  75   | c700 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  76   | c710 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  77   | c720 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  78   | c730 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  79   | c740 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  80   | c750 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  81   | c760 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  82   | c770 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  83   | c780 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  84   | c790 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  85   | c800 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  86   | c810 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  87   | c820 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  88   | c830 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  89   | c840 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  90   | c850 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  91   | c860 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  92   | c870 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  93   | c880 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  94   | c890 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  95   | c900 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  96   | c910 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  97   | c920 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  98   | c930 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  99   | c940 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  100   | c950 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  101   | c960 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  102   | c970 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  103   | c980 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  104   | c990 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  105   | c1000 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  106   | c1010 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  107   | c1020 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  108   | c1030 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  109   | c1040 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  110   | c1050 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  111   | c1060 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  112   | c1070 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  113   | c1080 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  114   | c1090 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  115   | c1100 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  116   | c1110 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  117   | c1120 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  118   | c1130 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  119   | c1140 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  120   | c1150 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  121   | c1160 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  122   | c1170 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  123   | c1180 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  124   | c1190 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  125   | c1200 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  126   | c1210 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  127   | c1220 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  128   | c1230 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  129   | c1240 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  130   | c1250 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  131   | c1260 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  132   | c1270 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  133   | c1280 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  134   | c1290 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  135   | c1300 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  136   | c1310 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  137   | c1320 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  138   | c1330 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  139   | c1340 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  140   | c1350 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  141   | c1360 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  142   | c1370 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  143   | c1380 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  144   | c1390 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  145   | c1400 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  146   | c1410 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  147   | c1420 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  148   | c1430 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  149   | c1440 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  150   | c1450 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  151   | c1460 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  152   | c1470 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  153   | c1480 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  154   | c1490 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  155   | c1500 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  156   | c1510 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  157   | c1520 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  158   | c1530 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  159   | c1540 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  160   | c1550 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  161   | c1560 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  162   | c1570 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  163   | c1580 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  164   | c1590 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  165   | c1600 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  166   | c1610 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  167   | c1620 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  168   | c1630 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  169   | c1640 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  170   | c1650 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  171   | c1660 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  172   | c1670 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  173   | c1680 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  174   | c1690 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  175   | c1700 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  176   | c1710 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  177   | c1720 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  178   | c1730 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  179   | c1740 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  180   | c1750 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  181   | c1760 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  182   | c1770 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  183   | c1780 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  184   | c1790 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  185   | c1800 |   text   | 65535 |   0    |    Y     |  N   |       |   |
|  186   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  187   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  188   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  189   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  190   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  191   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_lut">tax_draft_lut</a>

**说明：** 土地使用税底稿表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | VERSION_DETAIL_ID |   bigint   | 20 |   0    |    N     |  N   |       | 版本明细ID  |
|  3   | LINE_TYPE |   varchar   | 10 |   0    |    N     |  N   |       | 行类型  |
|  4   | LINE_NUM |   int   | 10 |   0    |    N     |  N   |       | 行号  |
|  5   | TAXPAYER_NUMBER |   varchar   | 200 |   0    |    N     |  N   |       | 纳税人识别号  |
|  6   | TAXPAYER_NAME |   varchar   | 400 |   0    |    N     |  N   |       | 纳税人名称  |
|  7   | AUTHORITY_NAME |   varchar   | 400 |   0    |    N     |  N   |       | 所属税务机关  |
|  8   | LNAD_NUMBER |   varchar   | 400 |   0    |    N     |  N   |       | 土地使用权证号  |
|  9   | LAND_PARCEL_NUM |   varchar   | 400 |   0    |    N     |  N   |       | 地号  |
|  10   | OWNER_DATE |   timestamp   | 19 |   0    |    N     |  N   |       | 取得日期  |
|  11   | LAND_AREA |   decimal   | 21 |   2    |    N     |  N   |       | 土地面积  |
|  12   | BALANCE_AREA |   decimal   | 21 |   2    |    Y     |  N   |       | 免税面积  |
|  13   | TAX_AREA |   decimal   | 21 |   2    |    N     |  N   |       | 应税面积  |
|  14   | LAND_LEVEL_CODE |   varchar   | 200 |   0    |    N     |  N   |       | 土地等级  |
|  15   | TAX_STANDARD |   decimal   | 21 |   2    |    N     |  N   |       | 税额标准  |
|  16   | PAYABLE_TAX |   decimal   | 21 |   2    |    Y     |  N   |       | 年度应纳税额  |
|  17   | AVERAGE_TAX |   decimal   | 21 |   2    |    N     |  N   |       | 本期应纳税额  |
|  18   | DEDUCT_TAX |   decimal   | 21 |   2    |    N     |  N   |       | 本期减免税额  |
|  19   | PAID_TAX |   decimal   | 21 |   2    |    N     |  N   |       | 本期已缴税额  |
|  20   | BALANCE_TAX |   decimal   | 21 |   2    |    N     |  N   |       | 本期应补（退）税额  |
|  21   | PRIOD_FROM |   varchar   | 200 |   0    |    N     |  N   |       | 税款所属期起  |
|  22   | PRIOD_TO |   varchar   | 200 |   0    |    N     |  N   |       | 税款所属期止  |
|  23   | AUTHORITY_ID |   decimal   | 21 |   0    |    N     |  N   |       | 所属税务机关id  |
|  24   | SMALL_REDUCTION_TAX |   decimal   | 21 |   2    |    Y     |  N   |       |   |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  27   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  28   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_spt_account1">tax_draft_spt_account1</a>

**说明：** 营业账簿底稿

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 版本明细ID  |
|  3   | line_type |   varchar   | 10 |   0    |    N     |  N   |       | 行类型  |
|  4   | line_num |   int   | 10 |   0    |    N     |  N   |       | 行号  |
|  5   | TAXPAYER_NUMBER |   varchar   | 200 |   0    |    N     |  N   |       | 纳税人识别号  |
|  6   | TAXPAYER_NAME |   varchar   | 400 |   0    |    N     |  N   |       | 纳税人名称  |
|  7   | TAX_PERIOD |   varchar   | 100 |   0    |    N     |  N   |       | 期间  |
|  8   | TAX_ITEM |   varchar   | 100 |   0    |    N     |  N   |       | 税目  |
|  9   | ACC_BOOK_NO |   varchar   | 200 |   0    |    N     |  N   |       | 账簿编号  |
|  10   | ACC_BOOK_NAME |   varchar   | 200 |   0    |    N     |  N   |       | 账簿名称  |
|  11   | ACC_BOOK_DATE |   timestamp   | 19 |   0    |    N     |  N   |       | 订立日期  |
|  12   | TAX_INCLU_AMOUNT |   varchar   | 2 |   0    |    N     |  N   |       | 计税金额/件数  |
|  13   | TAX_RATIO |   decimal   | 21 |   2    |    N     |  N   |       | 税率  |
|  14   | TAX_AMOUNT |   varchar   | 2 |   0    |    N     |  N   |       | 税额  |
|  15   | PAYED_TAX |   decimal   | 21 |   2    |    N     |  N   |       | 本期已纳税额  |
|  16   | RELIEF_CODE |   varchar   | 200 |   0    |    N     |  N   |       | 减免税项目  |
|  17   | CURRENT_TAX_RELIEF |   decimal   | 21 |   2    |    N     |  N   |       | 减免税金额  |
|  18   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  19   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  20   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  21   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  22   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  23   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_spt_contract">tax_draft_spt_contract</a>

**说明：** 合同类底稿

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | ID |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | VERSION_DETAIL_ID |   bigint   | 20 |   0    |    N     |  N   |       | 版本明细ID  |
|  3   | LINE_TYPE |   varchar   | 10 |   0    |    N     |  N   |       | 行类型  |
|  4   | LINE_NUM |   int   | 10 |   0    |    N     |  N   |       | 行号  |
|  5   | TAXPAYER_NUMBER |   varchar   | 200 |   0    |    N     |  N   |       | 合同申报纳税主体税号  |
|  6   | TAXPAYER_NAME |   varchar   | 500 |   0    |    N     |  N   |       | 合同申报纳税主体  |
|  7   | TAX_PERIOD |   varchar   | 200 |   0    |    N     |  N   |       | 期间  |
|  8   | TAX_ITEM |   varchar   | 200 |   0    |    N     |  N   |       | 税目代码  |
|  9   | CONTRACT_COMPANY |   varchar   | 500 |   0    |    N     |  N   |       | 合同签约公司  |
|  10   | TAX_NAME |   varchar   | 100 |   0    |    N     |  N   |       | 税目  |
|  11   | CONTRACT_NO |   varchar   | 200 |   0    |    N     |  N   |       | 合同编号  |
|  12   | CONTRACT_NAME |   varchar   | 500 |   0    |    N     |  N   |       | 合同名称  |
|  13   | CONTRACT_DATE |   timestamp   | 19 |   0    |    N     |  N   |       | 合同有效起始日期  |
|  14   | TAX_INCLU_AMOUNT |   decimal   | 21 |   2    |    N     |  N   |       | 合同金额  |
|  15   | ORDER_NO |   varchar   | 200 |   0    |    N     |  N   |       | 订单编号  |
|  16   | TAX_INCLU_AMOUNT2 |   decimal   | 21 |   2    |    N     |  N   |       | 计税金额  |
|  17   | TAX_RATIO |   decimal   | 21 |   5    |    N     |  N   |       | 税率  |
|  18   | TAX_AMOUNT |   decimal   | 21 |   4    |    N     |  N   |       | 税额  |
|  19   | PAYED_TAX |   decimal   | 21 |   2    |    N     |  N   |       | 本期已纳税额  |
|  20   | RELIEF_CODE |   varchar   | 200 |   0    |    N     |  N   |       | 减免税项目  |
|  21   | CURRENT_TAX_RELIEF |   decimal   | 21 |   2    |    N     |  N   |       | 减免税金额  |
|  22   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  23   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  24   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  25   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  27   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_spt_funding">tax_draft_spt_funding</a>

**说明：** 资金类营业账簿

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 版本明细ID  |
|  3   | line_type |   varchar   | 10 |   0    |    N     |  N   |       | 行类型  |
|  4   | line_num |   int   | 10 |   0    |    N     |  N   |       | 行号  |
|  5   | TAXPAYER_NUMBER |   varchar   | 360 |   0    |    N     |  N   |       | 纳税人识别号  |
|  6   | TAXPAYER_NAME |   varchar   | 360 |   0    |    N     |  N   |       | 纳税人名称  |
|  7   | TAX_PERIOD |   varchar   | 360 |   0    |    Y     |  N   |       | 期间  |
|  8   | TAX_NAME |   varchar   | 360 |   0    |    N     |  N   |       | 税目  |
|  9   | ACCOUNTING_SHARE_CAPITAL |   decimal   | 21 |   2    |    Y     |  N   |       | ERP总账-实收资本（股本）  |
|  10   | ACCOUNTING_CAPTIAL_CAPITAL |   decimal   | 21 |   2    |    Y     |  N   |       | ERP总账-资本公积  |
|  11   | TOTAL_AMOUNT_ON_ACCOUNT |   decimal   | 21 |   2    |    Y     |  N   |       | 账载金额合计  |
|  12   | LAST_PAID_AMOUNT |   decimal   | 21 |   2    |    N     |  N   |       | 上次缴税金额  |
|  13   | TAX_INCLU_AMOUNT |   decimal   | 21 |   2    |    Y     |  N   |       | 本期计税金额  |
|  14   | TAX_RATIO |   decimal   | 21 |   4    |    N     |  N   |       | 税率  |
|  15   | TAX_AMOUNT |   decimal   | 21 |   4    |    N     |  N   |       | 税额  |
|  16   | PAYED_TAX |   decimal   | 21 |   2    |    Y     |  N   |       | 本期已纳税额  |
|  17   | RELIEF_CODE |   varchar   | 360 |   0    |    Y     |  N   |       | 减免税项目  |
|  18   | CURRENT_TAX_RELIEF |   decimal   | 21 |   2    |    Y     |  N   |       | 减免税金额  |
|  19   | BALANCE_TAX |   decimal   | 21 |   2    |    Y     |  N   |       | 本期应补（退）税额  |
|  20   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  21   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  22   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  23   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  24   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  25   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_tax_type">tax_draft_tax_type</a>

**说明：** 底稿税种类型表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_category |   varchar   | 360 |   0    |    N     |  N   |       | 税种  |
|  3   | type_code |   varchar   | 360 |   0    |    N     |  N   |       | 类型代码  |
|  4   | type_name |   varchar   | 360 |   0    |    N     |  N   |       | 类型名称  |
|  5   | file_id |   bigint   | 20 |   0    |    Y     |  N   |       | 类型模板  |
|  6   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  7   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  8   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  9   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  10   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  11   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  12   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  13   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  14   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  15   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  16   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  17   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  18   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  19   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  20   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  21   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  22   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  23   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  24   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  25   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  26   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  27   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_template">tax_draft_template</a>

**说明：** 底稿模板

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | template_code |   varchar   | 360 |   0    |    N     |  N   |       | 模板代码  |
|  3   | template_index |   varchar   | 50 |   0    |    N     |  N   |       | 模板索引  |
|  4   | template_name |   varchar   | 360 |   0    |    N     |  N   |       | 模板名称  |
|  5   | template_type |   varchar   | 50 |   0    |    N     |  N   |       | 模板类型  |
|  6   | template_table |   varchar   | 360 |   0    |    Y     |  N   |       | 底稿表名  |
|  7   | draft_type |   varchar   | 50 |   0    |    N     |  N   |   BASE    | 底稿类型  |
|  8   | tax_category |   varchar   | 50 |   0    |    N     |  N   |       | 税种  |
|  9   | tax_category_type |   varchar   | 50 |   0    |    Y     |  N   |       | 税种类型  |
|  10   | template_sort |   int   | 10 |   0    |    Y     |  N   |       | 模板序号  |
|  11   | execute_sort |   int   | 10 |   0    |    Y     |  N   |       | 执行序号  |
|  12   | file_id |   bigint   | 20 |   0    |    Y     |  N   |       | 模板文件id  |
|  13   | enable_flag |   varchar   | 10 |   0    |    N     |  N   |       | 是否启用  |
|  14   | delete_flag |   varchar   | 10 |   0    |    N     |  N   |   N    | 删除标识  |
|  15   | relation_template_id |   int   | 10 |   0    |    Y     |  N   |       | 申报模板与更正申报模板关联  |
|  16   | template_desc |   varchar   | 4000 |   0    |    Y     |  N   |       | 备注  |
|  17   | created_taxpayer |   int   | 10 |   0    |    Y     |  N   |       | 创建税号id  |
|  18   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  19   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  20   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  21   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  22   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  23   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  24   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  25   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  26   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  27   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  28   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  29   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  30   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  31   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  32   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  33   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  34   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  35   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  36   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  37   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  38   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  39   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  40   | file_oid |   varchar   | 400 |   0    |    Y     |  N   |       | 模板文件  |
|  41   | judge_blank_row_from |   int   | 10 |   0    |    Y     |  N   |       | 判断空白行从  |
|  42   | judge_blank_row_to |   int   | 10 |   0    |    Y     |  N   |       | 判断空白行至  |
|  43   | judge_blank_col |   int   | 10 |   0    |    Y     |  N   |       | 判断空白列  |

**表名：** <a id="tax_draft_template_assign">tax_draft_template_assign</a>

**说明：** 底稿模板分配表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | parent_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 来源纳税主体id  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 分配纳税主体id  |
|  4   | template_id |   bigint   | 20 |   0    |    N     |  N   |       | 分配模板id  |
|  5   | enable_flag |   varchar   | 10 |   0    |    N     |  N   |   Y    | 是否启用  |
|  6   | created_taxpayer |   int   | 10 |   0    |    Y     |  N   |       | 创建税号id  |
|  7   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  8   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  9   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  10   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  11   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  12   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  13   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  14   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  15   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  16   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  17   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  18   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  19   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  20   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  21   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  22   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  23   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  24   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  25   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  27   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  28   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_template_columns">tax_draft_template_columns</a>

**说明：** 底稿浮动行模板填报字段

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | template_id |   bigint   | 20 |   0    |    N     |  N   |       | 模板ID  |
|  3   | column_code |   varchar   | 360 |   0    |    Y     |  N   |       | 字段代码  |
|  4   | template_column_name |   varchar   | 360 |   0    |    Y     |  N   |       | 字段名称  |
|  5   | column_type |   varchar   | 10 |   0    |    Y     |  N   |       | 字段类型  |
|  6   | column_length |   int   | 10 |   0    |    Y     |  N   |       | 字段长度  |
|  7   | nullable_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 可否为空  |
|  8   | column_sort |   int   | 10 |   0    |    Y     |  N   |       | 字段序号  |
|  9   | source_type |   varchar   | 10 |   0    |    Y     |  N   |       | 来源类型  |
|  10   | source_code |   varchar   | 100 |   0    |    Y     |  N   |       | 来源代码  |
|  11   | parent_column_id |   bigint   | 20 |   0    |    Y     |  N   |       | 父级  |
|  12   | default_value |   varchar   | 4000 |   0    |    Y     |  N   |       | 默认值  |
|  13   | edit_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 编辑标识  |
|  14   | display_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 展示标识  |
|  15   | query_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 查询标识  |
|  16   | column_width |   int   | 10 |   0    |    Y     |  N   |       | 字段宽度  |
|  17   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  18   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  19   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  20   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  21   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  22   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  23   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  24   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  25   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  26   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  27   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  28   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  29   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  30   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  31   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  32   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  33   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  34   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  35   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  36   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  37   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  38   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_template_detail">tax_draft_template_detail</a>

**说明：** 底稿模板明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | template_id |   bigint   | 20 |   0    |    N     |  N   |       | 模板id  |
|  3   | row_num |   int   | 10 |   0    |    N     |  N   |       | 行号  |
|  4   | rowspan |   int   | 10 |   0    |    N     |  N   |       | 合并行数  |
|  5   | cell_num |   int   | 10 |   0    |    N     |  N   |       | 列号  |
|  6   | cellspan |   int   | 10 |   0    |    N     |  N   |       | 合并列数  |
|  7   | position_code |   varchar   | 20 |   0    |    N     |  N   |       | 位置编码  |
|  8   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  9   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  10   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  11   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  12   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  13   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  14   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  15   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  16   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  17   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  18   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  19   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  20   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  21   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  22   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  23   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  24   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  25   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  26   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  27   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  28   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  29   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  30   | cell_type |   varchar   | 20 |   0    |    Y     |  N   |       | 单元格类型  |
|  31   | source_type |   varchar   | 20 |   0    |    Y     |  N   |       | 来源格来源类型  |
|  32   | cell_source |   varchar   | 360 |   0    |    Y     |  N   |       | 值来源  |
|  33   | cell_value |   text   | 65535 |   0    |    Y     |  N   |       | 单元格值  |
|  34   | decimals_num |   int   | 10 |   0    |    Y     |  N   |       | 小数位数  |

**表名：** <a id="tax_draft_template_dv">tax_draft_template_dv</a>

**说明：** 底稿浮动行模板默认值表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | template_id |   bigint   | 20 |   0    |    N     |  N   |       | 模板ID  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  4   | line_type |   varchar   | 1 |   0    |    N     |  N   |       | 行类型  |
|  5   | line_num |   int   | 10 |   0    |    Y     |  N   |       | 行号  |
|  6   | line_sql |   text   | 65535 |   0    |    Y     |  N   |       | 行初始化SQL  |
|  7   | item1 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  8   | item2 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  9   | item3 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  10   | item4 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  11   | item5 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  12   | item6 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  13   | item7 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  14   | item8 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  15   | item9 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  16   | item10 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  17   | item11 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  18   | item12 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  19   | item13 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  20   | item14 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  21   | item15 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  22   | item16 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  23   | item17 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  24   | item18 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  25   | item19 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  26   | item20 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  27   | item21 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  28   | item22 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  29   | item23 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  30   | item24 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  31   | item25 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  32   | item26 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  33   | item27 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  34   | item28 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  35   | item29 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  36   | item30 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  37   | item31 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  38   | item32 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  39   | item33 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  40   | item34 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  41   | item35 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  42   | item36 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  43   | item37 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  44   | item38 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  45   | item39 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  46   | item40 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  47   | item41 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  48   | item42 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  49   | item43 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  50   | item44 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  51   | item45 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  52   | item46 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  53   | item47 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  54   | item48 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  55   | item49 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  56   | item50 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  57   | item51 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  58   | item52 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  59   | item53 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  60   | item54 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  61   | item55 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  62   | item56 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  63   | item57 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  64   | item58 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  65   | item59 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  66   | item60 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  67   | item61 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  68   | item62 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  69   | item63 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  70   | item64 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  71   | item65 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  72   | item66 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  73   | item67 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  74   | item68 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  75   | item69 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  76   | item70 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  77   | item71 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  78   | item72 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  79   | item73 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  80   | item74 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  81   | item75 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  82   | item76 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  83   | item77 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  84   | item78 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  85   | item79 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  86   | item80 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  87   | item81 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  88   | item82 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  89   | item83 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  90   | item84 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  91   | item85 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  92   | item86 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  93   | item87 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  94   | item88 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  95   | item89 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  96   | item90 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  97   | item91 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  98   | item92 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  99   | item93 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  100   | item94 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  101   | item95 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  102   | item96 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  103   | item97 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  104   | item98 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  105   | item99 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  106   | item100 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  107   | item101 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  108   | item102 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  109   | item103 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  110   | item104 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  111   | item105 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  112   | item106 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  113   | item107 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  114   | item108 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  115   | item109 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  116   | item110 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  117   | item111 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  118   | item112 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  119   | item113 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  120   | item114 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  121   | item115 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  122   | item116 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  123   | item117 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  124   | item118 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  125   | item119 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  126   | item120 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  127   | item121 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  128   | item122 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  129   | item123 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  130   | item124 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  131   | item125 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  132   | item126 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  133   | item127 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  134   | item128 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  135   | item129 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  136   | item130 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  137   | item131 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  138   | item132 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  139   | item133 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  140   | item134 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  141   | item135 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  142   | item136 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  143   | item137 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  144   | item138 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  145   | item139 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  146   | item140 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  147   | item141 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  148   | item142 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  149   | item143 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  150   | item144 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  151   | item145 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  152   | item146 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  153   | item147 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  154   | item148 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  155   | item149 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  156   | item150 |   tinytext   | 255 |   0    |    Y     |  N   |       | 默认值  |
|  157   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  158   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  159   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  160   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  161   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  162   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_template_rule">tax_draft_template_rule</a>

**说明：** 底稿模板规则

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | template_detail_id |   bigint   | 20 |   0    |    Y     |  N   |       | 明细id  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税号id  |
|  4   | cell_type |   varchar   | 10 |   0    |    N     |  N   |       | 数据类型  |
|  5   | source_type |   varchar   | 10 |   0    |    Y     |  N   |       | 输入类型  |
|  6   | cell_source |   varchar   | 360 |   0    |    Y     |  N   |       | 数据源  |
|  7   | cell_value |   varchar   | 4000 |   0    |    Y     |  N   |       | 默认值  |
|  8   | decimals_num |   int   | 10 |   0    |    Y     |  N   |       | 小数位数  |
|  9   | cell_format |   varchar   | 30 |   0    |    Y     |  N   |       | 格式  |
|  10   | cell_width |   int   | 10 |   0    |    Y     |  N   |       | 宽度  |
|  11   | cell_color |   varchar   | 20 |   0    |    Y     |  N   |       | 背景色  |
|  12   | cell_desc |   varchar   | 4000 |   0    |    Y     |  N   |       | 描述  |
|  13   | input_type |   varchar   | 10 |   0    |    N     |  N   |       | 可输入性  |
|  14   | align_type |   varchar   | 10 |   0    |    N     |  N   |       | 对齐方式  |
|  15   | hidden_flag |   varchar   | 10 |   0    |    Y     |  N   |       | 是否隐藏  |
|  16   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  17   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  18   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  19   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  20   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  21   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  22   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  23   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  24   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  25   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  26   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  27   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  28   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  29   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  30   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  31   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  32   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  33   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  34   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  35   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  36   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  37   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_template_script">tax_draft_template_script</a>

**说明：** 底稿版本规则表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | script_code |   varchar   | 360 |   0    |    Y     |  N   |       | 脚本代码  |
|  3   | script_desc |   varchar   | 1000 |   0    |    Y     |  N   |       | 脚本描述  |
|  4   | tax_category |   varchar   | 20 |   0    |    Y     |  N   |       | 税种  |
|  5   | tax_category_type |   varchar   | 20 |   0    |    Y     |  N   |       | 税种类型  |
|  6   | template_id |   bigint   | 20 |   0    |    Y     |  N   |       | 模板ID  |
|  7   | script_type |   varchar   | 100 |   0    |    Y     |  N   |       | 脚本类型  |
|  8   | script_sql_type |   varchar   | 100 |   0    |    Y     |  N   |       | 执行的SQL类型  |
|  9   | sort_number |   int   | 10 |   0    |    Y     |  N   |       | 执行序号  |
|  10   | script_sql |   longtext   | 2147483647 |   0    |    Y     |  N   |       | 执行的SQL  |
|  11   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       | 备用类别  |
|  12   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段1  |
|  13   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段2  |
|  14   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段3  |
|  15   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段4  |
|  16   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段5  |
|  17   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段6  |
|  18   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段7  |
|  19   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段8  |
|  20   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段9  |
|  21   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段10  |
|  22   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段11  |
|  23   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段12  |
|  24   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段13  |
|  25   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段14  |
|  26   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       | 备用字段15  |
|  27   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  28   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  29   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  30   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  31   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  32   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_draft_template_script_a">tax_draft_template_script_a</a>

**说明：** 模板规则分配表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | script_id |   bigint   | 20 |   0    |    N     |  N   |       | 脚本ID  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税号ID  |
|  4   | template_id |   bigint   | 20 |   0    |    N     |  N   |       | 模板ID  |
|  5   | sort_number |   int   | 10 |   0    |    N     |  N   |       | 执行序号  |
|  6   | attribute_category |   varchar   | 30 |   0    |    Y     |  N   |       |   |
|  7   | attribute1 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  8   | attribute2 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  9   | attribute3 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  10   | attribute4 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  11   | attribute5 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  12   | attribute6 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  13   | attribute7 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  14   | attribute8 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  15   | attribute9 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  16   | attribute10 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  17   | attribute11 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  18   | attribute12 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  19   | attribute13 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  20   | attribute14 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  21   | attribute15 |   varchar   | 240 |   0    |    Y     |  N   |       |   |
|  22   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  23   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  24   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  25   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  26   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  27   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_exempt_income_interface">tax_exempt_income_interface</a>

**说明：** 免税收入接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 机构代码  |
|  3   | company_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 机构名称  |
|  4   | period_date |   varchar   | 100 |   0    |    Y     |  N   |       | 收入期间  |
|  5   | bond_type |   varchar   | 100 |   0    |    Y     |  N   |       | 债券类型  |
|  6   | exempt_income |   decimal   | 21 |   2    |    Y     |  N   |       | 免税金额  |
|  7   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  8   | taxpayer_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 纳税主体名称  |
|  9   | import_flag |   varchar   | 100 |   0    |    Y     |  N   |   系统接口    | 数据来源：默认“系统接口”  |
|  10   | import_sys |   varchar   | 100 |   0    |    Y     |  N   |   自营平台    | 来源系统：默认“自营平台”  |
|  11   | generate_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期（推送时间）  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  14   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  17   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |

**表名：** <a id="tax_fa_info_int_temp">tax_fa_info_int_temp</a>

**说明：** 核算系统资产信息接口导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | fa_books |   varchar   | 100 |   0    |    Y     |  N   |       | 资产账簿  |
|  3   | fa_des |   varchar   | 200 |   0    |    Y     |  N   |       | 资产说明  |
|  4   | category_segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 资产大类  |
|  5   | category_segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 资产中类  |
|  6   | category_segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 资产小类  |
|  7   | asset_type |   varchar   | 100 |   0    |    Y     |  N   |       | 资产类型  |
|  8   | asset_number |   varchar   | 500 |   0    |    Y     |  N   |       | 资产编号  |
|  9   | current_units |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  10   | in_use_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 是否折旧  |
|  11   | deprn_method_code |   varchar   | 100 |   0    |    Y     |  N   |       | 折旧方法  |
|  12   | prorate_conwention_code |   varchar   | 100 |   0    |    Y     |  N   |       | 折旧惯例  |
|  13   | life_in_months |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  14   | fa_deprn_period |   varchar   | 20 |   0    |    Y     |  N   |       | 期间  |
|  15   | original_cost |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  16   | cost |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  17   | recoverable_cost |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  18   | deprn_amount |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  19   | pre_deprn_amount |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  20   | start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 启用日期  |
|  21   | deprn_reserve |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  22   | ytd_deprn |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  23   | salvage_value |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  24   | retirement_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 报废期间  |
|  25   | retirement_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 报废标识  |
|  26   | distri_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 分配行ID  |
|  27   | gl_segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 机构段  |
|  28   | gl_segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 部门段  |
|  29   | gl_segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段  |
|  30   | gl_segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 子科目段  |
|  31   | gl_segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 产品段  |
|  32   | gl_segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 项目段  |
|  33   | gl_segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 往来段  |
|  34   | gl_segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段1  |
|  35   | gl_segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段2  |
|  36   | gl_segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段  |
|  37   | units_assigned |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  38   | location_id1 |   varchar   | 100 |   0    |    Y     |  N   |       | 城市  |
|  39   | location_id2 |   varchar   | 100 |   0    |    Y     |  N   |       | 物理位置  |
|  40   | assigned_to_name |   varchar   | 100 |   0    |    Y     |  N   |       | 资产分配员工姓名  |
|  41   | assigned_to_num |   varchar   | 100 |   0    |    Y     |  N   |       | 资产分配员工编号  |
|  42   | dispose_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 处理标识:未处理N,无需导入D,处理成功Y,处理失败F  |
|  43   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  44   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  45   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  46   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  47   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  48   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  49   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  50   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  51   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  52   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_fa_info_interface">tax_fa_info_interface</a>

**说明：** 核算系统资产信息接口

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | fa_books |   varchar   | 100 |   0    |    Y     |  N   |       | 资产账簿  |
|  3   | fa_des |   varchar   | 200 |   0    |    Y     |  N   |       | 资产说明  |
|  4   | category_segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 资产大类  |
|  5   | category_segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 资产中类  |
|  6   | category_segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 资产小类  |
|  7   | asset_type |   varchar   | 100 |   0    |    Y     |  N   |       | 资产类型  |
|  8   | asset_number |   varchar   | 500 |   0    |    Y     |  N   |       | 资产编号  |
|  9   | current_units |   int   | 10 |   0    |    Y     |  N   |       | 资产数量  |
|  10   | in_use_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 是否折旧  |
|  11   | deprn_method_code |   varchar   | 100 |   0    |    Y     |  N   |       | 折旧方法  |
|  12   | prorate_conwention_code |   varchar   | 100 |   0    |    Y     |  N   |       | 折旧惯例  |
|  13   | life_in_months |   decimal   | 23 |   4    |    Y     |  N   |       | 使用年限  |
|  14   | fa_deprn_period |   varchar   | 20 |   0    |    Y     |  N   |       | 期间  |
|  15   | original_cost |   decimal   | 21 |   2    |    Y     |  N   |       | 原始成本  |
|  16   | cost |   decimal   | 21 |   2    |    Y     |  N   |       | 当前成本  |
|  17   | recoverable_cost |   decimal   | 21 |   2    |    Y     |  N   |       | 可收回成本  |
|  18   | deprn_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本月实际计提折旧  |
|  19   | pre_deprn_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本月预测计提折旧  |
|  20   | start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 启用日期  |
|  21   | deprn_reserve |   decimal   | 21 |   2    |    Y     |  N   |       | 累计折旧  |
|  22   | ytd_deprn |   decimal   | 21 |   2    |    Y     |  N   |       | YTD折旧  |
|  23   | salvage_value |   decimal   | 21 |   2    |    Y     |  N   |       | 残值  |
|  24   | retirement_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 报废期间  |
|  25   | retirement_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 报废标识  |
|  26   | distri_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 分配行ID  |
|  27   | gl_segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 机构段  |
|  28   | gl_segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 部门段  |
|  29   | gl_segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段  |
|  30   | gl_segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 子科目段  |
|  31   | gl_segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 产品段  |
|  32   | gl_segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 项目段  |
|  33   | gl_segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 往来段  |
|  34   | gl_segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段1  |
|  35   | gl_segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段2  |
|  36   | gl_segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 备用段  |
|  37   | units_assigned |   int   | 10 |   0    |    Y     |  N   |       | 分配数量  |
|  38   | location_id1 |   varchar   | 100 |   0    |    Y     |  N   |       | 城市  |
|  39   | location_id2 |   varchar   | 100 |   0    |    Y     |  N   |       | 物理位置  |
|  40   | assigned_to_name |   varchar   | 100 |   0    |    Y     |  N   |       | 资产分配员工姓名  |
|  41   | assigned_to_num |   varchar   | 100 |   0    |    Y     |  N   |       | 资产分配员工编号  |
|  42   | dispose_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 处理标识:未处理N,无需导入D,处理成功Y,处理失败F  |
|  43   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  44   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  45   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  46   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  47   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  48   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  49   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_file_detail">tax_file_detail</a>

**说明：** 税务档案资料明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 档案资料头表ID  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 所属税号id  |
|  4   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       |   |
|  5   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  6   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  7   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  8   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  9   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  10   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_file_header">tax_file_header</a>

**说明：** 税务档案资料头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | file_code |   varchar   | 200 |   0    |    N     |  N   |       | 资料编号  |
|  3   | file_name |   varchar   | 200 |   0    |    N     |  N   |       | 资料名称  |
|  4   | a_level_category |   varchar   | 200 |   0    |    N     |  N   |       | 一级类别代码  |
|  5   | b_level_category |   varchar   | 200 |   0    |    N     |  N   |       | 二级类别代码  |
|  6   | c_level_category |   varchar   | 200 |   0    |    Y     |  N   |       | 三级类别代码  |
|  7   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 所属税号id  |
|  8   | memo |   varchar   | 1000 |   0    |    Y     |  N   |       | 备注  |
|  9   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  10   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  11   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  12   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  13   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  14   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  15   | apply_status |   varchar   | 100 |   0    |    Y     |  N   |       | 单据状态  |
|  16   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据OID  |
|  17   | data_year |   varchar   | 100 |   0    |    Y     |  N   |       | 所属年度  |
|  18   | cycle_precision |   varchar   | 100 |   0    |    Y     |  N   |       | 周期精度  |
|  19   | period |   varchar   | 100 |   0    |    Y     |  N   |       | 所属期间  |
|  20   | belong_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 所属日期  |

**表名：** <a id="tax_file_payer_permission">tax_file_payer_permission</a>

**说明：** 税务资料查看权限表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | file_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 档案资料明细表ID  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 税务查看权限税号ID  |
|  4   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_file_send_detail">tax_file_send_detail</a>

**说明：** 税务资料邮寄申请明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 申请头id  |
|  3   | file_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 档案资料明细表ID  |
|  4   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  10   | mailing_status |   varchar   | 100 |   0    |    Y     |  N   |       | 邮寄状态  |

**表名：** <a id="tax_file_send_header">tax_file_send_header</a>

**说明：** 税务资料邮寄申请头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 200 |   0    |    N     |  N   |       | 申请编号  |
|  3   | apply_person_id |   bigint   | 20 |   0    |    N     |  N   |       | 申请人id  |
|  4   | apply_company_id |   bigint   | 20 |   0    |    N     |  N   |       | 申请机构id  |
|  5   | recipient_name |   varchar   | 200 |   0    |    N     |  N   |       | 收件人  |
|  6   | recipient_num |   varchar   | 200 |   0    |    N     |  N   |       | 收件人电话  |
|  7   | recipient_address |   varchar   | 1000 |   0    |    N     |  N   |       | 收件地址  |
|  8   | sender_name |   varchar   | 100 |   0    |    Y     |  N   |       | 寄件人  |
|  9   | sender_num |   varchar   | 100 |   0    |    Y     |  N   |       | 寄件人电话  |
|  10   | apply_status |   varchar   | 1000 |   0    |    Y     |  N   |       | 事务状态  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  17   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据OID  |

**表名：** <a id="tax_iit_ba_info_inter_temp">tax_iit_ba_info_inter_temp</a>

**说明：** 个税基础信息导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 机构代码  |
|  3   | company_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 机构名称  |
|  4   | requisition_number |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单号  |
|  5   | je_creation_date_string |   varchar   | 100 |   0    |    Y     |  N   |       | 创建凭证日期  |
|  6   | je_creation_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 创建凭证日期  |
|  7   | csh_transaction_class |   varchar   | 100 |   0    |    Y     |  N   |       | 付款用途  |
|  8   | full_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 姓名  |
|  9   | id_card |   varchar   | 1000 |   0    |    Y     |  N   |       | 身份证号  |
|  10   | income_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 收入额  |
|  11   | derate_item |   varchar   | 100 |   0    |    Y     |  N   |       | 减免事项  |
|  12   | deduct_tax_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 允许撤销的税费  |
|  13   | derate_tax_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 减免税额  |
|  14   | tax_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 税额  |
|  15   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  16   | taxpayer_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 纳税主体名称  |
|  17   | import_flag |   varchar   | 100 |   0    |    Y     |  N   |   系统接口    | 数据来源：默认“系统接口”  |
|  18   | import_sys |   varchar   | 100 |   0    |    Y     |  N   |   费控系统    | 来源系统：默认“费控系统”  |
|  19   | generate_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期（推送时间）  |
|  20   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  21   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  22   | error_detail |   varchar   | 1000 |   0    |    Y     |  N   |       | 错误信息  |
|  23   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  24   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  25   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  26   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  27   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  28   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  29   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_iit_basic_infor_interface">tax_iit_basic_infor_interface</a>

**说明：** 个税基础信息接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 机构代码  |
|  3   | company_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 机构名称  |
|  4   | requisition_number |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单号  |
|  5   | je_creation_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 创建凭证日期  |
|  6   | csh_transaction_class |   varchar   | 100 |   0    |    Y     |  N   |       | 付款用途  |
|  7   | full_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 姓名  |
|  8   | id_card |   varchar   | 1000 |   0    |    Y     |  N   |       | 身份证号  |
|  9   | income_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 收入额  |
|  10   | derate_item |   varchar   | 100 |   0    |    Y     |  N   |       | 减免事项  |
|  11   | deduct_tax_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 允许撤销的税费  |
|  12   | derate_tax_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 减免税额  |
|  13   | tax_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 税额  |
|  14   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  15   | taxpayer_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 纳税主体名称  |
|  16   | import_flag |   varchar   | 100 |   0    |    Y     |  N   |   系统接口    | 数据来源：默认“系统接口”  |
|  17   | import_sys |   varchar   | 100 |   0    |    Y     |  N   |   费控系统    | 来源系统：默认“费控系统”  |
|  18   | generate_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期（推送时间）  |
|  19   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  20   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  21   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  22   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  23   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  24   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |

**表名：** <a id="tax_input_invoice_head">tax_input_invoice_head</a>

**说明：** 进项发票信息头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_type_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票类型ID  |
|  3   | invoice_date |   varchar   | 100 |   0    |    Y     |  N   |       | 开票日期  |
|  4   | invoice_no |   varchar   | 100 |   0    |    Y     |  N   |       | 发票号码  |
|  5   | invoice_code |   varchar   | 100 |   0    |    Y     |  N   |       | 发票代码  |
|  6   | currency_code |   varchar   | 100 |   0    |    N     |  N   |       | 币种  |
|  7   | exchange_rate |   decimal   | 21 |   2    |    Y     |  N   |       | 汇率  |
|  8   | total_amount |   varchar   | 100 |   0    |    N     |  N   |       | 价税合计  |
|  9   | buyer_name |   varchar   | 100 |   0    |    Y     |  N   |       | 购方名称  |
|  10   | buyer_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       | 购方纳税人识别号  |
|  11   | buyer_add_ph |   varchar   | 100 |   0    |    Y     |  N   |       | 购方地址/电话  |
|  12   | buyer_account |   varchar   | 100 |   0    |    Y     |  N   |       | 购方开户行/账号  |
|  13   | saler_name |   varchar   | 100 |   0    |    Y     |  N   |       | 销方名称  |
|  14   | saler_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       | 销方纳税人识别号  |
|  15   | saler_add_ph |   varchar   | 100 |   0    |    Y     |  N   |       | 销方地址/电话  |
|  16   | saler_account |   varchar   | 100 |   0    |    Y     |  N   |       | 销方开户行/账号  |
|  17   | created_method |   varchar   | 50 |   0    |    N     |  N   |       | 创建方式  |
|  18   | check_result |   bigint   | 20 |   0    |    Y     |  N   |       | 验真状态  |
|  19   | certification_date |   timestamp   | 26 |   0    |    Y     |  N   |       | 认证日期  |
|  20   | certification_reason |   varchar   | 300 |   0    |    Y     |  N   |       | 认证失败原因  |
|  21   | certification_status |   varchar   | 30 |   0    |    Y     |  N   |       | 认证状态  |
|  22   | invoice_status |   varchar   | 30 |   0    |    Y     |  N   |       | 发票状态  |
|  23   | cancel_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 作废标志  |
|  24   | red_invoice_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 红票标志  |
|  25   | blue_invoice_code |   varchar   | 100 |   0    |    Y     |  N   |       | 蓝票发票代码  |
|  26   | blue_invoice_no |   varchar   | 100 |   0    |    Y     |  N   |       | 蓝票发票号码  |
|  27   | deduction_flag |   varchar   | 10 |   0    |    Y     |  N   |       | 是否抵扣  |
|  28   | legalize_belong_date |   varchar   | 20 |   0    |    Y     |  N   |       | 税款所属期  |
|  29   | openid |   varchar   | 200 |   0    |    Y     |  N   |       | 微信用户唯一ID  |
|  30   | card_id |   varchar   | 200 |   0    |    Y     |  N   |       | 微信卡券标识ID  |
|  31   | encrypt_code |   varchar   | 200 |   0    |    Y     |  N   |       | 微信卡券加密码  |
|  32   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  33   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  34   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  35   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  36   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  37   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  38   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  39   | certification_batch_number |   varchar   | 100 |   0    |    Y     |  N   |       | 认证批次号  |

**表名：** <a id="tax_input_invoice_line">tax_input_invoice_line</a>

**说明：** 进项发票行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  3   | invoice_line_num |   int   | 10 |   0    |    N     |  N   |       | 发票行序号  |
|  4   | goods_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 货物或应税劳务、服务名称  |
|  5   | specification_model |   varchar   | 1000 |   0    |    Y     |  N   |       | 规格型号  |
|  6   | unit |   varchar   | 30 |   0    |    Y     |  N   |       | 单位  |
|  7   | unit_price |   decimal   | 28 |   9    |    Y     |  N   |       | 单价  |
|  8   | detail_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 金额  |
|  9   | tax_rate |   varchar   | 30 |   0    |    Y     |  N   |       | 税率  |
|  10   | tax_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 税额  |
|  11   | currency_code |   varchar   | 30 |   0    |    N     |  N   |       | 币种  |
|  12   | exchange_rate |   decimal   | 21 |   2    |    N     |  N   |       | 汇率  |
|  13   | detail_no |   varchar   | 200 |   0    |    Y     |  N   |       | 明细编号  |
|  14   | tax_unit_price |   decimal   | 21 |   2    |    Y     |  N   |       | 含税单价  |
|  15   | tax_detail_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 含税金额  |
|  16   | expense_item |   varchar   | 200 |   0    |    Y     |  N   |       | 费用项目  |
|  17   | plate_no |   varchar   | 200 |   0    |    Y     |  N   |       | 车牌号  |
|  18   | type |   varchar   | 50 |   0    |    Y     |  N   |       | 类型  |
|  19   | traffic_date_start |   timestamp   | 19 |   0    |    Y     |  N   |       | 通行日期起  |
|  20   | traffic_date_end |   timestamp   | 19 |   0    |    Y     |  N   |       | 通行日起止  |
|  21   | red_flag |   varchar   | 2 |   0    |    Y     |  N   |       | 红冲标志  |
|  22   | num |   decimal   | 21 |   2    |    Y     |  N   |       | 数量  |
|  23   | total_ticket_price |   decimal   | 21 |   2    |    Y     |  N   |       | 机票总额  |
|  24   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  27   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  28   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_itinerary_detail">tax_input_itinerary_detail</a>

**说明：** 进项机票行程单详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | total_ticket_price |   decimal   | 21 |   2    |    N     |  N   |       | 机票总额  |
|  4   | tax_total_amount |   varchar   | 100 |   0    |    N     |  N   |       | 税额合计  |
|  5   | name |   varchar   | 200 |   0    |    Y     |  N   |       | 乘客姓名  |
|  6   | id_card |   varchar   | 50 |   0    |    Y     |  N   |       | 身份证号  |
|  7   | agent_code |   varchar   | 100 |   0    |    Y     |  N   |       | 销售单位代号  |
|  8   | issue_by |   varchar   | 200 |   0    |    Y     |  N   |       | 填开单位  |
|  9   | fare |   decimal   | 21 |   2    |    Y     |  N   |       | 票价  |
|  10   | fuel_surcharge |   decimal   | 21 |   2    |    Y     |  N   |       | 燃油附加费  |
|  11   | caac_development_fund |   decimal   | 21 |   2    |    Y     |  N   |       | 民航发展基金  |
|  12   | insurance |   decimal   | 21 |   2    |    Y     |  N   |       | 保险费  |
|  13   | flight_check_code |   decimal   | 21 |   2    |    Y     |  N   |       | 验证码（后四位）  |
|  14   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  15   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  16   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  17   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  18   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  19   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  20   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_lemon_detail">tax_input_lemon_detail</a>

**说明：** 进项二手车发票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | machine_no |   varchar   | 100 |   0    |    N     |  N   |       | 设备编号  |
|  4   | check_code |   varchar   | 100 |   0    |    N     |  N   |       | 校验码(后6位)  |
|  5   | invoice_amount |   varchar   | 100 |   0    |    N     |  N   |       | 不含税金额合计  |
|  6   | tax_total_amount |   varchar   | 100 |   0    |    N     |  N   |       | 税额合计  |
|  7   | remark |   varchar   | 100 |   0    |    Y     |  N   |       | 备注  |
|  8   | drawer |   varchar   | 200 |   0    |    Y     |  N   |       | 开票人  |
|  9   | payee |   varchar   | 200 |   0    |    Y     |  N   |       | 收款人  |
|  10   | reviewer |   varchar   | 200 |   0    |    Y     |  N   |       | 复核人  |
|  11   | vehicle_type |   varchar   | 100 |   0    |    Y     |  N   |       | 车辆类型  |
|  12   | band_model |   varchar   | 100 |   0    |    Y     |  N   |       | 厂牌型号  |
|  13   | vehicle_identification_no |   varchar   | 100 |   0    |    Y     |  N   |       | 车辆识别代号/车架号码  |
|  14   | licenseplate |   varchar   | 100 |   0    |    Y     |  N   |       | 车牌照号  |
|  15   | registration_no |   varchar   | 100 |   0    |    Y     |  N   |       | 登记证号  |
|  16   | transferred_vehicle_office |   varchar   | 200 |   0    |    Y     |  N   |       | 转入地车辆车管所名称  |
|  17   | buyer_unit_or_individual |   varchar   | 200 |   0    |    Y     |  N   |       | 买方单位/个人  |
|  18   | buyer_unit_code_or_id_no |   varchar   | 50 |   0    |    Y     |  N   |       | 买方单位代码/身份证  |
|  19   | buyer_unit_or_individual_add |   varchar   | 200 |   0    |    Y     |  N   |       | 买方单位/个人住址  |
|  20   | buyer_phone |   varchar   | 50 |   0    |    Y     |  N   |       | 买方电话  |
|  21   | seller_unit_or_individual |   varchar   | 200 |   0    |    Y     |  N   |       | 卖方单位/个人  |
|  22   | seller_unit_code_or_id_no |   varchar   | 50 |   0    |    Y     |  N   |       | 卖方单位代码/身份证  |
|  23   | seller_unit_or_individual_add |   varchar   | 200 |   0    |    Y     |  N   |       | 卖方单位/个人住址  |
|  24   | seller_phone |   varchar   | 50 |   0    |    Y     |  N   |       | 卖方电话  |
|  25   | business_unit |   varchar   | 200 |   0    |    Y     |  N   |       | 经营、拍卖单位  |
|  26   | business_unit_address |   varchar   | 200 |   0    |    Y     |  N   |       | 经营、拍卖单位地址  |
|  27   | business_unit_tax_no |   varchar   | 200 |   0    |    Y     |  N   |       | 经营、拍卖单位纳税人识别号  |
|  28   | business_unit_bank_and_acc |   varchar   | 100 |   0    |    Y     |  N   |       | 开户银行及账号  |
|  29   | business_unit_phone |   varchar   | 50 |   0    |    Y     |  N   |       | 经营、拍卖单位电话  |
|  30   | lemon_market |   varchar   | 200 |   0    |    Y     |  N   |       | 二手车市场  |
|  31   | lemon_market_tax_no |   varchar   | 200 |   0    |    Y     |  N   |       | 二手车市场纳税人识别号  |
|  32   | lemon_market_address |   varchar   | 200 |   0    |    Y     |  N   |       | 二手车市场地址  |
|  33   | lemon_market_bank_and_account |   varchar   | 100 |   0    |    Y     |  N   |       | 二手车市场开户银行及账号  |
|  34   | lemon_market_phone |   varchar   | 50 |   0    |    Y     |  N   |       | 二手车市场电话  |
|  35   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  36   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  37   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  38   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  39   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  40   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  41   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_motor_detail">tax_input_motor_detail</a>

**说明：** 进项机动车发票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | machine_no |   varchar   | 100 |   0    |    N     |  N   |       | 设备编号  |
|  4   | check_code |   varchar   | 100 |   0    |    N     |  N   |       | 校验码(后6位)  |
|  5   | invoice_amount |   decimal   | 23 |   4    |    Y     |  N   |       |   |
|  6   | tax_total_amount |   decimal   | 23 |   4    |    Y     |  N   |       |   |
|  7   | remark |   varchar   | 100 |   0    |    Y     |  N   |       | 备注  |
|  8   | drawer |   varchar   | 200 |   0    |    Y     |  N   |       | 开票人  |
|  9   | payee |   varchar   | 200 |   0    |    Y     |  N   |       | 收款人  |
|  10   | reviewer |   varchar   | 200 |   0    |    Y     |  N   |       | 复核人  |
|  11   | id_no |   varchar   | 50 |   0    |    Y     |  N   |       | 购方身份证号/组织机构代码  |
|  12   | vehicle_type |   varchar   | 100 |   0    |    Y     |  N   |       | 车辆类型  |
|  13   | band_model |   varchar   | 100 |   0    |    Y     |  N   |       | 厂牌型号  |
|  14   | produce_area |   varchar   | 200 |   0    |    Y     |  N   |       | 产地  |
|  15   | qualified_no |   varchar   | 100 |   0    |    Y     |  N   |       | 合格证号  |
|  16   | commodity_inspection_no |   varchar   | 100 |   0    |    Y     |  N   |       | 商检单号  |
|  17   | engine_no |   varchar   | 100 |   0    |    Y     |  N   |       | 发动机号  |
|  18   | vehicle_identification_no |   varchar   | 100 |   0    |    Y     |  N   |       | 车辆识别代号/车架号码  |
|  19   | certificate_of_import |   varchar   | 100 |   0    |    Y     |  N   |       | 进口证明书号  |
|  20   | tax_authority_code |   varchar   | 100 |   0    |    Y     |  N   |       | 主管税务机关代码  |
|  21   | tax_payment_certificate_no |   varchar   | 100 |   0    |    Y     |  N   |       | 完税凭证号码  |
|  22   | limited_people_count |   int   | 10 |   0    |    Y     |  N   |       | 限乘人数  |
|  23   | tax_authority_name |   varchar   | 200 |   0    |    Y     |  N   |       | 主管税务机关名称  |
|  24   | tonnage |   varchar   | 200 |   0    |    Y     |  N   |       | 吨位  |
|  25   | tax_rate |   varchar   | 20 |   0    |    Y     |  N   |       | 税率  |
|  26   | saler_address |   varchar   | 200 |   0    |    Y     |  N   |       | 销方地址  |
|  27   | saler_phone |   varchar   | 50 |   0    |    Y     |  N   |       | 销方电话  |
|  28   | saler_bank_name |   varchar   | 100 |   0    |    Y     |  N   |       | 销方开户银行  |
|  29   | saler_bank_account |   varchar   | 100 |   0    |    Y     |  N   |       | 销方开户账号  |
|  30   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  31   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  32   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  33   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  34   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  35   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  36   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_passenger_detail">tax_input_passenger_detail</a>

**说明：** 进项客运发票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | name |   varchar   | 200 |   0    |    Y     |  N   |       | 乘客姓名  |
|  4   | id_card |   varchar   | 50 |   0    |    Y     |  N   |       | 身份证号  |
|  5   | time_get_on |   timestamp   | 19 |   0    |    Y     |  N   |       | 出发时间  |
|  6   | station_get_on |   varchar   | 200 |   0    |    Y     |  N   |       | 出发车站  |
|  7   | station_get_off |   varchar   | 200 |   0    |    Y     |  N   |       | 到达车站  |
|  8   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  9   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  10   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  11   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  12   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  13   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  14   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_quota_detail">tax_input_quota_detail</a>

**说明：** 进项定额发票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | province |   varchar   | 50 |   0    |    Y     |  N   |       | 省  |
|  4   | city |   varchar   | 50 |   0    |    Y     |  N   |       | 市  |
|  5   | company_seal |   tinyint   | 4 |   0    |    Y     |  N   |       |  是否有公司印章（0-没有;1-有）  |
|  6   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  7   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_requests_certification_line">tax_input_requests_certification_line</a>

**说明：** 

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | request_id |   bigint   | 20 |   0    |    Y     |  N   |       | 请求ID  |
|  3   | invoice_code |   varchar   | 20 |   0    |    Y     |  N   |       | 发票代码  |
|  4   | invoice_no |   varchar   | 20 |   0    |    Y     |  N   |       | 发票号码  |
|  5   | invoice_date |   varchar   | 20 |   0    |    Y     |  N   |       | 开票日期  |
|  6   | certification_status |   varchar   | 50 |   0    |    Y     |  N   |       | 认证状态  |
|  7   | legalize_belong_date |   varchar   | 20 |   0    |    Y     |  N   |       | 税款所属期  |
|  8   | certification_reason |   varchar   | 200 |   0    |    Y     |  N   |       | 认证失败原因  |
|  9   | total_amount |   decimal   | 23 |   4    |    N     |  N   |       | 价税合计  |
|  10   | buyer_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       | 购方纳税人识别号  |
|  11   | saler_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       | 销方纳税人识别号  |
|  12   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  14   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  15   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  17   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_requests_check_line">tax_input_requests_check_line</a>

**说明：** 税务进项接口日志信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | request_id |   bigint   | 20 |   0    |    N     |  N   |       | 请求ID  |
|  3   | invoice_code |   varchar   | 50 |   0    |    Y     |  N   |       |   |
|  4   | invoice_no |   varchar   | 30 |   0    |    Y     |  N   |       |   |
|  5   | invoice_date |   varchar   | 30 |   0    |    N     |  N   |       | 开票日期  |
|  6   | check_status |   varchar   | 10 |   0    |    N     |  N   |       | 查验状态  |
|  7   | check_error_info |   varchar   | 500 |   0    |    Y     |  N   |       |   |
|  8   | invoice_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 不含税金额  |
|  9   | buyer_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  10   | saler_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_requests_header">tax_input_requests_header</a>

**说明：** 税务进项接口日志头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | issue_employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 发起人id  |
|  3   | request_number |   varchar   | 100 |   0    |    N     |  N   |       | 请求批次号  |
|  4   | request_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 请求日期  |
|  5   | request_type |   varchar   | 100 |   0    |    N     |  N   |       | 请求类型  |
|  6   | status_code |   tinyint   | 4 |   0    |    N     |  N   |       | 请求状态  |
|  7   | response_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 响应日期  |
|  8   | request_xml |   text   | 65535 |   0    |    Y     |  N   |       | 请求内容  |
|  9   | response_xml |   text   | 65535 |   0    |    Y     |  N   |       | 响应内容  |
|  10   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  11   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  12   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  15   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_requests_info">tax_input_requests_info</a>

**说明：** 税务进项接口日志信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | request_id |   bigint   | 20 |   0    |    N     |  N   |       | 请求ID  |
|  3   | request_line_id |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  4   | process_node |   varchar   | 50 |   0    |    N     |  N   |       | 节点名称  |
|  5   | log_level |   varchar   | 50 |   0    |    N     |  N   |       | 日志级别  |
|  6   | log_info |   varchar   | 500 |   0    |    N     |  N   |       | 日志信息  |
|  7   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_taxi_detail">tax_input_taxi_detail</a>

**说明：** 进项出租车票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | name |   varchar   | 200 |   0    |    Y     |  N   |       | 乘客姓名  |
|  4   | id_card |   varchar   | 50 |   0    |    Y     |  N   |       | 身份证号  |
|  5   | time_get_on |   timestamp   | 19 |   0    |    Y     |  N   |       | 出发时间  |
|  6   | time_get_off |   timestamp   | 19 |   0    |    Y     |  N   |       | 到达时间  |
|  7   | mileage |   decimal   | 23 |   2    |    Y     |  N   |       | 里程  |
|  8   | province |   varchar   | 50 |   0    |    Y     |  N   |       | 省  |
|  9   | city |   varchar   | 50 |   0    |    Y     |  N   |       | 市  |
|  10   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_toll_detail">tax_input_toll_detail</a>

**说明：** 进项通行费详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | machine_no |   varchar   | 100 |   0    |    N     |  N   |       | 设备编号  |
|  4   | check_code |   varchar   | 100 |   0    |    N     |  N   |       | 校验码（后6位）  |
|  5   | invoice_amount |   decimal   | 23 |   4    |    Y     |  N   |       |   |
|  6   | tax_total_amount |   decimal   | 23 |   4    |    Y     |  N   |       |   |
|  7   | remark |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  8   | zero_tax_rate_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 零税率标志（空：非零税率 1：税率栏位显示“免税”， 2：税率栏位显示“不征税”， 3：零税率）  |
|  9   | traffic_fee_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 通行费标志（Y-可抵扣通行费\N-不可抵扣通行费）  |
|  10   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_trainticket_detail">tax_input_trainticket_detail</a>

**说明：** 进项火车票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | name |   varchar   | 200 |   0    |    Y     |  N   |       | 乘客姓名  |
|  4   | id_card |   varchar   | 50 |   0    |    Y     |  N   |       | 身份证号  |
|  5   | time_get_on |   timestamp   | 19 |   0    |    Y     |  N   |       | 出发时间  |
|  6   | station_get_on |   varchar   | 200 |   0    |    Y     |  N   |       | 出发车站  |
|  7   | station_get_off |   varchar   | 200 |   0    |    Y     |  N   |       | 到达车站  |
|  8   | train_number |   varchar   | 50 |   0    |    Y     |  N   |       | 车次  |
|  9   | seat |   varchar   | 20 |   0    |    Y     |  N   |       | 座位类型  |
|  10   | serial_number |   varchar   | 200 |   0    |    Y     |  N   |       | 序列号  |
|  11   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  12   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  14   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  15   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  17   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_transfer_interface">tax_input_transfer_interface</a>

**说明：** 进项转出数据接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | document_number |   varchar   | 50 |   0    |    Y     |  N   |       | 进项转出单据号  |
|  3   | je_creation_date |   varchar   | 15 |   0    |    Y     |  N   |       | 记账期间  |
|  4   | exp_report_line_id |   varchar   | 50 |   0    |    Y     |  N   |       | 报销单ID  |
|  5   | exp_report_line_num |   varchar   | 50 |   0    |    Y     |  N   |       | 报销单号  |
|  6   | use_type |   varchar   | 50 |   0    |    Y     |  N   |       | 转出类型  |
|  7   | use_type_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 转出类型名称  |
|  8   | company_id |   varchar   | 50 |   0    |    Y     |  N   |       | 公司ID  |
|  9   | company |   varchar   | 1000 |   0    |    Y     |  N   |       | 公司名称  |
|  10   | function_amount |   decimal   | 11 |   0    |    Y     |  N   |       | 转出金额  |
|  11   | taxpayer_id |   varchar   | 50 |   0    |    Y     |  N   |       | 纳税人ID  |
|  12   | taxpayer_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 纳税人名称  |
|  13   | import_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 数据来源:(默认系统接口)  |
|  14   | import_sys |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统:默认费控系统  |
|  15   | sys_date |   timestamp   | 19 |   0    |    N     |  N   |       | 数据产生日期(数据产生日期)  |
|  16   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  17   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |       |   |
|  18   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  19   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  20   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  21   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  22   | tenant_name |   varchar   | 100 |   0    |    Y     |  N   |       | 租户名称  |

**表名：** <a id="tax_input_transport_detail">tax_input_transport_detail</a>

**说明：** 进项货运发票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | machine_no |   varchar   | 100 |   0    |    N     |  N   |       | 设备编号  |
|  4   | check_code |   varchar   | 100 |   0    |    N     |  N   |       | 校验码(后6位)  |
|  5   | invoice_amount |   decimal   | 23 |   4    |    Y     |  N   |       |   |
|  6   | tax_total_amount |   decimal   | 23 |   4    |    Y     |  N   |       |   |
|  7   | remark |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  8   | drawer |   varchar   | 200 |   0    |    Y     |  N   |       | 开票人  |
|  9   | payee |   varchar   | 200 |   0    |    Y     |  N   |       | 收款人  |
|  10   | reviewer |   varchar   | 200 |   0    |    Y     |  N   |       | 复核人  |
|  11   | carrier_name |   varchar   | 200 |   0    |    Y     |  N   |       | 承运人名称  |
|  12   | carrier_tax_no |   varchar   | 200 |   0    |    Y     |  N   |       | 承运人识别号  |
|  13   | drawee_name |   varchar   | 200 |   0    |    Y     |  N   |       | 受票方名称  |
|  14   | drawee_tax_no |   varchar   | 200 |   0    |    Y     |  N   |       | 受票方识别号  |
|  15   | receive_name |   varchar   | 200 |   0    |    Y     |  N   |       | 收货人名称  |
|  16   | receive_tax_no |   varchar   | 200 |   0    |    Y     |  N   |       | 收货人识别号  |
|  17   | consignor_name |   varchar   | 200 |   0    |    Y     |  N   |       | 发货人名称  |
|  18   | consignor_tax_no |   varchar   | 200 |   0    |    Y     |  N   |       | 发货人识别号  |
|  19   | transport_goods_info |   varchar   | 200 |   0    |    Y     |  N   |       | 运输货物信息  |
|  20   | through_address |   varchar   | 200 |   0    |    Y     |  N   |       | 起运地、经由、到达地  |
|  21   | tax_disk_number |   varchar   | 200 |   0    |    Y     |  N   |       | 税控盘号  |
|  22   | car_number |   varchar   | 200 |   0    |    Y     |  N   |       | 车种车号  |
|  23   | vehicle_tonnage |   varchar   | 200 |   0    |    Y     |  N   |       | 车船吨位  |
|  24   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  27   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  28   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_input_vat_detail">tax_input_vat_detail</a>

**说明：** 进项增值税发票详情表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头表ID  |
|  3   | machine_no |   varchar   | 100 |   0    |    N     |  N   |       | 机器设备编号(同上)  |
|  4   | check_code |   varchar   | 100 |   0    |    N     |  N   |       | 校验码(后6位)(同上)  |
|  5   | invoice_amount |   decimal   | 23 |   2    |    N     |  N   |       | 不含税金额合计  |
|  6   | tax_total_amount |   decimal   | 23 |   2    |    N     |  N   |       | 税额合计  |
|  7   | remark |   varchar   | 100 |   0    |    Y     |  N   |       | 备注  |
|  8   | drawer |   varchar   | 200 |   0    |    Y     |  N   |       | 开票人  |
|  9   | payee |   varchar   | 200 |   0    |    Y     |  N   |       | 收款人  |
|  10   | reviewer |   varchar   | 200 |   0    |    Y     |  N   |       | 复核人  |
|  11   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  12   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  14   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  15   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  17   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_investor_info">tax_investor_info</a>

**说明：** 投资信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | investor_name |   varchar   | 300 |   0    |    Y     |  N   |       | 被投资者名称  |
|  4   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  5   | economic_nature |   varchar   | 100 |   0    |    Y     |  N   |       | 经济性质  |
|  6   | investment_ratio |   decimal   | 23 |   4    |    Y     |  N   |       | 投资比例  |
|  7   | investment_amount |   bigint   | 20 |   0    |    Y     |  N   |       | 投资金额  |
|  8   | registered_address |   varchar   | 4000 |   0    |    Y     |  N   |       | 注册地址  |
|  9   | description |   varchar   | 4000 |   0    |    Y     |  N   |       | 说明  |
|  10   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  11   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  12   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  13   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  14   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  15   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_invoice_applicant">tax_invoice_applicant</a>

**说明：** 申请人开票申请信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 200 |   0    |    N     |  N   |       | 申请编号  |
|  3   | scene_type |   varchar   | 100 |   0    |    N     |  N   |       | 申请场景类型  |
|  4   | apply_invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 申请类型  |
|  5   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  6   | separate_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 业务类型组合对应的价税分离id  |
|  7   | invoice_title |   varchar   | 100 |   0    |    Y     |  N   |       | 开票名称/开票项目  |
|  8   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户id  |
|  9   | client_name |   varchar   | 200 |   0    |    N     |  N   |       | 客户名称  |
|  10   | client_tax_num |   varchar   | 200 |   0    |    N     |  N   |       | 客户纳税人识别号  |
|  11   | client_tax_bank |   varchar   | 300 |   0    |    Y     |  N   |       | 客户开户行  |
|  12   | client_tax_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 客户银行账号  |
|  13   | client_tax_add |   varchar   | 300 |   0    |    Y     |  N   |       | 客户地址  |
|  14   | client_tax_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 客户电话  |
|  15   | business_num |   varchar   | 100 |   0    |    Y     |  N   |       | 业务订单单据编号如保单号交易订单合同编号等  |
|  16   | apply_total_amount |   decimal   | 21 |   2    |    N     |  N   |       | 申请价税合计金额  |
|  17   | memo |   varchar   | 1000 |   0    |    Y     |  N   |       | 备注  |
|  18   | applicant_status |   varchar   | 100 |   0    |    Y     |  N   |       | 申请状态  |
|  19   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  20   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  21   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  22   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  23   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  24   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  25   | contact_info |   varchar   | 100 |   0    |    Y     |  N   |       | 联系方式  |

**表名：** <a id="tax_invoice_apply_header">tax_invoice_apply_header</a>

**说明：** 交易流水开票申请头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 200 |   0    |    N     |  N   |       | 申请编号  |
|  3   | apply_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型（交易流水开票申请）  |
|  4   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务审批状态  |
|  5   | apply_person_id |   varchar   | 100 |   0    |    N     |  N   |       | 申请人ID  |
|  6   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  7   | invoice_site_id |   bigint   | 20 |   0    |    N     |  N   |       | 开票点ID  |
|  8   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  9   | output_tax_disk_firm |   varchar   | 100 |   0    |    N     |  N   |       | 销项盘商接口  |
|  10   | document_oid |   varchar   | 36 |   0    |    Y     |  N   |       | 单据OID  |
|  11   | form_oid |   varchar   | 36 |   0    |    Y     |  N   |       | 表单OID  |
|  12   | application_oid |   varchar   | 50 |   0    |    Y     |  N   |       | 申请人OID  |
|  13   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  14   | memo |   varchar   | 2000 |   0    |    Y     |  N   |       | 备注  |
|  15   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  16   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  17   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  18   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  19   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  20   | applicant_oid |   varchar   | 100 |   0    |    Y     |  N   |       | 申请人oid  |
|  21   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  22   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       | 附件  |
|  23   | tax_invoice_applicant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人开票申请信息表主键ID  |
|  24   | push_method |   varchar   | 100 |   0    |    Y     |  N   |       | 推送方式  |
|  25   | push_address |   varchar   | 100 |   0    |    Y     |  N   |       | 推送地址/推送号码  |

**表名：** <a id="tax_invoice_apply_line">tax_invoice_apply_line</a>

**说明：** 交易流水开票申请行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 开票申请头ID  |
|  3   | tran_invoice_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 交易流水ID  |
|  4   | tran_num |   varchar   | 100 |   0    |    N     |  N   |       | 交易流水号  |
|  5   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户ID  |
|  6   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  7   | invoice_amount |   decimal   | 23 |   2    |    N     |  N   |       | 本次开票金额（含税价）  |
|  8   | tax_rate_id |   varchar   | 100 |   0    |    N     |  N   |       | 增值税税目ID  |
|  9   | vat_rate |   decimal   | 23 |   2    |    N     |  N   |       | 税率%  |
|  10   | preferential_tax_rate |   decimal   | 23 |   4    |    Y     |  N   |       | 优惠税率  |
|  11   | deduct_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 是否差额征税Y/N  |
|  12   | deduct_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 扣除额  |
|  13   | sales |   decimal   | 23 |   2    |    N     |  N   |       | 不含税金额  |
|  14   | taxes |   decimal   | 23 |   2    |    N     |  N   |       | 税额  |
|  15   | invoice_title |   varchar   | 100 |   0    |    N     |  N   |       | 开票名称  |
|  16   | goods_id |   bigint   | 20 |   0    |    N     |  N   |       | 商品编码ID  |
|  17   | zero_rate_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 零税率标识，空非零税率、0：出口退税；1：免税；2：不征税；3：普通零税率  |
|  18   | receipt_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 收款人  |
|  19   | check_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 复核人  |
|  20   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  21   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  22   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  23   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  24   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  25   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_invoice_line_expense">tax_invoice_line_expense</a>

**说明：** 发票行报销记录表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_dist_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票分配行ID  |
|  3   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  4   | invoice_no |   varchar   | 30 |   0    |    Y     |  N   |       | 发票号码  |
|  5   | invoice_code |   varchar   | 30 |   0    |    Y     |  N   |       | 发票代码  |
|  6   | detail_amount |   decimal   | 21 |   2    |    N     |  N   |       | 金额  |
|  7   | tax_rate |   varchar   | 30 |   0    |    N     |  N   |       | 税率  |
|  8   | tax_amount |   decimal   | 21 |   2    |    N     |  N   |       | 税额  |
|  9   | exp_expense_head_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联报账单头ID  |
|  10   | requisition_number |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单单号  |
|  11   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  12   | department_code |   varchar   | 100 |   0    |    Y     |  N   |       | 部门代码  |
|  13   | document_type |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单类型  |
|  14   | employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人ID  |
|  15   | requisition_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 申请日期  |
|  16   | exp_expense_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联报账单行ID  |
|  17   | expense_type_code |   varchar   | 100 |   0    |    Y     |  N   |       | 费用类型代码  |
|  18   | description |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单行备注  |
|  19   | status |   varchar   | 30 |   0    |    N     |  N   |       | 状态  |
|  20   | invoice_mate_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 发票匹配标志  |
|  21   | reverse_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 反冲标识  |
|  22   | exp_expense_reverse_head_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联反冲单头ID  |
|  23   | exp_expense_reverse_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联反冲单行ID  |
|  24   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  25   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  26   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  27   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  28   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  29   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  30   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  31   | department_id |   bigint   | 20 |   0    |    Y     |  N   |       | 部门ID  |
|  32   | expense_type_name |   varchar   | 100 |   0    |    Y     |  N   |       | 费用类型名称  |
|  33   | expense_type_id |   bigint   | 20 |   0    |    Y     |  N   |       | 费用类型ID  |
|  34   | expense_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 费用金额  |

**表名：** <a id="tax_lut_land_basic_info">tax_lut_land_basic_info</a>

**说明：** 土地基础信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税人识别号ID  |
|  3   | seller_type_code |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税主体类型  |
|  4   | tax_department_id |   bigint   | 20 |   0    |    Y     |  N   |       | 所属税务机关ID  |
|  5   | user_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 土地使用人ID  |
|  6   | land_num |   varchar   | 100 |   0    |    Y     |  N   |       | 地号  |
|  7   | land_source |   varchar   | 100 |   0    |    Y     |  N   |       | 土地来源  |
|  8   | land_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地名称  |
|  9   | land_right_num |   varchar   | 100 |   0    |    Y     |  N   |       | 土地使用权证号  |
|  10   | land_character_code |   varchar   | 100 |   0    |    Y     |  N   |       | 土地性质  |
|  11   | gaining_mathod_code |   varchar   | 100 |   0    |    Y     |  N   |       | 土地取得方式  |
|  12   | land_usage_code |   varchar   | 100 |   0    |    Y     |  N   |       | 土地用途  |
|  13   | province |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落省份  |
|  14   | city |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落城市  |
|  15   | county |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落县（区）  |
|  16   | land_location |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落街道+详细地址  |
|  17   | land_area |   varchar   | 100 |   0    |    Y     |  N   |       | 土地面积  |
|  18   | land_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 土地取得时间  |
|  19   | land_level |   varchar   | 100 |   0    |    Y     |  N   |       | 土地等级  |
|  20   | tax_standard |   decimal   | 21 |   2    |    Y     |  N   |       | 税额标准  |
|  21   | tax_incentives_ratio |   decimal   | 21 |   2    |    Y     |  N   |       | 优惠比例%  |
|  22   | tax_start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 缴纳起始日期  |
|  23   | tax_end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 缴纳终止日期  |
|  24   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  27   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  28   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  31   | tax_bld_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 城镇土地使用税税率定义表ID  |
|  32   | user_taxpayer_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地使用人名称  |
|  33   | user_taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 土地使用人纳税识别号  |
|  34   | province_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落省份名称  |
|  35   | city_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落城市名称  |
|  36   | county_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落县（区）名称  |
|  37   | city_id |   bigint   | 20 |   0    |    Y     |  N   |       | 土地坐落城市Id  |

**表名：** <a id="tax_lut_land_info_t">tax_lut_land_info_t</a>

**说明：** 土地基础信息导入临时表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税人识别号ID  |
|  3   | seller_type_code |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税主体类型  |
|  4   | tax_department_id |   bigint   | 20 |   0    |    Y     |  N   |       | 所属税务机关ID  |
|  5   | user_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 土地使用人ID  |
|  6   | land_num |   varchar   | 100 |   0    |    Y     |  N   |       | 地号  |
|  7   | land_source |   varchar   | 100 |   0    |    Y     |  N   |       | 土地来源  |
|  8   | land_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地名称  |
|  9   | land_right_num |   varchar   | 100 |   0    |    Y     |  N   |       | 土地使用权证号  |
|  10   | land_character_code |   varchar   | 100 |   0    |    Y     |  N   |       | 土地性质  |
|  11   | gaining_mathod_code |   varchar   | 100 |   0    |    Y     |  N   |       | 土地取得方式  |
|  12   | land_usage_code |   varchar   | 100 |   0    |    Y     |  N   |       | 土地用途  |
|  13   | province |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落省份  |
|  14   | city |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落城市  |
|  15   | county |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落县（区）  |
|  16   | land_location |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落街道+详细地址  |
|  17   | land_area |   varchar   | 100 |   0    |    Y     |  N   |       | 土地面积  |
|  18   | land_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 土地取得时间  |
|  19   | land_level |   varchar   | 100 |   0    |    Y     |  N   |       | 土地等级  |
|  20   | tax_standard |   decimal   | 21 |   2    |    Y     |  N   |       | 税额标准  |
|  21   | tax_incentives_ratio |   decimal   | 21 |   2    |    Y     |  N   |       | 优惠比例%  |
|  22   | tax_start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 缴纳起始日期  |
|  23   | tax_end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 缴纳终止日期  |
|  24   | tax_bld_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 城镇土地使用税税率定义表ID  |
|  25   | user_taxpayer_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地使用人名称  |
|  26   | user_taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 土地使用人纳税识别号  |
|  27   | province_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落省份名称  |
|  28   | city_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落城市名称  |
|  29   | county_name |   varchar   | 100 |   0    |    Y     |  N   |       | 土地坐落县（区）名称  |
|  30   | city_id |   bigint   | 20 |   0    |    Y     |  N   |       | 土地坐落城市Id  |
|  31   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  32   | batch_number |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  33   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  34   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  35   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  36   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  37   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  38   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  39   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  40   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  41   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  42   | tax_department_code |   varchar   | 100 |   0    |    Y     |  N   |       | 所属税务机关code  |
|  43   | enabled_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 是否启用  |
|  44   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  45   | string_tax_end_date |   varchar   | 100 |   0    |    Y     |  N   |       | String格式的缴纳终止日期  |
|  46   | string_land_date |   varchar   | 100 |   0    |    Y     |  N   |       | String格式的土地取得时间  |

**表名：** <a id="tax_lut_reduction_info">tax_lut_reduction_info</a>

**说明：** 土地使用税税收优惠信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | lut_land_basic_info_id |   bigint   | 20 |   0    |    N     |  N   |       | 基础信息表id  |
|  3   | tax_reduction_id |   bigint   | 20 |   0    |    Y     |  N   |       | 减免税项目id  |
|  4   | tax_reduction_code |   varchar   | 100 |   0    |    Y     |  N   |       | 减免税项目代码  |
|  5   | tax_reduction_name |   varchar   | 100 |   0    |    Y     |  N   |       | 减免税项目名称  |
|  6   | reduction_start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 减免缴纳起始日期  |
|  7   | reduction_end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 减免缴纳终止日期  |
|  8   | tax_reduction_area |   decimal   | 21 |   2    |    Y     |  N   |       | 减免税土地面积  |
|  9   | tax_reduction_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 减免税金额  |
|  10   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  11   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  12   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  15   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  16   | line_num |   bigint   | 20 |   0    |    Y     |  N   |       | 序号  |

**表名：** <a id="tax_profit_interface">tax_profit_interface</a>

**说明：** 利润表接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | ledger_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账套名称  |
|  3   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  4   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  5   | item_code |   int   | 10 |   0    |    Y     |  N   |       | 项目代码(项目代码取报表栏次)  |
|  6   | item_name |   varchar   | 100 |   0    |    Y     |  N   |       | 项目名称（项目为报表各个项目名称）  |
|  7   | period_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本月数  |
|  8   | year_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本年累计数  |
|  9   | dispose_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 处理标识  |
|  10   | error_message |   varchar   | 100 |   0    |    Y     |  N   |       | 错误信息  |
|  11   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  12   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  15   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  17   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_profit_sheet">tax_profit_sheet</a>

**说明：** 利润表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  3   | ledger_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账套名称  |
|  4   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  5   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  6   | item_code |   varchar   | 100 |   0    |    Y     |  N   |       | 项目代码  |
|  7   | item_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 项目名称  |
|  8   | period_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本月数  |
|  9   | year_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本年累计数  |
|  10   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  11   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  12   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  13   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  15   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_profit_sheet_temp">tax_profit_sheet_temp</a>

**说明：** 利润导入表表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  3   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  4   | ledger_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账套名称  |
|  5   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  6   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 期间  |
|  7   | item_code |   varchar   | 100 |   0    |    Y     |  N   |       | 项目代码(项目代码取报表栏次)  |
|  8   | item_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 项目名称（项目为报表各个项目名称）  |
|  9   | period_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 本月数  |
|  10   | year_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 本年累计数  |
|  11   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  12   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  13   | error_detail |   varchar   | 1000 |   0    |    Y     |  N   |       | 错误信息  |
|  14   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  15   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  16   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  17   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  18   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  19   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  20   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_qr_code_statics_header">tax_qr_code_statics_header</a>

**说明：** 静态二维码管理头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | qr_code_number |   varchar   | 200 |   0    |    N     |  N   |       | 二维码编号  |
|  3   | qr_code_name |   varchar   | 200 |   0    |    N     |  N   |       | 二维码名称  |
|  4   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  5   | invoice_site_id |   bigint   | 20 |   0    |    N     |  N   |       | 开票点id  |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  8   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_qr_code_statics_line">tax_qr_code_statics_line</a>

**说明：** 静态二维码管理行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | qr_code_header_id |   bigint   | 20 |   0    |    N     |  N   |       | 二维码头表id  |
|  3   | line_num |   varchar   | 100 |   0    |    N     |  N   |       | 序号  |
|  4   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  5   | separate_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 业务类型组合对应的价税分离id  |
|  6   | invoice_title |   varchar   | 100 |   0    |    Y     |  N   |       | 开票名称/开票项目  |
|  7   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_rate">tax_rate</a>

**说明：** 税率定义表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_rate |   varchar   | 100 |   0    |    N     |  N   |       | 税率  |
|  3   | tax_ratio |   decimal   | 23 |   4    |    Y     |  N   |       | 计税税率  |
|  4   | preferential_tax_rate |   decimal   | 23 |   4    |    Y     |  N   |       | 优惠税率  |
|  5   | tax_category_id |   bigint   | 20 |   0    |    N     |  N   |       | 税种id  |
|  6   | remarks |   varchar   | 200 |   0    |    Y     |  N   |       | 备注  |
|  7   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  13   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  14   | tax_basis |   varchar   | 300 |   0    |    Y     |  N   |       | 计税依据  |
|  15   | tax_items |   varchar   | 300 |   0    |    Y     |  N   |       | 税目  |
|  16   | tax_calculate_category |   varchar   | 300 |   0    |    Y     |  N   |       | 计税类型  |
|  17   | tax_roll |   decimal   | 21 |   2    |    Y     |  N   |       | 计税税金  |

**表名：** <a id="tax_register_app_temp">tax_register_app_temp</a>

**说明：** 税务登记导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人识别号  |
|  3   | taxpayer_name |   varchar   | 300 |   0    |    Y     |  N   |       | 纳税人名称  |
|  4   | taxpayer_number_type |   varchar   | 30 |   0    |    Y     |  N   |       | 税号类型  |
|  5   | type_of_business |   varchar   | 30 |   0    |    Y     |  N   |       | 登记注册类型  |
|  6   | tax_qualification |   varchar   | 30 |   0    |    Y     |  N   |       | 纳税资质  |
|  7   | main_industry |   varchar   | 300 |   0    |    Y     |  N   |       | 国际行业（主行业）  |
|  8   | listed_company |   varchar   | 30 |   0    |    Y     |  N   |       | 是否为上市公司  |
|  9   | overseas_reg_res_ent |   varchar   | 30 |   0    |    Y     |  N   |       | 是否为境外注册居民企业  |
|  10   | taxpayer_address |   varchar   | 300 |   0    |    Y     |  N   |       | 纳税人地址  |
|  11   | client_tax_bank |   varchar   | 200 |   0    |    Y     |  N   |       | 银行开户行  |
|  12   | bank_account_number |   varchar   | 50 |   0    |    Y     |  N   |       | 银行账号  |
|  13   | taxpayer_tel |   varchar   | 50 |   0    |    Y     |  N   |       | 纳税人电话  |
|  14   | nat_tax_auth_code |   varchar   | 100 |   0    |    Y     |  N   |       | 主管税务机关  |
|  15   | parent_taxpayer_number |   varchar   | 100 |   0    |    Y     |  N   |       | 上级纳税主体  |
|  16   | company_type |   varchar   | 50 |   0    |    Y     |  N   |       | 单位性质  |
|  17   | accounting_system |   varchar   | 50 |   0    |    Y     |  N   |       | 适用会计制度  |
|  18   | accounting_method |   varchar   | 50 |   0    |    Y     |  N   |       | 核算方式  |
|  19   | affiliation_code |   varchar   | 50 |   0    |    Y     |  N   |       | 所属机构（代码）  |
|  20   | business_scope |   varchar   | 300 |   0    |    Y     |  N   |       | 经营范围  |
|  21   | registered_capital |   varchar   | 100 |   0    |    Y     |  N   |       | 注册资金  |
|  22   | operation_address |   varchar   | 300 |   0    |    Y     |  N   |       | 生产经营地址  |
|  23   | postal_code |   varchar   | 100 |   0    |    Y     |  N   |       | 邮政编码  |
|  24   | operating_period |   varchar   | 100 |   0    |    Y     |  N   |       | 营业期限  |
|  25   | legal_representative |   varchar   | 100 |   0    |    Y     |  N   |       | 法人代表  |
|  26   | registered_address |   varchar   | 300 |   0    |    Y     |  N   |       | 注册地址  |
|  27   | order_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  28   | batch_number |   varchar   | 36 |   0    |    Y     |  N   |       | 批次号  |
|  29   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  30   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  31   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  32   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  33   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  34   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  35   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  36   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_register_apply">tax_register_apply</a>

**说明：** 税务登记申请表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_code |   varchar   | 30 |   0    |    N     |  N   |       | 申请编码  |
|  3   | transaction_type |   varchar   | 30 |   0    |    N     |  N   |       | 事务类型  |
|  4   | transaction_status |   varchar   | 30 |   0    |    N     |  N   |       | 事务状态  |
|  5   | applicant_id |   bigint   | 20 |   0    |    N     |  N   |       | 申请人  |
|  6   | taxpayer_name |   varchar   | 300 |   0    |    N     |  N   |       | 纳税人名称  |
|  7   | taxpayer_number |   varchar   | 100 |   0    |    N     |  N   |       | 纳税人识别号  |
|  8   | taxpayer_number_type |   varchar   | 20 |   0    |    Y     |  N   |       | 税号类型  |
|  9   | type_of_business |   varchar   | 20 |   0    |    Y     |  N   |       | 登记注册类型  |
|  10   | tax_qualification |   varchar   | 20 |   0    |    Y     |  N   |       | 纳税资质  |
|  11   | main_industry |   varchar   | 100 |   0    |    Y     |  N   |       | 国际行业（主行业）  |
|  12   | listed_company |   tinyint   | 4 |   0    |    Y     |  N   |   1    | 是否为上市公司  |
|  13   | overseas_reg_res_ent |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否为境外注册居民企业  |
|  14   | taxpayer_address |   varchar   | 4000 |   0    |    Y     |  N   |       | 纳税人地址  |
|  15   | client_tax_bank |   varchar   | 300 |   0    |    Y     |  N   |       | 银行开户行  |
|  16   | bank_account_number |   varchar   | 30 |   0    |    Y     |  N   |       | 银行账号  |
|  17   | taxpayer_tel |   varchar   | 30 |   0    |    Y     |  N   |       | 纳税人电话  |
|  18   | nat_tax_auth |   bigint   | 20 |   0    |    Y     |  N   |       | 主管税务机关  |
|  19   | company_type |   varchar   | 20 |   0    |    Y     |  N   |       | 单位性质  |
|  20   | accounting_system |   varchar   | 20 |   0    |    Y     |  N   |       | 适用会计制度  |
|  21   | accounting_method |   varchar   | 20 |   0    |    Y     |  N   |       | 核算方式  |
|  22   | affiliation |   bigint   | 20 |   0    |    Y     |  N   |       | 所属机构  |
|  23   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  24   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  25   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  27   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  28   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  29   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司id  |
|  30   | business_scope |   varchar   | 400 |   0    |    Y     |  N   |       | 经营范围  |
|  31   | registered_capital |   decimal   | 21 |   2    |    Y     |  N   |       | 注册资金  |
|  32   | operation_address |   varchar   | 400 |   0    |    Y     |  N   |       | 生产经营地址  |
|  33   | postal_code |   varchar   | 20 |   0    |    Y     |  N   |       | 邮政编码  |
|  34   | operating_period |   varchar   | 100 |   0    |    Y     |  N   |       | 营业期限  |
|  35   | legal_representative |   varchar   | 100 |   0    |    Y     |  N   |       | 法人代表  |
|  36   | registered_address |   varchar   | 400 |   0    |    Y     |  N   |       | 注册地址  |
|  37   | parent_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 上级纳税主体ID  |
|  38   | form_oid |   varchar   | 500 |   0    |    Y     |  N   |       | 表单oid  |
|  39   | document_oid |   varchar   | 500 |   0    |    Y     |  N   |       | 单据oid  |
|  40   | applicant_oid |   varchar   | 500 |   0    |    Y     |  N   |       | 申请人oid  |
|  41   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       | 附件  |
|  42   | taxpayer_type_effe_time |   timestamp   | 19 |   0    |    Y     |  N   |       | 纳税资质生效日期  |
|  43   | taxpayer_start_time |   timestamp   | 19 |   0    |    Y     |  N   |       | 税务启用日期  |
|  44   | taxpayer_end_time |   timestamp   | 19 |   0    |    Y     |  N   |       | 税号停用日期  |

**表名：** <a id="tax_register_basic">tax_register_basic</a>

**说明：** 税务登记基础信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_name |   varchar   | 300 |   0    |    N     |  N   |       | 纳税人名称  |
|  3   | taxpayer_number |   varchar   | 100 |   0    |    N     |  N   |       | 纳税人识别号  |
|  4   | taxpayer_number_type |   varchar   | 20 |   0    |    Y     |  N   |       | 税号类型  |
|  5   | type_of_business |   varchar   | 20 |   0    |    Y     |  N   |       | 登记注册类型  |
|  6   | tax_qualification |   varchar   | 20 |   0    |    Y     |  N   |       | 纳税资质  |
|  7   | main_industry |   varchar   | 100 |   0    |    Y     |  N   |       | 国际行业（主行业）  |
|  8   | listed_company |   tinyint   | 4 |   0    |    Y     |  N   |   1    | 是否为上市公司  |
|  9   | overseas_reg_res_ent |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否为境外注册居民企业  |
|  10   | registration_status |   varchar   | 30 |   0    |    N     |  N   |       | 税号状态  |
|  11   | business_scope |   varchar   | 400 |   0    |    Y     |  N   |       | 经营范围  |
|  12   | registered_capital |   decimal   | 21 |   2    |    Y     |  N   |       | 注册资金  |
|  13   | operation_address |   varchar   | 400 |   0    |    Y     |  N   |       | 生产经营地址  |
|  14   | postal_code |   varchar   | 10 |   0    |    Y     |  N   |       | 邮政编码  |
|  15   | operating_period |   varchar   | 10 |   0    |    Y     |  N   |       | 营业期限  |
|  16   | legal_representative |   varchar   | 100 |   0    |    Y     |  N   |       | 法人代表  |
|  17   | registered_address |   varchar   | 400 |   0    |    Y     |  N   |       | 注册地址  |
|  18   | taxpayer_address |   varchar   | 4000 |   0    |    Y     |  N   |       | 纳税人地址  |
|  19   | client_tax_bank |   varchar   | 300 |   0    |    Y     |  N   |       | 银行开户行  |
|  20   | bank_account_number |   varchar   | 30 |   0    |    Y     |  N   |       | 银行账号  |
|  21   | taxpayer_tel |   varchar   | 30 |   0    |    Y     |  N   |       | 纳税人电话  |
|  22   | nat_tax_auth |   bigint   | 20 |   0    |    Y     |  N   |       | 主管税务机关  |
|  23   | company_type |   varchar   | 20 |   0    |    Y     |  N   |       | 单位性质  |
|  24   | accounting_system |   varchar   | 20 |   0    |    Y     |  N   |       | 适用会计制度  |
|  25   | accounting_method |   varchar   | 20 |   0    |    Y     |  N   |       | 核算方式  |
|  26   | affiliation |   bigint   | 20 |   0    |    Y     |  N   |       | 所属机构  |
|  27   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  28   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  29   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  30   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  31   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  32   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  33   | parent_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 上级纳税主体ID  |
|  34   | applicant_id |   bigint   | 20 |   0    |    N     |  N   |       | 申请人  |
|  35   | transaction_type |   varchar   | 30 |   0    |    Y     |  N   |       | 事务类型  |
|  36   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司id  |
|  37   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       | 附件  |
|  38   | taxpayer_type_effe_time |   varchar   | 50 |   0    |    Y     |  N   |       | 纳税资质生效日期  |
|  39   | taxpayer_start_time |   varchar   | 50 |   0    |    Y     |  N   |       | 税务启用日期  |
|  40   | taxpayer_end_time |   varchar   | 50 |   0    |    Y     |  N   |       | 税号停用日期  |

**表名：** <a id="tax_requests_ocr_line">tax_requests_ocr_line</a>

**说明：** 税务发票OCR识别接口日志行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | request_id |   bigint   | 20 |   0    |    N     |  N   |       | 请求ID  |
|  3   | invoice_code |   varchar   | 30 |   0    |    N     |  N   |       | 发票代码  |
|  4   | invoice_no |   varchar   | 30 |   0    |    Y     |  N   |       |   |
|  5   | invoice_date |   varchar   | 30 |   0    |    N     |  N   |       | 开票日期  |
|  6   | ocr_status |   varchar   | 30 |   0    |    N     |  N   |       | OCR识别状态  |
|  7   | import_flag |   varchar   | 30 |   0    |    Y     |  N   |       | OCR识别状态  |
|  8   | ocr_error_info |   varchar   | 300 |   0    |    Y     |  N   |       | OCR识别状态  |
|  9   | invoice_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 不含税金额  |
|  10   | buyer_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  11   | saler_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  12   | check_code |   varchar   | 30 |   0    |    Y     |  N   |       | 发票校验码  |
|  13   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  14   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  15   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  16   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  17   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  18   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_revenue_reduct">tax_revenue_reduct</a>

**说明：** 国债、基金减免税收入来源表数据表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税主体ID  |
|  3   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  4   | cost_center_code |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心代码  |
|  5   | tran_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  6   | tran_type_code |   varchar   | 100 |   0    |    Y     |  N   |       | 交易类型代码  |
|  7   | tran_type_name |   varchar   | 100 |   0    |    Y     |  N   |       | 交易类型名称  |
|  8   | product_code |   varchar   | 100 |   0    |    Y     |  N   |       | 产品代码  |
|  9   | product_name |   varchar   | 100 |   0    |    Y     |  N   |       | 产品名称  |
|  10   | category |   varchar   | 100 |   0    |    Y     |  N   |       | 类别  |
|  11   | account_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账号名称  |
|  12   | quantity |   int   | 10 |   0    |    Y     |  N   |       | 交易数量  |
|  13   | tran_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 交易金额  |
|  14   | accrued_interest |   decimal   | 21 |   2    |    Y     |  N   |       | 交易应计利息  |
|  15   | receipt_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 交易收付金额  |
|  16   | reduction_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 免税金额  |
|  17   | memo |   varchar   | 1000 |   0    |    Y     |  N   |       | 备注  |
|  18   | purchase_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 买入日  |
|  19   | previous_interest_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 上一付息日  |
|  20   | trade_place |   varchar   | 100 |   0    |    Y     |  N   |       | 场所  |
|  21   | attachment_num |   varchar   | 100 |   0    |    Y     |  N   |       | 附件序号  |
|  22   | journal_num |   varchar   | 100 |   0    |    Y     |  N   |       | 凭证号  |
|  23   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  24   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  25   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  27   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  28   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  29   | create_type |   varchar   | 30 |   0    |    Y     |  N   |       | 创建方式  |

**表名：** <a id="tax_revenue_reduct_temp">tax_revenue_reduct_temp</a>

**说明：** 国债、基金减免税收入来源表接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  3   | cost_center_code |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心代码  |
|  4   | tran_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  5   | tran_type_code |   varchar   | 100 |   0    |    Y     |  N   |       | 交易类型代码  |
|  6   | tran_type_name |   varchar   | 100 |   0    |    Y     |  N   |       | 交易类型名称  |
|  7   | product_code |   varchar   | 100 |   0    |    Y     |  N   |       | 产品代码  |
|  8   | product_name |   varchar   | 100 |   0    |    Y     |  N   |       | 产品名称  |
|  9   | category |   varchar   | 100 |   0    |    Y     |  N   |       | 类别  |
|  10   | account_name |   varchar   | 100 |   0    |    Y     |  N   |       | 账号名称  |
|  11   | quantity |   int   | 10 |   0    |    Y     |  N   |       | 交易数量  |
|  12   | tran_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 交易金额  |
|  13   | accrued_interest |   decimal   | 21 |   2    |    Y     |  N   |       | 交易应计利息  |
|  14   | receipt_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 交易收付金额  |
|  15   | reduction_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 免税金额  |
|  16   | memo |   varchar   | 1000 |   0    |    Y     |  N   |       | 备注  |
|  17   | purchase_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 买入日  |
|  18   | previous_interest_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 上一付息日  |
|  19   | trade_place |   varchar   | 100 |   0    |    Y     |  N   |       | 场所  |
|  20   | attachment_num |   varchar   | 100 |   0    |    Y     |  N   |       | 附件序号  |
|  21   | journal_num |   varchar   | 100 |   0    |    Y     |  N   |       | 凭证号  |
|  22   | dispose_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 处理标识  |
|  23   | error_message |   varchar   | 100 |   0    |    Y     |  N   |       | 错误信息  |
|  24   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  25   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  26   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  27   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  28   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  29   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  30   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_risk_degree">tax_risk_degree</a>

**说明：** 税务风险程度表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_risk_index_id |   bigint   | 20 |   0    |    N     |  N   |       | 风险预警指标ID  |
|  3   | risk_degree |   varchar   | 200 |   0    |    Y     |  N   |       | 风险程度  |
|  4   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  10   | lower_limit |   decimal   | 21 |   2    |    Y     |  N   |       | 下限  |
|  11   | upper_limit |   decimal   | 21 |   2    |    Y     |  N   |       | 上限  |

**表名：** <a id="tax_risk_index">tax_risk_index</a>

**说明：** 税务风险预警指标定义表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_type |   varchar   | 200 |   0    |    Y     |  N   |       | 税种  |
|  3   | risk_index_type |   varchar   | 200 |   0    |    Y     |  N   |       | 指标类型  |
|  4   | risk_index_code |   varchar   | 200 |   0    |    Y     |  N   |       | 指标编码  |
|  5   | risk_index_name |   varchar   | 200 |   0    |    Y     |  N   |       | 指标名称  |
|  6   | risk_index_explain |   varchar   | 1000 |   0    |    Y     |  N   |       | 指标描述  |
|  7   | risk_index_cal |   varchar   | 200 |   0    |    Y     |  N   |       | 指标公式  |
|  8   | risk_auxiliary_cal |   varchar   | 200 |   0    |    Y     |  N   |       | 辅助公式  |
|  9   | sql_text |   varchar   | 1000 |   0    |    Y     |  N   |       | 系统取值  |
|  10   | importance_degree |   varchar   | 100 |   0    |    Y     |  N   |       | 系统取值  |
|  11   | scope_application |   varchar   | 200 |   0    |    Y     |  N   |       | 适用范围  |
|  12   | cycle_precision |   varchar   | 200 |   0    |    Y     |  N   |       | 周期精度  |
|  13   | rule_type |   varchar   | 200 |   0    |    Y     |  N   |       | 预警规则  |
|  14   | warning_value |   decimal   | 21 |   2    |    Y     |  N   |       | 预警值  |
|  15   | warning_value_ul |   decimal   | 21 |   2    |    Y     |  N   |       | 预警上限  |
|  16   | warning_value_ll |   decimal   | 21 |   2    |    Y     |  N   |       | 预警下限  |
|  17   | risk_orientation |   varchar   | 200 |   0    |    Y     |  N   |       | 指标风险指向  |
|  18   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  19   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  20   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  21   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  22   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  23   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  24   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  25   | calc_model_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 计算模型名称  |
|  26   | start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 启用日期  |
|  27   | end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 失效日期  |

**表名：** <a id="tax_risk_inspection">tax_risk_inspection</a>

**说明：** 税务风险检查情况统计表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 纳税人识别号id  |
|  3   | data_year |   varchar   | 100 |   0    |    Y     |  N   |       | 填报年度  |
|  4   | inspected_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 被检查纳税人识别号id  |
|  5   | inspection_scope |   varchar   | 1000 |   0    |    Y     |  N   |       | 检查范围  |
|  6   | cycle_precision |   varchar   | 100 |   0    |    Y     |  N   |       | 周期精度  |
|  7   | period |   varchar   | 100 |   0    |    Y     |  N   |       | 检查期间  |
|  8   | file_name |   varchar   | 100 |   0    |    Y     |  N   |       | 检查文件名称及文号  |
|  9   | nature |   varchar   | 100 |   0    |    Y     |  N   |       | 检查主体性质  |
|  10   | subject_examination |   varchar   | 100 |   0    |    Y     |  N   |       | 检查主体（即税务登记监管部门）  |
|  11   | tax_matter |   varchar   | 1000 |   0    |    Y     |  N   |       | 查补税款事项（请详细描述）  |
|  12   | tax_category |   varchar   | 100 |   0    |    Y     |  N   |       | 税种  |
|  13   | problem_category |   varchar   | 100 |   0    |    Y     |  N   |       | 问题分类  |
|  14   | tax_supplemented_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 查补税款金额  |
|  15   | late_fee |   decimal   | 21 |   2    |    Y     |  N   |       | 滞纳金  |
|  16   | fine |   decimal   | 21 |   2    |    Y     |  N   |       | 罚款  |
|  17   | credit_rating |   varchar   | 100 |   0    |    Y     |  N   |       | 是否影响纳税信用评级  |
|  18   | handling_decision |   varchar   | 100 |   0    |    Y     |  N   |       | 是否已下发处理决定书  |
|  19   | rectification |   varchar   | 100 |   0    |    Y     |  N   |       | 是否已整改  |
|  20   | description |   varchar   | 1000 |   0    |    Y     |  N   |       | 备注  |
|  21   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  22   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  23   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  24   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  25   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  26   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_risk_result">tax_risk_result</a>

**说明：** 风险指标结果表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_risk_index_id |   bigint   | 20 |   0    |    Y     |  N   |       | 指标ID  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 组织id  |
|  4   | data_year |   varchar   | 100 |   0    |    Y     |  N   |       | 年度  |
|  5   | period |   varchar   | 100 |   0    |    Y     |  N   |       | 评估期间  |
|  6   | calculation_result |   decimal   | 21 |   2    |    Y     |  N   |       | 指标计算结果  |
|  7   | warning_state |   varchar   | 100 |   0    |    Y     |  N   |       | 预警状态  |
|  8   | description |   varchar   | 500 |   0    |    Y     |  N   |       | 预警原因说明  |
|  9   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  10   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  11   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  12   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  13   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  14   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_risk_scope">tax_risk_scope</a>

**说明：** 风险预警指标适用范围表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_risk_index_id |   bigint   | 20 |   0    |    N     |  N   |       | 风险预警指标ID  |
|  3   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税人识别号ID  |
|  4   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_small_taxes_info">tax_small_taxes_info</a>

**说明：** 税号对应小税种信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | tax_category |   bigint   | 20 |   0    |    N     |  N   |       | 税种  |
|  4   | provision_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否计提  |
|  5   | provision_period |   varchar   | 100 |   0    |    Y     |  N   |       | 计提周期  |
|  6   | declare_period |   varchar   | 100 |   0    |    Y     |  N   |       | 申报周期  |
|  7   | tax_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 税率  |
|  8   | deduction_rate |   decimal   | 23 |   4    |    Y     |  N   |       | 扣除比例  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  10   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  12   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  13   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  14   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  15   | tax_type |   varchar   | 100 |   0    |    Y     |  N   |       | 类型  |

**表名：** <a id="tax_spt_con_interface_temp">tax_spt_con_interface_temp</a>

**说明：** 印花税合同导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_rate |   varchar   | 100 |   0    |    Y     |  N   |       | 税目代码  |
|  3   | contract_company_code |   varchar   | 300 |   0    |    Y     |  N   |       | 合同签约公司code  |
|  4   | contract_category |   varchar   | 300 |   0    |    Y     |  N   |       | 合同类型  |
|  5   | framework |   varchar   | 100 |   0    |    Y     |  N   |       | 框架支出类  |
|  6   | contract_number |   varchar   | 100 |   0    |    Y     |  N   |       | 合同编号  |
|  7   | contract_name |   varchar   | 300 |   0    |    Y     |  N   |       | 合同名称  |
|  8   | partner_name |   varchar   | 100 |   0    |    Y     |  N   |       | 对方名称  |
|  9   | contract_date |   varchar   | 300 |   0    |    Y     |  N   |       | 订立日期  |
|  10   | contract_start_date |   varchar   | 300 |   0    |    Y     |  N   |       | 合同开始日期  |
|  11   | contract_end_date |   varchar   | 300 |   0    |    Y     |  N   |       | 合同截至日期  |
|  12   | amount |   varchar   | 100 |   0    |    Y     |  N   |       | 合同金额  |
|  13   | split_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 合同拆分金额  |
|  14   | order_number |   varchar   | 100 |   0    |    Y     |  N   |       | 订单编号  |
|  15   | tax_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 计税金额  |
|  16   | tax_ratio |   varchar   | 100 |   0    |    Y     |  N   |       | 计税税率  |
|  17   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  18   | batch_number |   varchar   | 36 |   0    |    Y     |  N   |       | 批次号  |
|  19   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  20   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  21   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  22   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  23   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  24   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  25   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  26   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_spt_contract_interface">tax_spt_contract_interface</a>

**说明：** 印花税合同接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_rate |   varchar   | 100 |   0    |    Y     |  N   |       | 税目代码  |
|  3   | contract_company |   varchar   | 300 |   0    |    Y     |  N   |       | 合同签约公司  |
|  4   | contract_category |   varchar   | 300 |   0    |    Y     |  N   |       | 合同类型  |
|  5   | framework |   varchar   | 100 |   0    |    Y     |  N   |       | 框架支出类  |
|  6   | contract_number |   varchar   | 100 |   0    |    Y     |  N   |       | 合同编号  |
|  7   | contract_name |   varchar   | 300 |   0    |    Y     |  N   |       | 合同名称  |
|  8   | partner_name |   varchar   | 100 |   0    |    Y     |  N   |       | 对方名称  |
|  9   | contract_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 订立日期  |
|  10   | amount |   decimal   | 21 |   2    |    Y     |  N   |       | 合同金额  |
|  11   | order_number |   varchar   | 100 |   0    |    Y     |  N   |       | 订单编号  |
|  12   | tax_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 计税金额  |
|  13   | tax_ratio |   decimal   | 24 |   5    |    Y     |  N   |       | 计税税率  |
|  14   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  15   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  16   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  17   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  18   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  19   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  20   | contract_end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 合同截止日期  |
|  21   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  22   | split_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 拆分金额  |
|  23   | contract_start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 合同开始日期  |
|  24   | creation_type |   varchar   | 100 |   0    |    Y     |  N   |       | 创建方式  |
|  25   | set_of_books_id |   bigint   | 20 |   0    |    Y     |  N   |       | 账套id  |
|  26   | one_off |   varchar   | 100 |   0    |    Y     |  N   |       | 是否一次性缴纳  |

**表名：** <a id="tax_spt_contract_interface_log">tax_spt_contract_interface_log</a>

**说明：** 印花税合同接口记录表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_rate |   varchar   | 100 |   0    |    Y     |  N   |       | 税目代码  |
|  3   | contract_company |   varchar   | 300 |   0    |    Y     |  N   |       | 合同签约公司  |
|  4   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  5   | contract_category |   varchar   | 300 |   0    |    Y     |  N   |       | 合同类型  |
|  6   | framework |   varchar   | 100 |   0    |    Y     |  N   |       | 框架支出类  |
|  7   | contract_number |   varchar   | 100 |   0    |    Y     |  N   |       | 合同编号  |
|  8   | contract_name |   varchar   | 300 |   0    |    Y     |  N   |       | 合同名称  |
|  9   | partner_name |   varchar   | 100 |   0    |    Y     |  N   |       | 对方名称  |
|  10   | contract_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 订立日期  |
|  11   | amount |   decimal   | 21 |   2    |    Y     |  N   |       | 合同金额  |
|  12   | order_number |   varchar   | 100 |   0    |    Y     |  N   |       | 订单编号  |
|  13   | tax_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 计税金额  |
|  14   | tax_ratio |   decimal   | 24 |   5    |    Y     |  N   |       | 计税税率  |
|  15   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  16   | contract_start_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 合同开始日期  |
|  17   | contract_end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 合同截止日期  |
|  18   | set_of_books_id |   bigint   | 20 |   0    |    Y     |  N   |       | 账套id  |
|  19   | order_id |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  20   | change_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 变更日期  |
|  21   | paid_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 支付日期  |
|  22   | creation_type |   varchar   | 100 |   0    |    Y     |  N   |       | 创建方式  |
|  23   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  24   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  25   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  26   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  27   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_sys_code">tax_sys_code</a>

**说明：** 系统代码

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | code_oid |   varchar   | 36 |   0    |    N     |  N   |       | 系统代码Oid  |
|  3   | code_name |   varchar   | 100 |   0    |    N     |  N   |       | 系统代码名称  |
|  4   | enabled |   tinyint   | 4 |   0    |    N     |  N   |       | 是否有效  |
|  5   | deleted |   tinyint   | 4 |   0    |    N     |  N   |       | 是否删除  |
|  6   | type_flag |   bigint   | 20 |   0    |    Y     |  N   |       | 1001:用户自定义1002:租户级初始化1003:系统级  |
|  7   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户Id  |
|  8   | code |   varchar   | 100 |   0    |    Y     |  N   |       | 系统代码描述  |
|  9   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |   0    | 创建人  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |   0    | 更新人  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |   0    | 版本  |

**表名：** <a id="tax_sys_code_value">tax_sys_code_value</a>

**说明：** 系统代码值

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | code_id |   bigint   | 20 |   0    |    N     |  N   |       | 系统代码Id  |
|  3   | value_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 名称  |
|  4   | value_code |   varchar   | 100 |   0    |    N     |  N   |       | 值代码  |
|  5   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 是否有效  |
|  6   | sys_code_code |   varchar   | 100 |   0    |    Y     |  N   |       | 值列表的code  |
|  7   | deleted |   tinyint   | 4 |   0    |    N     |  N   |   0    | 是否删除  |
|  8   | remark |   varchar   | 500 |   0    |    Y     |  N   |       | 备注  |
|  9   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  11   | created_by |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  12   | last_updated_by |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  13   | version_number |   int   | 10 |   0    |    Y     |  N   |       |   |

**表名：** <a id="tax_sys_company">tax_sys_company</a>

**说明：** 公司表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  3   | last_updated_by |   bigint   | 20 |   0    |    Y     |  N   |   0    | 最后更新人  |
|  4   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  5   | deleted |   bit   | 1 |   0    |    Y     |  N   |   b'0'    | 删除标志  |
|  6   | company_oid |   varchar   | 36 |   0    |    N     |  N   |       | 公司OID  |
|  7   | company_name |   varchar   | 255 |   0    |    N     |  N   |       | 公司名称  |
|  8   | created_by |   bigint   | 20 |   0    |    Y     |  N   |   0    | 创建人  |
|  9   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | enabled |   bit   | 1 |   0    |    N     |  N   |       | 是否有效  |
|  11   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  12   | company_code |   varchar   | 50 |   0    |    Y     |  N   |       | 公司代码  |
|  13   | address |   varchar   | 255 |   0    |    Y     |  N   |       | 地址  |
|  14   | company_level_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司级别id  |
|  15   | parent_company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 上级公司id  |
|  16   | start_date_active |   timestamp   | 19 |   0    |    Y     |  N   |       | 有效日期从  |
|  17   | end_date_active |   timestamp   | 19 |   0    |    Y     |  N   |       | 有效日期至  |

**表名：** <a id="tax_sys_currency_rate">tax_sys_currency_rate</a>

**说明：** 汇率表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | last_updated_by |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  3   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  4   | currency_rate_oid |   varchar   | 36 |   0    |    N     |  N   |       | 生效汇率Oid  |
|  5   | base_currency_code |   varchar   | 20 |   0    |    N     |  N   |       | 持有币种code  |
|  6   | currency_code |   varchar   | 20 |   0    |    N     |  N   |       | 兑换币种code  |
|  7   | rate |   double   | 23 |   0    |    N     |  N   |       | 持有币种A对兑换币种B的汇率  |
|  8   | apply_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 生效日期  |
|  9   | rate_source |   varchar   | 50 |   0    |    N     |  N   |       | 汇率来源【欧行ECB、手动更新MANUAL】  |
|  10   | set_of_books_id |   bigint   | 20 |   0    |    N     |  N   |       | 账套ID  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |   1    |   |
|  13   | created_by |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  14   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |

**表名：** <a id="tax_sys_lov">tax_sys_lov</a>

**说明：** lov定义

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | lov_code |   varchar   | 50 |   0    |    Y     |  N   |       | 代码  |
|  3   | lov_name |   varchar   | 200 |   0    |    Y     |  N   |       | 名称  |
|  4   | data_type |   varchar   | 10 |   0    |    Y     |  N   |       | 数据类型,sql,api  |
|  5   | app_id |   bigint   | 20 |   0    |    Y     |  N   |       | 应用服务ID  |
|  6   | api_id |   bigint   | 20 |   0    |    Y     |  N   |       | 接口ID  |
|  7   | sql_text |   varchar   | 4000 |   0    |    Y     |  N   |       | 自定义sql  |
|  8   | title |   varchar   | 100 |   0    |    Y     |  N   |       | 标题  |
|  9   | prompt |   varchar   | 100 |   0    |    Y     |  N   |       | 提示  |
|  10   | deleted |   bit   | 1 |   0    |    N     |  N   |       | 删除标识  |
|  11   | version_number |   int   | 10 |   0    |    Y     |  N   |       | 版本号  |
|  12   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  13   | created_by |   bigint   | 20 |   0    |    Y     |  N   |       | 创建用户ID  |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  15   | last_updated_by |   bigint   | 20 |   0    |    Y     |  N   |       | 最后更新用户ID  |
|  16   | request_column |   varchar   | 4000 |   0    |    Y     |  N   |       | 查询字段  |
|  17   | response_column |   varchar   | 4000 |   0    |    Y     |  N   |       | 展示字段  |
|  18   | remarks |   varchar   | 1024 |   0    |    Y     |  N   |       | 描述  |

**表名：** <a id="tax_sys_res_center">tax_sys_res_center</a>

**说明：** 责任中心表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  3   | set_of_books_id |   bigint   | 20 |   0    |    N     |  N   |       | 账套id  |
|  4   | responsibility_center_code |   varchar   | 60 |   0    |    N     |  N   |       | 责任中心代码  |
|  5   | responsibility_center_name |   varchar   | 100 |   0    |    N     |  N   |       | 责任中心名称  |
|  6   | responsibility_center_type |   varchar   | 30 |   0    |    Y     |  N   |       | 责任中心类型  |
|  7   | enabled |   bit   | 1 |   0    |    Y     |  N   |   b'1'    | 是否启用1:启用0：未启用  |
|  8   | deleted |   bit   | 1 |   0    |    Y     |  N   |   b'0'    | 是否删除1：删除0：未删除  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |   1    |   |
|  10   | created_by |   bigint   | 20 |   0    |    Y     |  N   |       | 创建人  |
|  11   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  12   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  13   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_taxpayer_invoicing">tax_taxpayer_invoicing</a>

**说明：** 关联开票人表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   varchar   | 100 |   0    |    Y     |  N   |       | 纳税人ID  |
|  3   | issue_employee_id |   varchar   | 100 |   0    |    Y     |  N   |       | 开票人ID  |
|  4   | issue_employee_name |   varchar   | 100 |   0    |    Y     |  N   |       | 开票人名称  |
|  5   | issue_ip |   varchar   | 100 |   0    |    Y     |  N   |       | 开票客户端Ip  |
|  6   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  7   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  8   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |

**表名：** <a id="tax_taxpayer_org">tax_taxpayer_org</a>

**说明：** 税号对应机构分配表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | company_id |   bigint   | 20 |   0    |    N     |  N   |       | 公司ID  |
|  4   | responsibility_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心id  |
|  5   | default_flag |   tinyint   | 4 |   0    |    N     |  N   |   0    | 默认标志  |
|  6   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  7   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  8   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  9   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  10   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  11   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 机构代码  |
|  12   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_time_period">tax_time_period</a>

**说明：** 税务期间表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | tax_year |   varchar   | 100 |   0    |    Y     |  N   |       | 年  |
|  2   | tax_month |   varchar   | 100 |   0    |    Y     |  N   |       | 月  |
|  3   | tax_year_month |   varchar   | 100 |   0    |    Y     |  N   |       | 年-月  |

**表名：** <a id="tax_value_added_tax_info">tax_value_added_tax_info</a>

**说明：** 税号对应增值税信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | tax_category |   varchar   | 100 |   0    |    N     |  N   |   VAT    | 税种  |
|  4   | declare_mode |   varchar   | 100 |   0    |    Y     |  N   |       | 申报模式  |
|  5   | declare_level |   varchar   | 100 |   0    |    Y     |  N   |       | 申报层级  |
|  6   | parent_taxpayer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 上级纳税主体ID  |
|  7   | declare_period |   varchar   | 100 |   0    |    Y     |  N   |       | 申报周期  |
|  8   | pre_declare_period |   varchar   | 100 |   0    |    Y     |  N   |       | 预缴申报周期  |
|  9   | pre_rate |   decimal   | 23 |   4    |    Y     |  N   |       | 预征率  |
|  10   | pre_distribution_ratio |   decimal   | 23 |   4    |    Y     |  N   |       | 预缴分配比例  |
|  11   | rem_declare_period |   varchar   | 100 |   0    |    Y     |  N   |       | 汇缴申报周期  |
|  12   | rem_distribution_ratio |   decimal   | 23 |   4    |    Y     |  N   |       | 汇缴分配比例  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  14   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  15   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  17   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  18   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_account_entry">tax_vat_account_entry</a>

**说明：** 临时分录表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | manual_header_id |   bigint   | 20 |   0    |    Y     |  N   |       | 手工价税分离头ID  |
|  3   | manual_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 手工价税分离行ID  |
|  4   | source_system |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统  |
|  5   | org_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构ID  |
|  6   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构CODE  |
|  7   | cost_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心ID  |
|  8   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心CODE  |
|  9   | tran_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  10   | tran_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水行号  |
|  11   | tran_date |   timestamp   | 19 |   0    |    N     |  N   |       | 交易日期  |
|  12   | tran_period |   varchar   | 100 |   0    |    Y     |  N   |       | 交易期间  |
|  13   | period_year |   varchar   | 100 |   0    |    Y     |  N   |       | 年份  |
|  14   | period_quarter |   varchar   | 100 |   0    |    Y     |  N   |       | 季度  |
|  15   | tran_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 交易说明  |
|  16   | currency_code |   varchar   | 100 |   0    |    N     |  N   |       | 币种  |
|  17   | exchange_rate_type |   varchar   | 100 |   0    |    Y     |  N   |       | 汇率类型  |
|  18   | exchange_rate_quotation |   varchar   | 100 |   0    |    Y     |  N   |       | 标价方法  |
|  19   | exchange_rate |   decimal   | 21 |   2    |    Y     |  N   |       | 汇率  |
|  20   | account_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 账务日期  |
|  21   | account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 科目ID  |
|  22   | account_code |   varchar   | 100 |   0    |    Y     |  N   |       | 科目CODE  |
|  23   | entered_amount_dr |   decimal   | 21 |   2    |    Y     |  N   |       | 借方原币金额  |
|  24   | entered_amount_cr |   decimal   | 21 |   2    |    Y     |  N   |       | 贷方原币金额  |
|  25   | functional_amount_dr |   decimal   | 21 |   2    |    Y     |  N   |       | 借方本币金额  |
|  26   | functional_amount_cr |   decimal   | 21 |   2    |    Y     |  N   |       | 贷方本币金额  |
|  27   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  28   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  29   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  30   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  31   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  32   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  33   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  34   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  35   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  36   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  37   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  38   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  39   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  40   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  41   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  42   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 处理批号  |
|  43   | tax_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税目ID  |
|  44   | accounting_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  45   | declare_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否申报  |
|  46   | invoice_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否开票  |
|  47   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  48   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  49   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  50   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  51   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  52   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  53   | amount_type |   varchar   | 100 |   0    |    Y     |  N   |       | 金额类型  |

**表名：** <a id="tax_vat_cancel_apply_header">tax_vat_cancel_apply_header</a>

**说明：** 发票作废申请头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 200 |   0    |    N     |  N   |       | 申请编号  |
|  3   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务状态  |
|  4   | apply_person_id |   varchar   | 100 |   0    |    N     |  N   |       | 申请人ID  |
|  5   | form_oid |   varchar   | 100 |   0    |    Y     |  N   |       | 表单oid  |
|  6   | document_oid |   varchar   | 100 |   0    |    N     |  N   |       | 单据oid  |
|  7   | applicant_oid |   varchar   | 100 |   0    |    N     |  N   |       | 申请人oid  |
|  8   | company_id |   varchar   | 100 |   0    |    N     |  N   |       | 公司id  |
|  9   | apply_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型  |
|  10   | cancel_reason |   varchar   | 100 |   0    |    N     |  N   |       | 作废原因  |
|  11   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  12   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建人id  |
|  13   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  14   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新人id  |
|  15   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  16   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  17   | instructions |   varchar   | 2000 |   0    |    Y     |  N   |       | 说明  |

**表名：** <a id="tax_vat_cancel_apply_line">tax_vat_cancel_apply_line</a>

**说明：** 发票作废申请行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票作废申请头ID  |
|  3   | invoice_header_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  4   | cancel_reason |   varchar   | 100 |   0    |    N     |  N   |       | 作废原因  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  6   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建人id  |
|  7   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  8   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新人id  |
|  9   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |       | 最后更新日期  |
|  10   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户id  |
|  11   | invoice_apply_seq |   varchar   | 30 |   0    |    Y     |  N   |       | 申请序列号  |

**表名：** <a id="tax_vat_deemed_sales_detail">tax_vat_deemed_sales_detail</a>

**说明：** 视同销售数据明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_system |   varchar   | 300 |   0    |    N     |  N   |       | 来源系统  |
|  3   | data_type |   varchar   | 100 |   0    |    Y     |  N   |       | 数据类型（是否价税分离）  |
|  4   | tran_code |   varchar   | 100 |   0    |    N     |  N   |       | 交易代码  |
|  5   | tran_type |   varchar   | 100 |   0    |    N     |  N   |       | 交易类型  |
|  6   | input_invoice_no |   varchar   | 100 |   0    |    Y     |  N   |       | 进项发票号码  |
|  7   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户ID  |
|  8   | tran_date |   timestamp   | 19 |   0    |    N     |  N   |       | 交易日期  |
|  9   | org_id |   bigint   | 20 |   0    |    N     |  N   |       | 机构ID  |
|  10   | cost_center_id |   bigint   | 20 |   0    |    N     |  N   |       | 责任中心ID  |
|  11   | currency_code |   varchar   | 100 |   0    |    N     |  N   |       | 交易币种  |
|  12   | tran_amount |   decimal   | 21 |   2    |    N     |  N   |       | 视同销售金额（价税合计）  |
|  13   | tax_rate_id |   bigint   | 20 |   0    |    N     |  N   |       | 增值税税目ID  |
|  14   | sales |   decimal   | 21 |   2    |    N     |  N   |       | 视同销售应税销售额（不含税）  |
|  15   | cost |   decimal   | 21 |   2    |    Y     |  N   |       | 视同销售成本  |
|  16   | out_taxes |   decimal   | 21 |   2    |    N     |  N   |       | 视同销售销项税额  |
|  17   | memo |   varchar   | 2000 |   0    |    Y     |  N   |       | 说明  |
|  18   | goods_id |   bigint   | 20 |   0    |    Y     |  N   |       | 商品编码ID  |
|  19   | invoice_type |   varchar   | 100 |   0    |    Y     |  N   |       | 发票类型  |
|  20   | accounting_code |   varchar   | 100 |   0    |    Y     |  N   |       | 会计科目  |
|  21   | accounting_name |   varchar   | 100 |   0    |    Y     |  N   |       | 会计科目名称  |
|  22   | expense_report_number |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单编号  |
|  23   | vat_sale_type |   varchar   | 100 |   0    |    Y     |  N   |       |   |
|  24   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  25   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  26   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  27   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  28   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  29   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户ID  |

**表名：** <a id="tax_vat_input_header">tax_vat_input_header</a>

**说明：** 进项发票头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_type_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票类型ID  |
|  3   | invoice_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 发票日期  |
|  4   | invoice_code |   varchar   | 100 |   0    |    Y     |  N   |       | 发票代码  |
|  5   | invoice_number |   varchar   | 100 |   0    |    Y     |  N   |       | 发票号码  |
|  6   | company_id |   varchar   | 100 |   0    |    Y     |  N   |   缺省    | 公司ID  |
|  7   | total_amount |   decimal   | 23 |   4    |    N     |  N   |       | 发票价税合计  |
|  8   | invoice_amount |   decimal   | 23 |   4    |    N     |  N   |       | 发票不含税金额  |
|  9   | tax_total_amount |   decimal   | 23 |   4    |    N     |  N   |       | 发票总税额  |
|  10   | currency_code |   varchar   | 100 |   0    |    N     |  N   |   CNY    | 币种  |
|  11   | remark |   varchar   | 1000 |   0    |    Y     |  N   |       | 发票备注  |
|  12   | buyer_id |   bigint   | 20 |   0    |    N     |  N   |       | 购方纳税主体ID  |
|  13   | buyer_name |   varchar   | 300 |   0    |    N     |  N   |       | 购方纳税主体名称  |
|  14   | buyer_tax_no |   varchar   | 300 |   0    |    N     |  N   |       | 购方纳税人识别号  |
|  15   | buyer_add_ph |   varchar   | 300 |   0    |    Y     |  N   |       | 购方纳税人地址电话  |
|  16   | buyer_account |   varchar   | 300 |   0    |    Y     |  N   |       | 购方纳税人开户行账号  |
|  17   | saler_name |   varchar   | 300 |   0    |    Y     |  N   |       | 销方名称  |
|  18   | saler_tax_no |   varchar   | 300 |   0    |    Y     |  N   |       | 销方纳税人识别号  |
|  19   | saler_add_ph |   varchar   | 300 |   0    |    Y     |  N   |       | 销方纳税人地址电话  |
|  20   | saler_account |   varchar   | 300 |   0    |    Y     |  N   |       | 销方纳税人开户行账号  |
|  21   | invoice_status |   varchar   | 300 |   0    |    N     |  N   |       | 发票状态包括：0-正常；1-失控；2-作废；3-红冲；4-异常  |
|  22   | certificate_status |   varchar   | 300 |   0    |    N     |  N   |       | 是否认证包括：0-未认证；1-已认证；2-不认证  |
|  23   | certificate_result |   varchar   | 300 |   0    |    N     |  N   |       | 认证处理状态包括：0-未认证；1-待认证；2-系统认证中；3-第三方认证中；4-认证成功；5-认证失败  |
|  24   | certificate_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 认证时间  |
|  25   | certificate_period |   timestamp   | 19 |   0    |    Y     |  N   |       | 认证期间  |
|  26   | deduction_note_flag |   varchar   | 300 |   0    |    N     |  N   |       | 抵扣标识包括未抵扣、已抵扣  |
|  27   | deduction_period |   timestamp   | 19 |   0    |    N     |  N   |       | 抵扣期间  |
|  28   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  29   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  30   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  31   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  32   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  33   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_input_line">tax_vat_input_line</a>

**说明：** 进项发票行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | input_header_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  3   | line_num |   varchar   | 100 |   0    |    N     |  N   |       | 序号  |
|  4   | goods_name |   varchar   | 100 |   0    |    Y     |  N   |       | 商品名称  |
|  5   | goods_standard |   varchar   | 100 |   0    |    Y     |  N   |       | 规格型号  |
|  6   | goods_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |
|  7   | goods_number |   bigint   | 20 |   0    |    Y     |  N   |       | 数量  |
|  8   | goods_price |   varchar   | 100 |   0    |    Y     |  N   |       | 单价  |
|  9   | vat_rate |   decimal   | 23 |   4    |    N     |  N   |       | 税率%  |
|  10   | line_total_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 行合计金额  |
|  11   | sales |   decimal   | 23 |   4    |    N     |  N   |       | 不含税金额  |
|  12   | taxes |   decimal   | 23 |   4    |    N     |  N   |       | 税额  |
|  13   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  14   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  15   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  16   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  17   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  18   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_invoice">tax_vat_invoice</a>

**说明：** 发票头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_apply_seq |   varchar   | 100 |   0    |    N     |  N   |       | 发票申请序列号（申请编号+两位流水号）  |
|  3   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  4   | invoice_amount_type |   varchar   | 100 |   0    |    N     |  N   |       | 红票/蓝票；0：蓝字发票；1：红字发票  |
|  5   | create_type |   varchar   | 100 |   0    |    N     |  N   |       | 创建方式；MANUAL：手工创建；TRAN：交易创建  |
|  6   | apply_header_id |   bigint   | 20 |   0    |    Y     |  N   |       | 交易流水开票申请ID  |
|  7   | manual_invoice_id |   bigint   | 20 |   0    |    Y     |  N   |       | 手工开票申请ID  |
|  8   | invoice_code |   varchar   | 100 |   0    |    Y     |  N   |       | 发票代码  |
|  9   | invoice_number |   varchar   | 100 |   0    |    Y     |  N   |       | 发票号码  |
|  10   | output_tax_disk_firm |   varchar   | 100 |   0    |    N     |  N   |       | 盘商开票接口CODE  |
|  11   | invoice_site_id |   bigint   | 20 |   0    |    Y     |  N   |       | 开票点ID  |
|  12   | cal_rule_code |   varchar   | 100 |   0    |    N     |  N   |       | 计税规则代码  |
|  13   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户ID  |
|  14   | client_name |   varchar   | 200 |   0    |    N     |  N   |       | 客户名称  |
|  15   | client_tax_num |   varchar   | 200 |   0    |    N     |  N   |       | 客户纳税人识别号  |
|  16   | client_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 客户开户行及账号  |
|  17   | client_add_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 客户地址/电话  |
|  18   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  19   | taxpayer_name |   varchar   | 200 |   0    |    N     |  N   |       | 销方名称  |
|  20   | taxpayer_num |   varchar   | 200 |   0    |    N     |  N   |       | 销方纳税人识别号  |
|  21   | taxpayer_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 销方开户行及账号  |
|  22   | taxpayer_add_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 销方地址、电话  |
|  23   | total_amount |   decimal   | 23 |   2    |    N     |  N   |       | 发票总价税合计金额  |
|  24   | sales |   decimal   | 23 |   2    |    N     |  N   |       | 发票总不含税金额  |
|  25   | taxes |   decimal   | 23 |   2    |    N     |  N   |       | 发票总税额  |
|  26   | invoice_memo |   varchar   | 2000 |   0    |    Y     |  N   |       | 备注  |
|  27   | bill_flag |   tinyint   | 4 |   0    |    N     |  N   |   1    | 清单标识，0不开具1开具  |
|  28   | invoice_status |   varchar   | 100 |   0    |    N     |  N   |       | 发票状态，未开具、开具中，已开具，开具失败，已作废  |
|  29   | receipt_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 收款人  |
|  30   | check_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 复核人  |
|  31   | issue_employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 开票员ID  |
|  32   | invoice_flag |   varchar   | 100 |   0    |    N     |  N   |       | 开票标识，P是开票中，Y是开票成功，N是开票失败  |
|  33   | issue_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 开票日期  |
|  34   | issue_period |   varchar   | 100 |   0    |    Y     |  N   |       | 开票期间  |
|  35   | issue_year |   varchar   | 100 |   0    |    Y     |  N   |       | 开票年份  |
|  36   | issue_quarter |   bigint   | 20 |   0    |    Y     |  N   |       | 开票季度  |
|  37   | return_info_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 合计不含税金额(接口返回)  |
|  38   | return_info_tax_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 合计税额(接口返回)  |
|  39   | write_off_status |   varchar   | 100 |   0    |    N     |  N   |       | 核销状态；N未核销，Y部分核销，C全部核销  |
|  40   | invoice_print_flag |   varchar   | 100 |   0    |    N     |  N   |       | 发票打印标识；N未打印，P打印中，Y已打印，E打印失败  |
|  41   | print_employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 发票打印人ID  |
|  42   | invoice_print_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 发票打印日期  |
|  43   | bill_print_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 清单打印标识；N未打印，P打印中，Y已打印，E打印失败  |
|  44   | bill_print_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 清单打印日期  |
|  45   | cancel_apply_id |   bigint   | 20 |   0    |    Y     |  N   |       | 发票作废申请ID  |
|  46   | cancel_reason |   varchar   | 200 |   0    |    Y     |  N   |       | 发票作废原因  |
|  47   | cancel_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 发票作废日期  |
|  48   | cancel_employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 发票作废员工ID  |
|  49   | REVERSE_APPLY_ID |   varchar   | 30 |   0    |    Y     |  N   |       |   |
|  50   | source_invoice_id |   bigint   | 20 |   0    |    Y     |  N   |       | 红冲来源发票ID  |
|  51   | reverse_info_num |   varchar   | 100 |   0    |    Y     |  N   |       | 红冲信息表编号  |
|  52   | reverse_flag |   varchar   | 100 |   0    |    N     |  N   |       | 红冲标识；N未红冲，C全部被红冲,Y部分被红冲  |
|  53   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  54   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  55   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  56   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  57   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  58   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 币种  |
|  59   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  60   | email_pdf |   varchar   | 500 |   0    |    Y     |  N   |       | 电子发票pdf地址  |
|  61   | cancel_flag |   varchar   | 30 |   0    |    Y     |  N   |   N    | 作废标识  |
|  62   | information_table_status |   varchar   | 20 |   0    |    Y     |  N   |   N    | 是否创建红字信息表  |
|  63   | reverse_invoice_flag |   varchar   | 30 |   0    |    Y     |  N   |   N    | 红冲标识，已开具发票调整用  |
|  64   | push_method |   varchar   | 100 |   0    |    Y     |  N   |       | 推送方式  |
|  65   | push_status |   varchar   | 100 |   0    |    Y     |  N   |       | 推送状态  |
|  66   | push_address |   varchar   | 100 |   0    |    Y     |  N   |       | 推送地址/推送号码  |
|  67   | check_code |   varchar   | 100 |   0    |    Y     |  N   |       | 校验码  |

**表名：** <a id="tax_vat_invoice_head">tax_vat_invoice_head</a>

**说明：** 发票头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_type_code |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型代码  |
|  3   | invoice_type_name |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型名称  |
|  4   | invoice_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 开票日期  |
|  5   | invoice_no |   varchar   | 30 |   0    |    N     |  N   |       | 发票号码  |
|  6   | invoice_code |   varchar   | 30 |   0    |    N     |  N   |       | 发票代码  |
|  7   | total_amount |   decimal   | 21 |   2    |    N     |  N   |       | 发票价税合计  |
|  8   | invoice_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 发票不含税金额  |
|  9   | tax_total_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 税额合计  |
|  10   | currency_code |   varchar   | 30 |   0    |    N     |  N   |   CNY    | 币种  |
|  11   | remark |   varchar   | 1000 |   0    |    Y     |  N   |       | 备注  |
|  12   | buyer_id |   bigint   | 20 |   0    |    Y     |  N   |       | 购方纳税主体ID  |
|  13   | buyer_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 购方名称  |
|  14   | buyer_tax_no |   varchar   | 1000 |   0    |    Y     |  N   |       | 购方纳税人识别号  |
|  15   | buyer_add_ph |   varchar   | 1000 |   0    |    Y     |  N   |       | 购方地址/电话  |
|  16   | buyer_account |   varchar   | 1000 |   0    |    Y     |  N   |       | 购方开户行/账号  |
|  17   | saler_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 销方名称  |
|  18   | saler_tax_no |   varchar   | 1000 |   0    |    Y     |  N   |       | 销方纳税人识别号  |
|  19   | saler_add_ph |   varchar   | 1000 |   0    |    Y     |  N   |       | 销方地址/电话  |
|  20   | saler_account |   varchar   | 1000 |   0    |    Y     |  N   |       | 销方开户行/账号  |
|  21   | cancel_flag |   tinyint   | 4 |   0    |    N     |  N   |       | 作废标志  |
|  22   | red_invoice_flag |   tinyint   | 4 |   0    |    N     |  N   |       | 红票标志  |
|  23   | accounting_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 入账标志（Y/N）  |
|  24   | red_flag |   varchar   | 50 |   0    |    Y     |  N   |       | 红冲标志  |
|  25   | invoice_status |   varchar   | 100 |   0    |    Y     |  N   |       | 发票状态  |
|  26   | certification_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 认证日期  |
|  27   | certification_status |   varchar   | 100 |   0    |    Y     |  N   |       | 是否认证  |
|  28   | certification_reason |   varchar   | 300 |   0    |    Y     |  N   |       | 认证失败原因  |
|  29   | blue_invoice_code |   varchar   | 100 |   0    |    Y     |  N   |       | 蓝票发票代码  |
|  30   | blue_invoice_no |   varchar   | 100 |   0    |    Y     |  N   |       | 蓝票发票号码  |
|  31   | traffic_fee_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 通行费标志  |
|  32   | zero_tax_rate_flag |   varchar   | 2 |   0    |    Y     |  N   |       | 零税率标志（非零税率：空；税率栏位显示“免税”：1；税率栏位显示“不征税”：2；零税率：3）  |
|  33   | passenger_name |   varchar   | 200 |   0    |    Y     |  N   |       | 乘客姓名  |
|  34   | id_card |   varchar   | 50 |   0    |    Y     |  N   |       | 身份证号  |
|  35   | fare |   decimal   | 21 |   2    |    Y     |  N   |       | 票价  |
|  36   | fuel_surcharge |   decimal   | 21 |   2    |    Y     |  N   |       | 燃油附加费  |
|  37   | property_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 不动产标识（Y/N）  |
|  38   | legalize_belong_date |   varchar   | 100 |   0    |    Y     |  N   |       | 税款所属期  |
|  39   | deduction_note_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 抵扣标识，是否抵扣  |
|  40   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  41   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  42   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  43   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  44   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  45   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_invoice_info">tax_vat_invoice_info</a>

**说明：** 税号发票管理配置信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  3   | output_tax_disk_firm |   varchar   | 300 |   0    |    Y     |  N   |       | 销项盘商  |
|  4   | board_number |   varchar   | 100 |   0    |    Y     |  N   |       | 税控盘编号  |
|  5   | board_word |   varchar   | 100 |   0    |    Y     |  N   |       | 税控盘口令  |
|  6   | sign_passwd |   varchar   | 100 |   0    |    Y     |  N   |       | 税务数据证书密码  |
|  7   | server_number |   varchar   | 100 |   0    |    Y     |  N   |       | 服务器编号  |
|  8   | maximum_lines |   bigint   | 20 |   0    |    Y     |  N   |       | 最大开票行数  |
|  9   | maximum_amount |   bigint   | 20 |   0    |    Y     |  N   |       | 最大开票限额（普票）  |
|  10   | spe_maximum_amount |   bigint   | 20 |   0    |    Y     |  N   |       | 最大开票限额（专票）  |
|  11   | elec_enable_flag |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否启用电子发票  |
|  12   | elec_maximum_amount |   bigint   | 20 |   0    |    Y     |  N   |       | 最大开票限额（电子普票）  |
|  13   | elec_spe_maximum_amount |   bigint   | 20 |   0    |    Y     |  N   |       | 最大开票限额（电子专票）  |
|  14   | input_tax_disk_firm |   varchar   | 100 |   0    |    Y     |  N   |       | 进项盘商  |
|  15   | input_enabled |   tinyint   | 4 |   0    |    Y     |  N   |   0    | 是否启用进项接口  |
|  16   | access_key_user_name |   varchar   | 100 |   0    |    Y     |  N   |       | 进项接口用户名  |
|  17   | access_key_password |   varchar   | 100 |   0    |    Y     |  N   |       | 进项接口密码  |
|  18   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  19   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  20   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  21   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  22   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  23   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  24   | elec_authentication_id |   varchar   | 100 |   0    |    Y     |  N   |       | 电票身份认证ID  |

**表名：** <a id="tax_vat_invoice_item">tax_vat_invoice_item</a>

**说明：** 发票行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | line_num |   bigint   | 20 |   0    |    N     |  N   |       | 序号  |
|  3   | invoice_line_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票行性质0普通明细行，3被折扣行，4折扣行  |
|  4   | goods_id |   bigint   | 20 |   0    |    N     |  N   |       | 商品编码ID  |
|  5   | goods_code |   varchar   | 100 |   0    |    N     |  N   |       | 商品编码  |
|  6   | goods_version_number |   varchar   | 100 |   0    |    N     |  N   |       | 商品编码版本号  |
|  7   | goods_name |   varchar   | 100 |   0    |    N     |  N   |       | 商品名称  |
|  8   | goods_standard |   varchar   | 100 |   0    |    Y     |  N   |       | 规格型号  |
|  9   | goods_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |
|  10   | goods_number |   bigint   | 20 |   0    |    Y     |  N   |       | 数量  |
|  11   | goods_price |   decimal   | 23 |   2    |    Y     |  N   |       | 单价  |
|  12   | tax_rate_id |   bigint   | 20 |   0    |    N     |  N   |       | 税目ID  |
|  13   | vat_rate |   decimal   | 23 |   2    |    N     |  N   |       | 税率%  |
|  14   | perferential_tax_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 优惠税率  |
|  15   | total_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 价税合计金额  |
|  16   | sales |   decimal   | 23 |   2    |    Y     |  N   |       | 不含税金额  |
|  17   | taxes |   decimal   | 23 |   2    |    Y     |  N   |       | 税额  |
|  18   | zero_rate_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 零税率标识；空非零税率、0：出口退税；1：免税；2：不征税；3：普通零税率  |
|  19   | deduct_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 是否差额征税Y/N  |
|  20   | deduct_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 扣除额  |
|  21   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  22   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  23   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  24   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  25   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  26   | invoice_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  27   | preferential_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 优惠政策标识是否享受  |
|  28   | preferential_policy |   varchar   | 100 |   0    |    Y     |  N   |       | 优惠政策内容  |
|  29   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_invoice_line">tax_vat_invoice_line</a>

**说明：** 发票行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  3   | invoice_line_num |   int   | 10 |   0    |    N     |  N   |       | 发票行序号  |
|  4   | goods_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 货物或应税劳务、服务名称  |
|  5   | specification_model |   varchar   | 1000 |   0    |    Y     |  N   |       | 规格型号  |
|  6   | unit |   varchar   | 30 |   0    |    Y     |  N   |       | 单位  |
|  7   | num |   bigint   | 20 |   0    |    Y     |  N   |       | 数量  |
|  8   | unit_price |   decimal   | 28 |   9    |    Y     |  N   |       | 单价  |
|  9   | detail_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 金额  |
|  10   | tax_rate |   varchar   | 30 |   0    |    Y     |  N   |       | 税率  |
|  11   | tax_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 税额  |
|  12   | currency_code |   varchar   | 30 |   0    |    N     |  N   |       | 币种  |
|  13   | exchange_rate |   decimal   | 21 |   2    |    N     |  N   |       | 汇率  |
|  14   | detail_no |   varchar   | 200 |   0    |    Y     |  N   |       | 明细编号  |
|  15   | tax_unit_price |   decimal   | 21 |   2    |    Y     |  N   |       | 含税单价  |
|  16   | tax_detail_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 含税金额  |
|  17   | expense_item |   varchar   | 200 |   0    |    Y     |  N   |       | 费用项目  |
|  18   | plate_no |   varchar   | 200 |   0    |    Y     |  N   |       | 车牌号  |
|  19   | data_type |   varchar   | 50 |   0    |    Y     |  N   |       | 类型  |
|  20   | traffic_date_start |   timestamp   | 19 |   0    |    Y     |  N   |       | 通行日期起  |
|  21   | traffic_date_end |   timestamp   | 19 |   0    |    Y     |  N   |       | 通行日起止  |
|  22   | red_flag |   varchar   | 2 |   0    |    Y     |  N   |       | 红冲标志  |
|  23   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  24   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  25   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  26   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  27   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  28   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_invoice_line_dist">tax_vat_invoice_line_dist</a>

**说明：** 发票分配行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_line_id |   bigint   | 20 |   0    |    N     |  N   |       | 关联发票行ID  |
|  3   | invoice_no |   varchar   | 30 |   0    |    Y     |  N   |       | 发票号码  |
|  4   | invoice_code |   varchar   | 30 |   0    |    Y     |  N   |       | 发票代码  |
|  5   | goods_name |   varchar   | 1000 |   0    |    Y     |  N   |       | 货物或应税劳务、服务名称  |
|  6   | specification_model |   varchar   | 1000 |   0    |    Y     |  N   |       | 规格型号  |
|  7   | unit |   varchar   | 30 |   0    |    Y     |  N   |       | 单位  |
|  8   | num |   bigint   | 20 |   0    |    Y     |  N   |       | 数量  |
|  9   | unit_price |   decimal   | 28 |   9    |    Y     |  N   |       | 单价  |
|  10   | detail_amount |   decimal   | 21 |   2    |    N     |  N   |       | 金额  |
|  11   | tax_rate |   varchar   | 30 |   0    |    N     |  N   |       | 税率  |
|  12   | tax_amount |   decimal   | 21 |   2    |    N     |  N   |       | 税额  |
|  13   | currency_code |   varchar   | 30 |   0    |    N     |  N   |       | 币种  |
|  14   | exchange_rate |   decimal   | 21 |   2    |    N     |  N   |       | 汇率  |
|  15   | accounting_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 入账标志（Y/N）  |
|  16   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  17   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  18   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  19   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  20   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  21   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_invoice_line_expense">tax_vat_invoice_line_expense</a>

**说明：** 发票行报销记录表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_dist_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票分配行ID  |
|  3   | invoice_head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  4   | invoice_no |   varchar   | 30 |   0    |    Y     |  N   |       | 发票号码  |
|  5   | invoice_code |   varchar   | 30 |   0    |    Y     |  N   |       | 发票代码  |
|  6   | detail_amount |   decimal   | 21 |   2    |    N     |  N   |       | 金额  |
|  7   | tax_rate |   varchar   | 30 |   0    |    N     |  N   |       | 税率  |
|  8   | tax_amount |   decimal   | 21 |   2    |    N     |  N   |       | 税额  |
|  9   | exp_expense_head_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联报账单头ID  |
|  10   | requisition_number |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单单号  |
|  11   | company_code |   varchar   | 100 |   0    |    Y     |  N   |       | 公司代码  |
|  12   | department_code |   varchar   | 100 |   0    |    Y     |  N   |       | 部门代码  |
|  13   | document_type |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单类型  |
|  14   | employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人ID  |
|  15   | requisition_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 申请日期  |
|  16   | exp_expense_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联报账单行ID  |
|  17   | expense_type_code |   varchar   | 100 |   0    |    Y     |  N   |       | 费用类型代码  |
|  18   | description |   varchar   | 100 |   0    |    Y     |  N   |       | 报账单行备注  |
|  19   | status |   varchar   | 30 |   0    |    N     |  N   |       | 状态  |
|  20   | invoice_mate_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 发票匹配标志  |
|  21   | reverse_flag |   varchar   | 1 |   0    |    Y     |  N   |       | 反冲标识  |
|  22   | exp_expense_reverse_head_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联反冲单头ID  |
|  23   | exp_expense_reverse_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 关联反冲单行ID  |
|  24   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  25   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  26   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  27   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  28   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  29   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  30   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  31   | department_id |   bigint   | 20 |   0    |    Y     |  N   |       | 部门ID  |
|  32   | expense_type_name |   varchar   | 100 |   0    |    Y     |  N   |       | 费用类型名称  |
|  33   | expense_type_id |   bigint   | 20 |   0    |    Y     |  N   |       | 费用类型ID  |
|  34   | expense_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 费用金额  |

**表名：** <a id="tax_vat_invoice_period">tax_vat_invoice_period</a>

**说明：** 发票期间控制表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | period |   varchar   | 100 |   0    |    N     |  N   |       | 期间  |
|  3   | period_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 期间控制标识（N/Y/E）未处理、执行成功、执行失败  |
|  4   | begin_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 任务执行的开始日期  |
|  5   | end_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 任务执行的结束日期  |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  8   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_invoice_rule">tax_vat_invoice_rule</a>

**说明：** 开票规则定义表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | seperate_rule_id |   bigint   | 20 |   0    |    N     |  N   |       | 价税分离规则ID  |
|  3   | commodity_id |   bigint   | 20 |   0    |    Y     |  N   |       | 商品编码ID  |
|  4   | invoice_title |   varchar   | 100 |   0    |    Y     |  N   |       | 开票名称  |
|  5   | invoice_type |   varchar   | 100 |   0    |    Y     |  N   |       | 发票类型  |
|  6   | unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |
|  7   | enable_flag |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  10   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  13   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_invoicing_dimension">tax_vat_invoicing_dimension</a>

**说明：** 开票权限信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoicing_site_id |   bigint   | 20 |   0    |    N     |  N   |       | 开票点ID  |
|  3   | company_id |   bigint   | 20 |   0    |    N     |  N   |       | 机构ID  |
|  4   | department_id |   bigint   | 20 |   0    |    Y     |  N   |       | 成本中心ID  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  10   | organization_code |   varchar   | 100 |   0    |    Y     |  N   |       | 机构代码  |
|  11   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_invoicing_site">tax_vat_invoicing_site</a>

**说明：** 开票点信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoicing_site_code |   varchar   | 100 |   0    |    N     |  N   |       | 开票点编码  |
|  3   | invoicing_site_name |   varchar   | 300 |   0    |    N     |  N   |       | 开票点名称  |
|  4   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  5   | invoicing_site_add |   varchar   | 400 |   0    |    Y     |  N   |       | 开票点地址  |
|  6   | passwod |   varchar   | 100 |   0    |    Y     |  N   |       | 税控钥匙密码  |
|  7   | invoicing_terminal |   varchar   | 100 |   0    |    Y     |  N   |       | 开票终端标识  |
|  8   | security_code |   varchar   | 100 |   0    |    Y     |  N   |       | 安全码  |
|  9   | print_top |   bigint   | 20 |   0    |    Y     |  N   |       | 上边距  |
|  10   | print_left |   bigint   | 20 |   0    |    Y     |  N   |       | 左边距  |
|  11   | remarks |   varchar   | 400 |   0    |    Y     |  N   |       | 备注  |
|  12   | enabled |   tinyint   | 4 |   0    |    N     |  N   |   1    | 启用标志  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  14   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  15   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  17   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  18   | taxpayer_name |   varchar   | 300 |   0    |    Y     |  N   |       | 所属纳税主体名称  |
|  19   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_manual_header">tax_vat_manual_header</a>

**说明：** 手工开票申请头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 300 |   0    |    Y     |  N   |       | 手工开票申请编号  |
|  3   | apply_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型（手工开票申请）  |
|  4   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务审批状态  |
|  5   | applicant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人ID  |
|  6   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  7   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司id  |
|  8   | department_id |   bigint   | 20 |   0    |    N     |  N   |       | 责任中心ID  |
|  9   | invoice_site_id |   bigint   | 20 |   0    |    Y     |  N   |       | 开票点ID  |
|  10   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  11   | cal_rule_code |   varchar   | 100 |   0    |    Y     |  N   |       | 计税规则代码  |
|  12   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户ID  |
|  13   | client_name |   varchar   | 200 |   0    |    Y     |  N   |       |   |
|  14   | client_tax_num |   varchar   | 200 |   0    |    Y     |  N   |       |   |
|  15   | client_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 客户开户行及账号  |
|  16   | client_add_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 客户地址/电话  |
|  17   | invoice_memo |   varchar   | 2000 |   0    |    Y     |  N   |       | 发票备注  |
|  18   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  19   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  20   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  21   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  22   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  23   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据OID  |
|  24   | form_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 表单OID  |
|  25   | applicant_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 申请人OID  |
|  26   | total_price_and_tax |   decimal   | 23 |   4    |    Y     |  N   |       | 总价税合计金额  |
|  27   | total_sales |   decimal   | 23 |   4    |    Y     |  N   |       | 总不含税金额  |
|  28   | total_taxes |   decimal   | 23 |   4    |    Y     |  N   |       | 总税额  |
|  29   | push_method |   varchar   | 100 |   0    |    Y     |  N   |       | 推送方式  |
|  30   | push_status |   varchar   | 100 |   0    |    Y     |  N   |       | 推送状态  |
|  31   | push_address |   varchar   | 100 |   0    |    Y     |  N   |       | 推送地址/推送号码  |
|  32   | tax_invoice_applicant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人开票申请信息表主键ID  |
|  33   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_manual_line">tax_vat_manual_line</a>

**说明：** 手工开票申请行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 手工开票申请头ID  |
|  3   | line_num |   varchar   | 100 |   0    |    N     |  N   |       | 序号  |
|  4   | invoice_line_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票行性质0普通明细行，3被折扣行，4折扣行  |
|  5   | goods_id |   bigint   | 20 |   0    |    N     |  N   |       | 商品编码ID  |
|  6   | goods_code |   varchar   | 100 |   0    |    N     |  N   |       | 商品编码  |
|  7   | goods_name |   varchar   | 100 |   0    |    N     |  N   |       | 商品名称  |
|  8   | goods_standard |   varchar   | 100 |   0    |    Y     |  N   |       | 规格型号  |
|  9   | goods_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |
|  10   | goods_number |   bigint   | 20 |   0    |    Y     |  N   |       | 数量  |
|  11   | goods_price |   decimal   | 23 |   4    |    Y     |  N   |       | 单价  |
|  12   | tax_rate_id |   bigint   | 20 |   0    |    N     |  N   |       | 税目ID  |
|  13   | vat_rate |   decimal   | 23 |   4    |    N     |  N   |       | 税率%  |
|  14   | preferential_tax_rate |   decimal   | 23 |   4    |    Y     |  N   |       | 优惠税率%  |
|  15   | total_amount |   decimal   | 23 |   4    |    Y     |  N   |       | 价税合计金额  |
|  16   | sales |   decimal   | 23 |   4    |    Y     |  N   |       | 不含税金额  |
|  17   | taxes |   decimal   | 23 |   4    |    Y     |  N   |       | 税额  |
|  18   | deduct_flag |   varchar   | 100 |   0    |    N     |  N   |   N    | 是否差额征税Y/N  |
|  19   | deduct_amount |   decimal   | 23 |   4    |    Y     |  N   |       | 扣除额  |
|  20   | zero_rate_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 零税率标识；空非零税率、0：出口退税；1：免税；2：不征税；3：普通零税率  |
|  21   | commodity_name |   varchar   | 300 |   0    |    Y     |  N   |       | 货物或应税劳务、服务名称  |
|  22   | separate_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离规则id  |
|  23   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  24   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  25   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  26   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  27   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  28   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_output_detail">tax_vat_output_detail</a>

**说明：** 销项明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | trans_detail_id |   bigint   | 20 |   0    |    Y     |  N   |       | 来源交易明细ID  |
|  3   | source_system |   varchar   | 30 |   0    |    N     |  N   |       | 来源系统  |
|  4   | cal_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离规则  |
|  5   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户ID  |
|  6   | trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  7   | trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水行号  |
|  8   | source_data_status |   varchar   | 50 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  9   | accounting_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  10   | trans_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  11   | trans_period |   varchar   | 20 |   0    |    Y     |  N   |       | 交易期间  |
|  12   | period_year |   varchar   | 20 |   0    |    Y     |  N   |       | 年份  |
|  13   | period_quarter |   varchar   | 20 |   0    |    Y     |  N   |       | 季度  |
|  14   | org_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构ID  |
|  15   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构  |
|  16   | cost_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心ID  |
|  17   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心  |
|  18   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 交易币种  |
|  19   | amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币金额  |
|  20   | functional_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币金额  |
|  21   | sales |   decimal   | 21 |   2    |    Y     |  N   |       | 原币应税销售额  |
|  22   | fun_sales |   decimal   | 21 |   2    |    Y     |  N   |       | 本币应税销售额  |
|  23   | output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 原币销项税额  |
|  24   | fun_output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 本币销项税额  |
|  25   | adjust_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币调整金额  |
|  26   | fun_adjust_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币调整金额  |
|  27   | deduct_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 差额开票标识  |
|  28   | deduct_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 差额开票抵扣额  |
|  29   | separate_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离科目id  |
|  30   | dr_or_cr |   varchar   | 10 |   0    |    Y     |  N   |       | 增值税科目方向  |
|  31   | tax_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 增值税科目id  |
|  32   | tax_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 税率  |
|  33   | source_trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水号  |
|  34   | source_trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水行号  |
|  35   | trans_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 交易说明  |
|  36   | exchange_rate_type |   varchar   | 100 |   0    |    Y     |  N   |       | 汇率类型  |
|  37   | exchange_rate_quotation |   varchar   | 100 |   0    |    Y     |  N   |       | 标价方法  |
|  38   | exchange_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 汇率  |
|  39   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段1  |
|  40   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段2  |
|  41   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段3  |
|  42   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段4  |
|  43   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段5  |
|  44   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段6  |
|  45   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段7  |
|  46   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段8  |
|  47   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段9  |
|  48   | segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段10  |
|  49   | segment11 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段11  |
|  50   | segment12 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段12  |
|  51   | segment13 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段13  |
|  52   | segment14 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段14  |
|  53   | segment15 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段15  |
|  54   | segment16 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段16  |
|  55   | segment17 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段17  |
|  56   | segment18 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段18  |
|  57   | segment19 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段19  |
|  58   | segment20 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段20  |
|  59   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  60   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  61   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  62   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  63   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  64   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  65   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  66   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  67   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  68   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  69   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  70   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  71   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  72   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  73   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  74   | declare_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否申报  |
|  75   | invoice_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否开票  |
|  76   | post_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 入账标识  |
|  77   | post_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 入账日期  |
|  78   | tax_account_status |   varchar   | 20 |   0    |    Y     |  N   |       | 税务系统凭证状态  |
|  79   | gl_acc_entry_status |   varchar   | 20 |   0    |    Y     |  N   |       | 核算平台返回状态  |
|  80   | gl_acc_error_message |   varchar   | 100 |   0    |    Y     |  N   |       | 核算平台错误信息  |
|  81   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  82   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  83   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  84   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  85   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  86   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  87   | process_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 处理状态  |
|  88   | data_type |   varchar   | 20 |   0    |    Y     |  N   |       | 数据创建类型  |
|  89   | set_of_books_id |   bigint   | 20 |   0    |    Y     |  N   |       | 账套id  |
|  90   | process_batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 税务系统批次号  |
|  91   | tax_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税目id  |
|  92   | disc_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币折扣金额  |
|  93   | fun_disc_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币折扣金额  |

**表名：** <a id="tax_vat_output_detail_wait">tax_vat_output_detail_wait</a>

**说明：** 手工价税分离数据临时表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_system |   varchar   | 100 |   0    |    Y     |  N   |       | 系统代码  |
|  3   | cal_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离规则ID  |
|  4   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户ID  |
|  5   | tran_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  6   | tran_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水行号  |
|  7   | data_status |   varchar   | 100 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  8   | accounting_type |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  9   | tran_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  10   | tran_period |   varchar   | 100 |   0    |    Y     |  N   |       | 交易期间  |
|  11   | period_year |   varchar   | 100 |   0    |    Y     |  N   |       | 年份  |
|  12   | period_quarter |   varchar   | 100 |   0    |    Y     |  N   |       | 季度  |
|  13   | org_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构ID  |
|  14   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构CODE  |
|  15   | cost_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心ID  |
|  16   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心CODE  |
|  17   | currency_code |   varchar   | 100 |   0    |    N     |  N   |       | 交易币种  |
|  18   | tran_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 原币交易金额  |
|  19   | fun_tran_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 本币交易金额  |
|  20   | sales |   decimal   | 23 |   2    |    Y     |  N   |       | 原币应税销售额  |
|  21   | fun_sales |   decimal   | 23 |   2    |    Y     |  N   |       | 本币应税销售额  |
|  22   | out_taxes |   decimal   | 23 |   2    |    Y     |  N   |       | 原币销项税额  |
|  23   | fun_out_taxes |   decimal   | 23 |   2    |    Y     |  N   |       | 本币销项税额  |
|  24   | adjust_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 原币调整金额  |
|  25   | fun_adjust_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 本币调整金额  |
|  26   | separate_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离科目id  |
|  27   | dr_or_cr |   varchar   | 100 |   0    |    Y     |  N   |       | 增值税科目方向  |
|  28   | tax_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 增值税科目ID  |
|  29   | tax_rate_code |   varchar   | 100 |   0    |    Y     |  N   |       | 税率代码  |
|  30   | tax_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 税率  |
|  31   | source_tran_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水号  |
|  32   | source_tran_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水行号  |
|  33   | tran_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 交易说明  |
|  34   | exchange_rate_type |   varchar   | 100 |   0    |    Y     |  N   |       | 汇率类型  |
|  35   | exchange_rate_quotation |   varchar   | 100 |   0    |    Y     |  N   |       | 标价方法  |
|  36   | exchange_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 汇率  |
|  37   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段1  |
|  38   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段2  |
|  39   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段3  |
|  40   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段4  |
|  41   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段5  |
|  42   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段6  |
|  43   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段7  |
|  44   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段8  |
|  45   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段9  |
|  46   | segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段10  |
|  47   | segment11 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段11  |
|  48   | segment12 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段12  |
|  49   | segment13 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段13  |
|  50   | segment14 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段14  |
|  51   | segment15 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段15  |
|  52   | segment16 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段16  |
|  53   | segment17 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段17  |
|  54   | segment18 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段18  |
|  55   | segment19 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段19  |
|  56   | segment20 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段20  |
|  57   | genarate_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 数据产生日期  |
|  58   | declare_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否申报  |
|  59   | invoice_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否开票  |
|  60   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  61   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  62   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  63   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  64   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  65   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  66   | manual_header_id |   bigint   | 20 |   0    |    Y     |  N   |       | 手工价税分离头ID  |
|  67   | manual_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 手工价税分离行ID  |
|  68   | tax_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税目ID  |
|  69   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  70   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  71   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  72   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  73   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  74   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  75   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  76   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  77   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  78   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  79   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  80   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  81   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  82   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  83   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  84   | account_entry_id |   bigint   | 20 |   0    |    Y     |  N   |       | 凭证ID  |

**表名：** <a id="tax_vat_output_temp">tax_vat_output_temp</a>

**说明：** 销项发票导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | order_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  3   | disk_firm |   varchar   | 100 |   0    |    Y     |  N   |       | 盘商  |
|  4   | invoice_apply_seq |   varchar   | 100 |   0    |    Y     |  N   |       | 发票申请序列号（申请编号+两位流水号）  |
|  5   | invoice_code |   varchar   | 100 |   0    |    Y     |  N   |       | 发票代码  |
|  6   | invoice_number |   varchar   | 100 |   0    |    Y     |  N   |       | 发票号码  |
|  7   | client_name |   varchar   | 200 |   0    |    Y     |  N   |       | 购方企业名称  |
|  8   | client_tax_num |   varchar   | 200 |   0    |    Y     |  N   |       | 购方税号  |
|  9   | client_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 购方开户行及账号  |
|  10   | client_add_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 购方地址/电话  |
|  11   | issue_date |   varchar   | 300 |   0    |    Y     |  N   |       | 开票日期  |
|  12   | taxpayer_name |   varchar   | 200 |   0    |    Y     |  N   |       | 销方名称  |
|  13   | taxpayer_num |   varchar   | 200 |   0    |    Y     |  N   |       | 销方纳税人识别号  |
|  14   | taxpayer_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 销方开户行及账号  |
|  15   | taxpayer_add_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 销方地址、电话  |
|  16   | goods_name |   varchar   | 100 |   0    |    Y     |  N   |       | 商品名称  |
|  17   | goods_standard |   varchar   | 100 |   0    |    Y     |  N   |       | 规格型号  |
|  18   | goods_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |
|  19   | goods_number |   varchar   | 100 |   0    |    Y     |  N   |       | 数量  |
|  20   | goods_price |   varchar   | 100 |   0    |    Y     |  N   |       | 单价  |
|  21   | sales |   varchar   | 100 |   0    |    Y     |  N   |       | 不含税金额  |
|  22   | vat_rate |   varchar   | 100 |   0    |    Y     |  N   |       | 税率%  |
|  23   | taxes |   varchar   | 100 |   0    |    Y     |  N   |       | 税额  |
|  24   | total_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 价税合计金额  |
|  25   | commodity_code |   varchar   | 100 |   0    |    Y     |  N   |       | 商品编码  |
|  26   | receipt_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 收款人  |
|  27   | invoice_status |   varchar   | 100 |   0    |    Y     |  N   |       | 打印标志；N未打印，Y已打印  |
|  28   | cancel_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 作废标志；N未作废，Y已作废  |
|  29   | bill_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 清单标志  |
|  30   | check_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 复核人  |
|  31   | batch_number |   varchar   | 36 |   0    |    Y     |  N   |       | 批次号  |
|  32   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  33   | error_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 错误标识  |
|  34   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  35   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  36   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  37   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  38   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  39   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_reverse_apply_header">tax_vat_reverse_apply_header</a>

**说明：** 发票红冲申请头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 200 |   0    |    N     |  N   |       | 申请编号  |
|  3   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务状态  |
|  4   | apply_person_id |   varchar   | 100 |   0    |    N     |  N   |       | 申请人ID  |
|  5   | reverse_reason |   varchar   | 100 |   0    |    Y     |  N   |       | 红字信息申请原因  |
|  6   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  7   | invoice_code |   varchar   | 100 |   0    |    Y     |  N   |       | 对应蓝字发票号码  |
|  8   | invoice_number |   varchar   | 100 |   0    |    Y     |  N   |       | 对应蓝字发票代码  |
|  9   | invoice_type_re |   varchar   | 100 |   0    |    N     |  N   |       | 对应蓝字发票类型  |
|  10   | cal_rule_code |   varchar   | 100 |   0    |    N     |  N   |       | 计税规则代码  |
|  11   | invoice_site_id |   bigint   | 20 |   0    |    Y     |  N   |       |   |
|  12   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户ID  |
|  13   | client_name |   varchar   | 200 |   0    |    N     |  N   |       | 客户名称  |
|  14   | client_tax_num |   varchar   | 200 |   0    |    N     |  N   |       | 客户纳税人识别号  |
|  15   | client_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 客户开户行及账号  |
|  16   | client_add_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 客户地址/电话  |
|  17   | taxpayer_id |   varchar   | 200 |   0    |    N     |  N   |       | 纳税主体ID  |
|  18   | taxpayer_name |   varchar   | 200 |   0    |    N     |  N   |       | 销方名称  |
|  19   | taxpayer_num |   varchar   | 300 |   0    |    Y     |  N   |       | 销方纳税人识别号  |
|  20   | taxpayer_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 销方开户行及账号  |
|  21   | taxpayer_add_tel |   varchar   | 200 |   0    |    Y     |  N   |       | 销方地址、电话  |
|  22   | total_amount |   decimal   | 23 |   4    |    Y     |  N   |       | 发票总价税合计金额  |
|  23   | sales |   decimal   | 23 |   4    |    Y     |  N   |       | 发票总不含税金额  |
|  24   | taxes |   decimal   | 23 |   4    |    Y     |  N   |       | 发票总税额  |
|  25   | invoice_memo |   varchar   | 2000 |   0    |    Y     |  N   |       | 发票备注  |
|  26   | receipt_employee |   varchar   | 300 |   0    |    Y     |  N   |       | 收款人  |
|  27   | check_employee |   varchar   | 300 |   0    |    Y     |  N   |       | 复核人  |
|  28   | issue_employee_id |   bigint   | 20 |   0    |    Y     |  N   |       | 开票员ID  |
|  29   | reverse_info_num |   varchar   | 300 |   0    |    Y     |  N   |       | 红字信息表编号  |
|  30   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  31   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  32   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  33   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  34   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  35   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  36   | invoice_header_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  37   | apply_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型（发票红冲申请）  |
|  38   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  39   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据OID  |
|  40   | form_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 表单OID  |
|  41   | apply_person_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 申请人OID  |
|  42   | apply_reason |   varchar   | 100 |   0    |    N     |  N   |       | 申请原因（存十位数字）  |
|  43   | apply_square |   varchar   | 100 |   0    |    Y     |  N   |       | 申请方  |
|  44   | description |   varchar   | 1000 |   0    |    Y     |  N   |       | 说明  |

**表名：** <a id="tax_vat_reverse_apply_line">tax_vat_reverse_apply_line</a>

**说明：** 发票红冲申请行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票红冲申请头ID  |
|  3   | goods_name |   varchar   | 100 |   0    |    N     |  N   |       | 商品名称  |
|  4   | goods_standard |   varchar   | 100 |   0    |    Y     |  N   |       | 规格型号  |
|  5   | goods_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |
|  6   | goods_number |   int   | 10 |   0    |    Y     |  N   |       | 数量  |
|  7   | goods_price |   decimal   | 23 |   4    |    Y     |  N   |       | 单价  |
|  8   | vat_rate |   decimal   | 23 |   4    |    N     |  N   |       | 税率%  |
|  9   | total_amount |   decimal   | 23 |   5    |    Y     |  N   |       | 价税合计金额  |
|  10   | sales |   decimal   | 23 |   6    |    Y     |  N   |       | 不含税金额  |
|  11   | taxes |   decimal   | 23 |   7    |    Y     |  N   |       | 税额  |
|  12   | invoice_line_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票行性质0普通明细行，3被折扣行，4折扣行  |
|  13   | preferential_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 优惠政策标识是否享受  |
|  14   | preferential_policy |   varchar   | 1000 |   0    |    Y     |  N   |       | 优惠政策内容  |
|  15   | zero_rate_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 零税率标识；空非零税率、0：出口退税；1：免税；2：不征税；3：普通零税率  |
|  16   | deduct_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 是否差额征税Y/N  |
|  17   | deduct_amount |   decimal   | 23 |   4    |    Y     |  N   |       | 扣除额  |
|  18   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  19   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  20   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  21   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  22   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  23   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  24   | preferential_tax_rate |   decimal   | 23 |   4    |    Y     |  N   |       | 优惠税率%  |
|  25   | line_num |   varchar   | 100 |   0    |    N     |  N   |       | 序号  |
|  26   | blue_invoice_item_id |   bigint   | 20 |   0    |    Y     |  N   |       | 对应蓝票行D  |
|  27   | reverse_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本次红冲金额  |

**表名：** <a id="tax_vat_reverse_header">tax_vat_reverse_header</a>

**说明：** 发票红冲申请头表（方正版本用）

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 100 |   0    |    N     |  N   |       | 申请编号  |
|  3   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务状态  |
|  4   | instructions |   varchar   | 2000 |   0    |    Y     |  N   |       | 说明  |
|  5   | cancel_reason |   varchar   | 100 |   0    |    N     |  N   |       | 申请原因（存十位数字）  |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  8   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  10   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  12   | apply_person_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人ID  |
|  13   | apply_type |   varchar   | 100 |   0    |    Y     |  N   |       | 事务类型（发票红冲申请）  |
|  14   | document_oid |   varchar   | 100 |   0    |    Y     |  N   |       | 单据oid  |
|  15   | form_oid |   varchar   | 100 |   0    |    Y     |  N   |       | 表单oid  |
|  16   | apply_person_oid |   varchar   | 100 |   0    |    Y     |  N   |       | 申请人oid  |
|  17   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司  |
|  18   | attachment_Oid |   varchar   | 100 |   0    |    Y     |  N   |       | 附件  |

**表名：** <a id="tax_vat_reverse_inf_header">tax_vat_reverse_inf_header</a>

**说明：** 红字信息表申请头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 200 |   0    |    N     |  N   |       | 申请编号  |
|  3   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务状态  |
|  4   | apply_person_id |   varchar   | 100 |   0    |    N     |  N   |       | 申请人ID  |
|  5   | apply_date |   timestamp   | 19 |   0    |    N     |  N   |       | 申请日期  |
|  6   | apply_tax_num |   varchar   | 100 |   0    |    N     |  N   |       | 申请税号  |
|  7   | apply_device_number |   varchar   | 100 |   0    |    Y     |  N   |       | 申请方设备编号  |
|  8   | apply_terminal_number |   varchar   | 100 |   0    |    Y     |  N   |       | 申请方开票点号  |
|  9   | apply_square |   varchar   | 100 |   0    |    N     |  N   |       | 申请方  |
|  10   | deduction_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否抵扣  |
|  11   | apply_reason |   varchar   | 100 |   0    |    N     |  N   |       | 申请原因（存十位数字）  |
|  12   | invoice_code |   varchar   | 100 |   0    |    N     |  N   |       | 对应蓝字发票号码  |
|  13   | invoice_number |   varchar   | 100 |   0    |    N     |  N   |       | 对应蓝字发票代码  |
|  14   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 对应蓝字发票类型  |
|  15   | total_amount |   decimal   | 23 |   4    |    N     |  N   |       | 红票合计金额  |
|  16   | sales |   decimal   | 23 |   4    |    N     |  N   |       | 红票不含税金额  |
|  17   | taxes |   decimal   | 23 |   4    |    N     |  N   |       | 红票税额  |
|  18   | raets |   decimal   | 23 |   4    |    Y     |  N   |       | 红票税率  |
|  19   | mul_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 多税率标识  |
|  20   | reverse_info_num |   varchar   | 100 |   0    |    Y     |  N   |       | 红字信息表编号  |
|  21   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  22   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户ID  |
|  23   | client_name |   varchar   | 200 |   0    |    N     |  N   |       | 客户名称  |
|  24   | client_tax_num |   varchar   | 200 |   0    |    N     |  N   |       | 客户纳税人识别号  |
|  25   | client_bank_acc |   varchar   | 300 |   0    |    Y     |  N   |       | 客户开户行及账号  |
|  26   | client_add_tel |   varchar   | 300 |   0    |    Y     |  N   |       | 客户地址/电话  |
|  27   | taxpayer_name |   varchar   | 300 |   0    |    Y     |  N   |       | 销方名称  |
|  28   | taxpayer_num |   varchar   | 300 |   0    |    Y     |  N   |       | 销方税号  |
|  29   | invoice_memo |   varchar   | 2000 |   0    |    Y     |  N   |       | 发票备注  |
|  30   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  31   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  32   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  33   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  34   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  35   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  36   | apply_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型（红字信息表申请）  |
|  37   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  38   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据OID  |
|  39   | form_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 表单OID  |
|  40   | apply_person_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 申请人OID  |
|  41   | description |   varchar   | 1000 |   0    |    Y     |  N   |       | 说明  |

**表名：** <a id="tax_vat_reverse_inf_line">tax_vat_reverse_inf_line</a>

**说明：** 红字信息申请行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 红字信息表申请头ID  |
|  3   | goods_name |   varchar   | 100 |   0    |    N     |  N   |       | 商品名称  |
|  4   | goods_standard |   varchar   | 100 |   0    |    Y     |  N   |       | 规格型号  |
|  5   | goods_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |
|  6   | goods_number |   bigint   | 20 |   0    |    Y     |  N   |       | 数量  |
|  7   | goods_price |   decimal   | 23 |   4    |    Y     |  N   |       | 单价  |
|  8   | vat_rate |   decimal   | 23 |   4    |    N     |  N   |       | 税率%  |
|  9   | total_amount |   decimal   | 23 |   4    |    Y     |  N   |       | 价税合计金额  |
|  10   | sales |   decimal   | 23 |   4    |    Y     |  N   |       | 税额  |
|  11   | taxes |   decimal   | 23 |   4    |    Y     |  N   |       | 税额  |
|  12   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  15   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  17   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |

**表名：** <a id="tax_vat_reverse_line">tax_vat_reverse_line</a>

**说明：** 发票红冲申请行表（方正版本用）

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票红冲申请头ID  |
|  3   | invoice_header_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID  |
|  4   | reverse_apply |   varchar   | 2000 |   0    |    Y     |  N   |       | 红字申请方  |
|  5   | reverse_info_num |   varchar   | 100 |   0    |    Y     |  N   |       | 红字信息表编号  |
|  6   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  8   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  9   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  10   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  11   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |

**表名：** <a id="tax_vat_rule_dimension">tax_vat_rule_dimension</a>

**说明：** 拓展维度表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | rule_code |   varchar   | 30 |   0    |    N     |  N   |       | 规则代码  |
|  3   | dimension_id |   bigint   | 20 |   0    |    Y     |  N   |       | 维度id  |
|  4   | default_item_id |   bigint   | 20 |   0    |    Y     |  N   |       | 默认维值id  |
|  5   | essential_flag |   varchar   | 10 |   0    |    Y     |  N   |       | 是否必输  |
|  6   | priority |   int   | 10 |   0    |    Y     |  N   |       | 优先级  |
|  7   | tab_name |   varchar   | 50 |   0    |    Y     |  N   |       | 匹配表  |
|  8   | col_name |   varchar   | 50 |   0    |    Y     |  N   |       | 匹配字段  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  10   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  12   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  13   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  14   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_separate_rule">tax_vat_separate_rule</a>

**说明：** 价税分离规则

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_system |   varchar   | 30 |   0    |    N     |  N   |       | 来源系统  |
|  3   | source_data_status |   varchar   | 50 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  4   | separate_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离科目id  |
|  5   | tax_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税目id  |
|  6   | dr_or_cr |   varchar   | 10 |   0    |    Y     |  N   |       | 增值税科目方向  |
|  7   | tax_account_id |   bigint   | 20 |   0    |    Y     |  N   |       | 增值税科目id  |
|  8   | tax_rule_code |   varchar   | 30 |   0    |    Y     |  N   |       | 计税规则  |
|  9   | declare_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否申报  |
|  10   | invoice_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否开票  |
|  11   | accounting_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  12   | enabled |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否启用  |
|  13   | rule_description |   varchar   | 200 |   0    |    Y     |  N   |       | 规则说明  |
|  14   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  15   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  16   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  17   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  18   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  19   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  20   | dimension1_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  21   | dimension1_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  22   | dimension2_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  23   | dimension2_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  24   | dimension3_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  25   | dimension3_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  26   | dimension4_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  27   | dimension4_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  28   | dimension5_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  29   | dimension5_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  30   | dimension6_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  31   | dimension6_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  32   | dimension7_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  33   | dimension7_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  34   | dimension8_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  35   | dimension8_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  36   | dimension9_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  37   | dimension9_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  38   | dimension10_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  39   | dimension10_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  40   | dimension11_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  41   | dimension11_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  42   | dimension12_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  43   | dimension12_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  44   | dimension13_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  45   | dimension13_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  46   | dimension14_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  47   | dimension14_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |
|  48   | dimension15_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  49   | dimension15_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |

**表名：** <a id="tax_vat_separate_rule_add">tax_vat_separate_rule_add</a>

**说明：** 价税分离规则拓展表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | separate_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离规则id  |
|  3   | dimension_id |   bigint   | 20 |   0    |    Y     |  N   |       | 拓展段维度ID  |
|  4   | dimension_value_id |   bigint   | 20 |   0    |    Y     |  N   |       | 拓展段维值ID  |
|  5   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  6   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  7   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  8   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  9   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  10   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  11   | dimension_value_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维值代码  |
|  12   | dimension_value_name |   varchar   | 100 |   0    |    Y     |  N   |       | 维值名称  |

**表名：** <a id="tax_vat_separate_rule_temp">tax_vat_separate_rule_temp</a>

**说明：** 价税分离规则导入表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_system |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统  |
|  3   | source_data_status |   varchar   | 50 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  4   | separate_account_code |   varchar   | 100 |   0    |    Y     |  N   |       | 价税分离科目code  |
|  5   | tax_rate_code |   varchar   | 100 |   0    |    Y     |  N   |       | 税目code  |
|  6   | dr_or_cr |   varchar   | 50 |   0    |    Y     |  N   |       | 增值税科目方向  |
|  7   | tax_account_code |   varchar   | 100 |   0    |    Y     |  N   |       | 增值税科目code  |
|  8   | tax_rule_code |   varchar   | 50 |   0    |    Y     |  N   |       | 计税规则  |
|  9   | declare_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 是否申报  |
|  10   | invoice_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 是否开票  |
|  11   | accounting_flag |   varchar   | 30 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  12   | enabled_str |   varchar   | 30 |   0    |    Y     |  N   |       | 是否启用标识  |
|  13   | enabled |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否启用  |
|  14   | rule_description |   varchar   | 200 |   0    |    Y     |  N   |       | 规则说明  |
|  15   | dimension1_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度1code  |
|  16   | dimension2_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度2code  |
|  17   | dimension3_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度3code  |
|  18   | dimension4_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度4code  |
|  19   | dimension5_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度5code  |
|  20   | dimension6_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度6code  |
|  21   | dimension7_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度7code  |
|  22   | dimension8_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度8code  |
|  23   | dimension9_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度9code  |
|  24   | dimension10_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度10code  |
|  25   | dimension11_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度11code  |
|  26   | dimension12_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度12code  |
|  27   | dimension13_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度13code  |
|  28   | dimension14_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度14code  |
|  29   | dimension15_code |   varchar   | 100 |   0    |    Y     |  N   |       | 维度15code  |
|  30   | order_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  31   | batch_number |   varchar   | 36 |   0    |    Y     |  N   |       | 批次号  |
|  32   | error_detail |   varchar   | 4000 |   0    |    Y     |  N   |       | 错误信息  |
|  33   | error_flag |   bit   | 1 |   0    |    Y     |  N   |       | 错误标识  |
|  34   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  35   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  36   | created_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  37   | last_updated_date |   timestamp   | 19 |   0    |    Y     |  N   |   CURRENT_TIMESTAMP    |   |
|  38   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  39   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  40   | commodity_code |   varchar   | 100 |   0    |    Y     |  N   |       | 商品编码  |
|  41   | invoice_title |   varchar   | 100 |   0    |    Y     |  N   |       | 开票名称  |
|  42   | invoice_type |   varchar   | 100 |   0    |    Y     |  N   |       | 发票类型  |
|  43   | unit |   varchar   | 100 |   0    |    Y     |  N   |       | 单位  |

**表名：** <a id="tax_vat_tran_interface_record">tax_vat_tran_interface_record</a>

**说明：** 恒生交易数据接口表中间表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_table |   varchar   | 100 |   0    |    Y     |  N   |       | 来源表：01：股票期权、02：融资融券、03：恒生流水  |
|  3   | client_acc |   varchar   | 500 |   0    |    Y     |  N   |       | 客户编号  |
|  4   | tran_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  5   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构  |
|  6   | currency_code |   varchar   | 500 |   0    |    Y     |  N   |       | 交易币种  |
|  7   | tran_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币金额  |
|  8   | functional_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币金额  |
|  9   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1?(业务类型）  |
|  10   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2（业务小类）  |
|  11   | tran_num |   varchar   | 100 |   0    |    N     |  N   |       | 交易流水号  |
|  12   | dw_trade_date |   bigint   | 20 |   0    |    N     |  N   |       | 数据日期  |
|  13   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  14   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  15   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  16   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  17   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  18   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_tran_invoice_apply_header">tax_vat_tran_invoice_apply_header</a>

**说明：** 交易流水开票申请头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | apply_number |   varchar   | 200 |   0    |    N     |  N   |       | 申请编号  |
|  3   | apply_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型（交易流水开票申请）  |
|  4   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务审批状态  |
|  5   | apply_person_id |   varchar   | 100 |   0    |    N     |  N   |       | 申请人ID  |
|  6   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  7   | invoice_site_id |   bigint   | 20 |   0    |    N     |  N   |       | 开票点ID  |
|  8   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  9   | output_rax_disk_firm |   varchar   | 100 |   0    |    N     |  N   |       | 销项盘商接口  |
|  10   | memo |   varchar   | 2000 |   0    |    Y     |  N   |       | 备注  |
|  11   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  12   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  15   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_tran_invoice_apply_line">tax_vat_tran_invoice_apply_line</a>

**说明：** 交易流水开票申请行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 开票申请头ID  |
|  3   | tran_invoice_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 交易流水ID  |
|  4   | tran_num |   varchar   | 100 |   0    |    N     |  N   |       | 交易流水号  |
|  5   | client_id |   bigint   | 20 |   0    |    N     |  N   |       | 客户ID  |
|  6   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  7   | invoice_amount |   decimal   | 23 |   2    |    N     |  N   |       | 本次开票金额（含税价）  |
|  8   | tax_rate_id |   varchar   | 100 |   0    |    N     |  N   |       | 增值税税目ID  |
|  9   | vat_rate |   decimal   | 23 |   2    |    N     |  N   |       | 税率%  |
|  10   | perferential_tax_rate |   decimal   | 23 |   2    |    N     |  N   |       | 优惠税率%  |
|  11   | deduct_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 是否差额征税Y/N  |
|  12   | deduct_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 扣除额  |
|  13   | sales |   decimal   | 23 |   2    |    N     |  N   |       | 不含税金额  |
|  14   | taxes |   decimal   | 23 |   2    |    N     |  N   |       | 税额  |
|  15   | invoice_title |   varchar   | 100 |   0    |    N     |  N   |       | 开票名称  |
|  16   | goods_id |   bigint   | 20 |   0    |    N     |  N   |       | 商品编码ID  |
|  17   | zero_rate_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 零税率标识，空非零税率、0：出口退税；1：免税；2：不征税；3：普通零税率  |
|  18   | receipt_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 收款人  |
|  19   | check_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 复核人  |
|  20   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  21   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  22   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  23   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  24   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_vat_tran_invoice_detail">tax_vat_tran_invoice_detail</a>

**说明：** 待开票交易流水明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tran_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 来源交易明细表ID  |
|  3   | output_detail_id |   bigint   | 20 |   0    |    N     |  N   |       | 来源销项明细表ID  |
|  4   | source_system |   varchar   | 400 |   0    |    Y     |  N   |       | 来源系统  |
|  5   | data_type |   varchar   | 100 |   0    |    Y     |  N   |       | 数据类型（是否价税分离）  |
|  6   | tran_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  7   | sourse_tran_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水号  |
|  8   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户ID  |
|  9   | cal_rule_code |   varchar   | 100 |   0    |    Y     |  N   |       | 计税规则（一般/简易/免税）  |
|  10   | tran_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  11   | tran_period |   varchar   | 100 |   0    |    Y     |  N   |       | 交易期间  |
|  12   | period_year |   varchar   | 100 |   0    |    Y     |  N   |       | 年份  |
|  13   | period_quarter |   bigint   | 20 |   0    |    Y     |  N   |       | 季度  |
|  14   | org_id |   bigint   | 20 |   0    |    N     |  N   |       | 机构ID  |
|  15   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构代码  |
|  16   | cost_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心ID  |
|  17   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心  |
|  18   | currency_code |   varchar   | 100 |   0    |    N     |  N   |       | 币种  |
|  19   | tran_amount |   decimal   | 23 |   2    |    N     |  N   |       | 原币交易金额（价税合计）  |
|  20   | fun_tran_amount |   decimal   | 23 |   2    |    N     |  N   |       | 本币交易金额  |
|  21   | dsct_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 原币折扣金额  |
|  22   | fun_dsct_ampunt |   decimal   | 23 |   2    |    Y     |  N   |       | 本币折扣金额  |
|  23   | dsct_invoice_flag |   varchar   | 100 |   0    |    Y     |  N   |   1    | 是否折扣Y/N  |
|  24   | tax_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 增值税税目ID  |
|  25   | vat_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 税率%  |
|  26   | preferential_tax_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 优惠税率%  |
|  27   | zero_rate_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 零税率标识，空非零税率、0：出口退税；1：免税；2：不征税；3：普通零税率  |
|  28   | deduct_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 是否差额征税Y/N  |
|  29   | deduct_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 扣除额  |
|  30   | sales |   decimal   | 23 |   2    |    N     |  N   |       | 原币销售额（不含税）  |
|  31   | fun_sales |   decimal   | 23 |   2    |    N     |  N   |       | 本币销售额  |
|  32   | fun_out_taxes |   decimal   | 23 |   2    |    N     |  N   |       | 本币税额  |
|  33   | exchange_rate_type |   varchar   | 100 |   0    |    Y     |  N   |       | 汇率类型  |
|  34   | exchange_rate |   decimal   | 23 |   6    |    Y     |  N   |       | 汇率值  |
|  35   | memo |   varchar   | 200 |   0    |    Y     |  N   |       | 备注  |
|  36   | separate_rule_id |   bigint   | 20 |   0    |    N     |  N   |       | 价税分离规则ID  |
|  37   | invoice_rule_id |   bigint   | 20 |   0    |    N     |  N   |       | 开票规则ID  |
|  38   | goods_id |   bigint   | 20 |   0    |    N     |  N   |       | 商品编码ID  |
|  39   | invoice_title |   varchar   | 1000 |   0    |    Y     |  N   |       | 开票名称  |
|  40   | invoice_type |   varchar   | 100 |   0    |    Y     |  N   |       | 发票类型  |
|  41   | goods_standard |   varchar   | 200 |   0    |    Y     |  N   |       | 商品规格型号  |
|  42   | goods_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 商品单位  |
|  43   | goods_number |   bigint   | 20 |   0    |    Y     |  N   |       | 商品数量  |
|  44   | goods_price |   decimal   | 23 |   2    |    Y     |  N   |       | 商品单价  |
|  45   | receipt_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 收款人  |
|  46   | check_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 复核人  |
|  47   | write_off_status |   varchar   | 100 |   0    |    N     |  N   |       | N未核销Y部分C全部核销  |
|  48   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  49   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  50   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  51   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  52   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  53   | out_taxes |   decimal   | 23 |   2    |    Y     |  N   |       | 本币税额  |
|  54   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  55   | may_invoice_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 可开票金额  |

**表名：** <a id="tax_vat_tran_write_off">tax_vat_tran_write_off</a>

**说明：** 核销正式表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | write_off_type |   varchar   | 100 |   0    |    Y     |  N   |       | 核销类型;INVOICE_TRAN:发票核销交易;REVERSE_TRAN:反冲核销交易  |
|  3   | tran_invoice_detail_id |   bigint   | 20 |   0    |    Y     |  N   |       | 待开票交易流水ID  |
|  4   | write_off_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 核销金额  |
|  5   | write_off_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 核销日期，取交易流水开票申请创建日期  |
|  6   | period_name |   varchar   | 100 |   0    |    Y     |  N   |       | 核销期间  |
|  7   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  8   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  10   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  12   | document_source |   varchar   | 100 |   0    |    Y     |  N   |       | 单据来源；INVOICE:发票REVERSE_TRAN:反冲交易  |
|  13   | document_header_id |   bigint   | 20 |   0    |    Y     |  N   |       | 交易流水开票申请头ID  |
|  14   | document_line_id |   bigint   | 20 |   0    |    Y     |  N   |       | 如果反冲交易，则取反冲交易流水ID；如果发票，则取发票正式表头ID  |
|  15   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |

**表名：** <a id="tax_vat_trans_detail">tax_vat_trans_detail</a>

**说明：** 交易明细表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | interface_id |   bigint   | 20 |   0    |    Y     |  N   |       | 来源接口表ID  |
|  3   | source_system |   varchar   | 30 |   0    |    N     |  N   |       | 来源系统  |
|  4   | cal_rule_id |   bigint   | 20 |   0    |    Y     |  N   |       | 价税分离规则  |
|  5   | client_id |   bigint   | 20 |   0    |    Y     |  N   |       | 客户ID  |
|  6   | trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  7   | trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水行号  |
|  8   | source_data_status |   varchar   | 50 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  9   | accounting_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否生成凭证  |
|  10   | trans_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  11   | trans_period |   varchar   | 20 |   0    |    Y     |  N   |       | 交易期间  |
|  12   | trans_year |   varchar   | 20 |   0    |    Y     |  N   |       | 年份  |
|  13   | trans_quarter |   varchar   | 20 |   0    |    Y     |  N   |       | 季度  |
|  14   | org_id |   bigint   | 20 |   0    |    Y     |  N   |       | 机构ID  |
|  15   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构  |
|  16   | cost_center_id |   bigint   | 20 |   0    |    Y     |  N   |       | 责任中心ID  |
|  17   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心  |
|  18   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 交易币种  |
|  19   | amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币金额  |
|  20   | functional_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币金额  |
|  21   | disc_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币折扣金额  |
|  22   | func_disc_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币折扣金额  |
|  23   | deduct_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 差额开票标识  |
|  24   | deduct_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 差额开票抵扣额  |
|  25   | sales |   decimal   | 21 |   2    |    Y     |  N   |       | 原币应税销售额  |
|  26   | fun_sales |   decimal   | 21 |   2    |    Y     |  N   |       | 本币应税销售额  |
|  27   | output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 原币销项税额  |
|  28   | fun_output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 本币销项税额  |
|  29   | tax_rate_code |   varchar   | 100 |   0    |    Y     |  N   |       | 税率代码  |
|  30   | tax_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 税率  |
|  31   | source_trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水号  |
|  32   | source_trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水行号  |
|  33   | trans_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 交易说明  |
|  34   | exchange_rate_type |   varchar   | 100 |   0    |    Y     |  N   |       | 汇率类型  |
|  35   | exchange_rate_quotation |   varchar   | 100 |   0    |    Y     |  N   |       | 标价方法  |
|  36   | exchange_rate |   decimal   | 23 |   2    |    Y     |  N   |       | 汇率  |
|  37   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段1  |
|  38   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段2  |
|  39   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段3  |
|  40   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段4  |
|  41   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段5  |
|  42   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段6  |
|  43   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段7  |
|  44   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段8  |
|  45   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段9  |
|  46   | segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段10  |
|  47   | segment11 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段11  |
|  48   | segment12 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段12  |
|  49   | segment13 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段13  |
|  50   | segment14 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段14  |
|  51   | segment15 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段15  |
|  52   | segment16 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段16  |
|  53   | segment17 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段17  |
|  54   | segment18 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段18  |
|  55   | segment19 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段19  |
|  56   | segment20 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段20  |
|  57   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  58   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  59   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  60   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  61   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  62   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  63   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  64   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  65   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  66   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  67   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  68   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  69   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  70   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  71   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  72   | data_type |   varchar   | 20 |   0    |    Y     |  N   |       | 数据创建类型  |
|  73   | declare_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否申报  |
|  74   | invoice_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 是否开票  |
|  75   | process_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 价税分离执行标志  |
|  76   | process_batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 税务系统批次号  |
|  77   | tax_account_status |   varchar   | 20 |   0    |    Y     |  N   |       | 税务系统凭证状态  |
|  78   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  79   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  80   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  81   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  82   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  83   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  84   | set_of_books_id |   bigint   | 20 |   0    |    Y     |  N   |       | 账套id  |
|  85   | tax_rate_id |   bigint   | 20 |   0    |    Y     |  N   |       | 税目id  |

**表名：** <a id="tax_vat_trans_interface">tax_vat_trans_interface</a>

**说明：** 交易接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_system |   varchar   | 30 |   0    |    N     |  N   |       | 来源系统  |
|  3   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  4   | trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  5   | trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水行号  |
|  6   | source_data_status |   varchar   | 50 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  7   | client_number_original |   varchar   | 100 |   0    |    Y     |  N   |       | 来源系统客户编号  |
|  8   | taxpayer_name |   varchar   | 100 |   0    |    Y     |  N   |       | 客户纳税人名称  |
|  9   | client_tax_type |   varchar   | 20 |   0    |    Y     |  N   |       | 客户纳税人类型  |
|  10   | client_tax_bank |   varchar   | 300 |   0    |    Y     |  N   |       | 开户行  |
|  11   | client_tax_acc |   varchar   | 200 |   0    |    Y     |  N   |       | 银行账号  |
|  12   | payee_name |   varchar   | 100 |   0    |    Y     |  N   |       | 收款人  |
|  13   | check_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 复核人  |
|  14   | trans_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 交易日期  |
|  15   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构  |
|  16   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心  |
|  17   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 交易币种  |
|  18   | amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币金额  |
|  19   | functional_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币金额  |
|  20   | disc_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 原币折扣金额  |
|  21   | func_disc_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 本币折扣金额  |
|  22   | deduct_flag |   tinyint   | 4 |   0    |    Y     |  N   |       | 差额开票标识  |
|  23   | deduct_amount |   decimal   | 21 |   2    |    Y     |  N   |       | 差额开票抵扣额  |
|  24   | output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 原币销项税额  |
|  25   | fun_output_taxes |   decimal   | 21 |   2    |    Y     |  N   |       | 本币销项税额  |
|  26   | source_trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水号  |
|  27   | source_trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水行号  |
|  28   | trans_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 交易说明  |
|  29   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段1  |
|  30   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段2  |
|  31   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段3  |
|  32   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段4  |
|  33   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段5  |
|  34   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段6  |
|  35   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段7  |
|  36   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段8  |
|  37   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段9  |
|  38   | segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段10  |
|  39   | segment11 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段11  |
|  40   | segment12 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段12  |
|  41   | segment13 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段13  |
|  42   | segment14 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段14  |
|  43   | segment15 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段15  |
|  44   | segment16 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段16  |
|  45   | segment17 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段17  |
|  46   | segment18 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段18  |
|  47   | segment19 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段19  |
|  48   | segment20 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段20  |
|  49   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  50   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  51   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  52   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  53   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  54   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  55   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  56   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  57   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  58   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  59   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  60   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  61   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  62   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  63   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  64   | data_type |   varchar   | 20 |   0    |    Y     |  N   |       | 数据创建类型  |
|  65   | error_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 数据状态  |
|  66   | error_message |   varchar   | 200 |   0    |    Y     |  N   |       | 错误说明  |
|  67   | import_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 导入标识  |
|  68   | process_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 价税分离执行标志  |
|  69   | process_batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 税务系统批次号  |
|  70   | tax_account_status |   varchar   | 20 |   0    |    Y     |  N   |       | 税务系统凭证状态  |
|  71   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  72   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  73   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  74   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  75   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  76   | sales |   decimal   | 21 |   2    |    Y     |  N   |       | 原币应税销售额  |
|  77   | fun_sales |   decimal   | 21 |   2    |    Y     |  N   |       | 本币应税销售额  |
|  78   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  79   | source_table |   varchar   | 100 |   0    |    Y     |  N   |       | 恒生机构交易流水来源类型（1:恒生佣金及手续费收入,2:融资融券利息收入,3:质押约定购回利息收入）,校验数据重复使用  |
|  80   | dw_trade_date |   decimal   | 39 |   0    |    Y     |  N   |       | 数据日期,校验数据重复使用  |

**表名：** <a id="tax_vat_trans_interface_temp">tax_vat_trans_interface_temp</a>

**说明：** 交易接口表导入临时表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | source_system |   varchar   | 30 |   0    |    Y     |  N   |       | 来源系统  |
|  3   | batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 批次号  |
|  4   | trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水号  |
|  5   | trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 交易流水行号  |
|  6   | source_data_status |   varchar   | 50 |   0    |    Y     |  N   |       | 来源数据价税状态  |
|  7   | client_number_original |   varchar   | 100 |   0    |    Y     |  N   |       | 客户账号  |
|  8   | taxpayer_name |   varchar   | 100 |   0    |    Y     |  N   |       | 客户纳税人名称  |
|  9   | client_tax_type |   varchar   | 20 |   0    |    Y     |  N   |       | 客户纳税人类型  |
|  10   | client_tax_bank |   varchar   | 300 |   0    |    Y     |  N   |       | 开户行  |
|  11   | client_tax_acc |   varchar   | 200 |   0    |    Y     |  N   |       | 银行账号  |
|  12   | payee_name |   varchar   | 100 |   0    |    Y     |  N   |       | 收款人  |
|  13   | check_employee |   varchar   | 100 |   0    |    Y     |  N   |       | 复核人  |
|  14   | trans_date |   varchar   | 100 |   0    |    Y     |  N   |       | 交易日期  |
|  15   | org |   varchar   | 100 |   0    |    Y     |  N   |       | 机构  |
|  16   | cost_center |   varchar   | 100 |   0    |    Y     |  N   |       | 责任中心  |
|  17   | currency_code |   varchar   | 100 |   0    |    Y     |  N   |       | 交易币种  |
|  18   | amount |   varchar   | 100 |   0    |    Y     |  N   |       | 原币金额  |
|  19   | functional_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 本币金额  |
|  20   | disc_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 原币折扣金额  |
|  21   | func_disc_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 本币折扣金额  |
|  22   | deduct_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 差额开票标识  |
|  23   | deduct_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 差额开票抵扣额  |
|  24   | output_taxes |   varchar   | 100 |   0    |    Y     |  N   |       | 原币销项税额  |
|  25   | fun_output_taxes |   varchar   | 100 |   0    |    Y     |  N   |       | 本币销项税额  |
|  26   | source_trans_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水号  |
|  27   | source_trans_line_num |   varchar   | 100 |   0    |    Y     |  N   |       | 反冲交易来源交易流水行号  |
|  28   | trans_desc |   varchar   | 100 |   0    |    Y     |  N   |       | 交易说明  |
|  29   | segment1 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段1  |
|  30   | segment2 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段2  |
|  31   | segment3 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段3  |
|  32   | segment4 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段4  |
|  33   | segment5 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段5  |
|  34   | segment6 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段6  |
|  35   | segment7 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段7  |
|  36   | segment8 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段8  |
|  37   | segment9 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段9  |
|  38   | segment10 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段10  |
|  39   | segment11 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段11  |
|  40   | segment12 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段12  |
|  41   | segment13 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段13  |
|  42   | segment14 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段14  |
|  43   | segment15 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段15  |
|  44   | segment16 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段16  |
|  45   | segment17 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段17  |
|  46   | segment18 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段18  |
|  47   | segment19 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段19  |
|  48   | segment20 |   varchar   | 100 |   0    |    Y     |  N   |       | 科目段20  |
|  49   | match_field1 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段1  |
|  50   | match_field2 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段2  |
|  51   | match_field3 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段3  |
|  52   | match_field4 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段4  |
|  53   | match_field5 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段5  |
|  54   | match_field6 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段6  |
|  55   | match_field7 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段7  |
|  56   | match_field8 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段8  |
|  57   | match_field9 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段9  |
|  58   | match_field10 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段10  |
|  59   | match_field11 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段11  |
|  60   | match_field12 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段12  |
|  61   | match_field13 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段13  |
|  62   | match_field14 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段14  |
|  63   | match_field15 |   varchar   | 100 |   0    |    Y     |  N   |       | 匹配段15  |
|  64   | data_type |   varchar   | 20 |   0    |    Y     |  N   |       | 数据创建类型  |
|  65   | error_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 数据状态  |
|  66   | error_message |   varchar   | 1000 |   0    |    Y     |  N   |       | 错误说明  |
|  67   | import_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 导入标识  |
|  68   | process_flag |   varchar   | 20 |   0    |    Y     |  N   |       | 价税分离执行标志  |
|  69   | process_batch_id |   varchar   | 100 |   0    |    Y     |  N   |       | 税务系统批次号  |
|  70   | tax_account_status |   varchar   | 20 |   0    |    Y     |  N   |       | 税务系统凭证状态  |
|  71   | sales |   varchar   | 100 |   0    |    Y     |  N   |       | 原币应税销售额  |
|  72   | fun_sales |   varchar   | 100 |   0    |    Y     |  N   |       | 本币应税销售额  |
|  73   | source_table |   varchar   | 100 |   0    |    Y     |  N   |       | 恒生机构交易流水来源类型（1:恒生佣金及手续费收入,2:融资融券利息收入,3:质押约定购回利息收入）,校验数据重复使用  |
|  74   | dw_trade_date |   varchar   | 100 |   0    |    Y     |  N   |       | 数据日期,校验数据重复使用  |
|  75   | line_number |   varchar   | 30 |   0    |    Y     |  N   |       | 行号  |
|  76   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  77   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  78   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  79   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  80   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  81   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_version_manage_inform">tax_version_manage_inform</a>

**说明：** 版本管理基础信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_code |   varchar   | 300 |   0    |    N     |  N   |       | 版本号  |
|  3   | version_name |   varchar   | 600 |   0    |    N     |  N   |       | 版本名称  |
|  4   | taxpayer_id |   bigint   | 20 |   0    |    N     |  N   |       | 纳税主体ID  |
|  5   | data_year |   varchar   | 100 |   0    |    Y     |  N   |       | 年度  |
|  6   | declare_type |   varchar   | 100 |   0    |    N     |  N   |       | 周期精度  |
|  7   | declare_period |   varchar   | 100 |   0    |    N     |  N   |       | 申报周期  |
|  8   | version_status |   varchar   | 100 |   0    |    N     |  N   |       | 版本状态  |
|  9   | creation_type |   varchar   | 100 |   0    |    N     |  N   |       | 创建方式  |
|  10   | history_version_id |   bigint   | 20 |   0    |    Y     |  N   |       | 管理历史版本ID  |
|  11   | apply_type |   varchar   | 100 |   0    |    N     |  N   |       | 事务类型（版本管理创建申请）  |
|  12   | apply_status |   varchar   | 100 |   0    |    N     |  N   |       | 事务审批状态  |
|  13   | memo |   varchar   | 1000 |   0    |    Y     |  N   |       | 申请备注说明  |
|  14   | applicant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 申请人ID  |
|  15   | document_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 单据OID  |
|  16   | applicant_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 申请人OID  |
|  17   | form_oid |   varchar   | 300 |   0    |    Y     |  N   |       | 表单OID  |
|  18   | company_id |   bigint   | 20 |   0    |    Y     |  N   |       | 公司ID  |
|  19   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  20   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  21   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  22   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  23   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  24   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |
|  25   | attachment_oid |   varchar   | 4000 |   0    |    Y     |  N   |       | 附件  |
|  26   | tax_category |   varchar   | 200 |   0    |    N     |  N   |       | 税种代码  |
|  27   | draft_type |   varchar   | 50 |   0    |    N     |  N   |       | 底稿类型  |
|  28   | tax_category_type |   varchar   | 50 |   0    |    N     |  N   |       | 税种类型代码  |
|  29   | date_from |   varchar   | 100 |   0    |    Y     |  N   |       | 税款所属期起  |
|  30   | date_to |   varchar   | 100 |   0    |    Y     |  N   |       | 税款所属期止  |
|  31   | one_touch_status |   varchar   | 100 |   0    |    Y     |  N   |       | 一键生成状态  |
|  32   | settle_pay_version |   varchar   | 100 |   0    |    Y     |  N   |       | 汇缴版本  |
|  33   | check_status |   varchar   | 100 |   0    |    Y     |  N   |       | 校验状态  |
|  34   | file_status |   varchar   | 100 |   0    |    Y     |  N   |       | 归档状态  |
|  35   | function_type |   varchar   | 30 |   0    |    Y     |  N   |       | 功能类型，计提、支付  |
|  36   | transaction_type |   varchar   | 30 |   0    |    Y     |  N   |       | 事务类型，计提，结转，缴纳，手工  |
|  37   | correct_version_id |   bigint   | 20 |   0    |    Y     |  N   |       | 更正版本ID  |
|  38   | account_date |   varchar   | 100 |   0    |    Y     |  N   |       | 凭证日期  |
|  39   | adjust_amount |   decimal   | 23 |   2    |    Y     |  N   |       | 调整金额  |

**表名：** <a id="tax_version_table">tax_version_table</a>

**说明：** 版本管理关联表单信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | version_id |   bigint   | 20 |   0    |    N     |  N   |       | 版本ID  |
|  3   | table_model_id |   bigint   | 20 |   0    |    N     |  N   |       | 表单模板ID  |
|  4   | table_index_num |   varchar   | 300 |   0    |    N     |  N   |       | 表单索引号  |
|  5   | table_model_code |   varchar   | 300 |   0    |    N     |  N   |       | 表单模板代码  |
|  6   | table_model_name |   varchar   | 300 |   0    |    N     |  N   |       | 表单模板名称  |
|  7   | TABLE_NAME |   varchar   | 1000 |   0    |    N     |  N   |       | 表单名称  |
|  8   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户id  |
|  9   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  10   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  12   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  13   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="tax_work_order_interface">tax_work_order_interface</a>

**说明：** 税务会计引擎接口表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | company_id |   bigint   | 20 |   0    |    N     |  N   |       | 公司ID  |
|  3   | department_id |   bigint   | 20 |   0    |    N     |  N   |       | 部门ID  |
|  4   | employee_id |   bigint   | 20 |   0    |    N     |  N   |       | 员工ID  |
|  5   | work_order_number |   varchar   | 100 |   0    |    N     |  N   |       | 版本编码  |
|  6   | requisition_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 申请日期  |
|  7   | work_order_type_id |   bigint   | 20 |   0    |    N     |  N   |       | 核算工单类型ID  |
|  8   | remark |   varchar   | 500 |   0    |    Y     |  N   |       | 备注  |
|  9   | currency |   varchar   | 20 |   0    |    N     |  N   |       | 币种  |
|  10   | exchange_rate |   decimal   | 23 |   2    |    N     |  N   |       | 汇率  |
|  11   | account_id |   bigint   | 20 |   0    |    N     |  N   |       | 科目ID  |
|  12   | responsibility_center_id |   bigint   | 20 |   0    |    N     |  N   |       | 责任中心ID  |
|  13   | account_code |   varchar   | 100 |   0    |    N     |  N   |       | 科目CODE  |
|  14   | entered_amount_dr |   decimal   | 23 |   2    |    N     |  N   |       | 原币借方金额  |
|  15   | entered_amount_cr |   decimal   | 23 |   2    |    N     |  N   |       | 原币贷方金额  |
|  16   | functional_amount_dr |   decimal   | 23 |   2    |    N     |  N   |       | 本币借方金额  |
|  17   | functional_amount_cr |   decimal   | 23 |   2    |    N     |  N   |       | 本币贷方金额  |
|  18   | description |   varchar   | 300 |   0    |    Y     |  N   |       | 行说明  |
|  19   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户ID  |
|  20   | version_number |   int   | 10 |   0    |    N     |  N   |   1    | 版本号  |
|  21   | created_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 创建日期  |
|  22   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户ID  |
|  23   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  24   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户ID  |

**表名：** <a id="vat_input_certificates_base">vat_input_certificates_base</a>

**说明：** 纳税主体认证基础信息表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_no |   varchar   | 100 |   0    |    N     |  N   |       | 纳税主体识别号（不允许重复）  |
|  3   | current_tax_period |   varchar   | 100 |   0    |    N     |  N   |       | 当前税款所属期  |
|  4   | legalize_end_date |   varchar   | 100 |   0    |    N     |  N   |       | 当前税款所属,期勾选截止日  |
|  5   | legalize_invoice_date_begin |   varchar   | 100 |   0    |    N     |  N   |       | 当前税款所属期可勾选发票开票日期起  |
|  6   | legalize_invoice_date_end |   varchar   | 100 |   0    |    N     |  N   |       | 当前税款所属期可勾选发票开票日期至  |
|  7   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  8   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  9   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  10   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  11   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  12   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |

**表名：** <a id="vat_input_certificates_head">vat_input_certificates_head</a>

**说明：** 进项发票底库头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | invoice_code |   varchar   | 100 |   0    |    N     |  N   |       | 发票代码  |
|  3   | invoice_number |   varchar   | 100 |   0    |    N     |  N   |       | 发票号码  |
|  4   | invoice_state |   varchar   | 100 |   0    |    N     |  N   |       | 发票状态：0-正常1-失控2-作废3-红冲4-异常  |
|  5   | invoice_date |   timestamp   | 19 |   0    |    N     |  N   |       | 发票日期  |
|  6   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型：01-增值税专用发票；06-货物运输业增值税专用发票；07-机动车销售统一发票；05-税收缴款凭证；03-海关进口增值税专用缴款书；04-农产品销售发票；09-境外服务单据；10-非税收费收据；99-其他  |
|  7   | buyer_tax_name |   varchar   | 100 |   0    |    Y     |  N   |       | 购方名称  |
|  8   | buyer_tax_number |   varchar   | 100 |   0    |    Y     |  N   |       | 购方纳税识别号  |
|  9   | saler_name |   varchar   | 100 |   0    |    Y     |  N   |       | 销方名称  |
|  10   | saler_tax_no |   varchar   | 100 |   0    |    Y     |  N   |       | 销方纳税人识别号  |
|  11   | invoice_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 发票金额  |
|  12   | tax_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 发票税额  |
|  13   | total_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 价税合计  |
|  14   | legalize_state |   varchar   | 100 |   0    |    Y     |  N   |       | 认证状态  |
|  15   | legalize_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 认证日期  |
|  16   | tax_period |   varchar   | 100 |   0    |    Y     |  N   |       | 税款所属期  |
|  17   | reimbursement_flag |   varchar   | 100 |   0    |    Y     |  N   |       | 是否报账  |
|  18   | reimbursement_date |   timestamp   | 19 |   0    |    Y     |  N   |       | 报账日期  |
|  19   | reimbursement_num |   varchar   | 100 |   0    |    Y     |  N   |       | 报销单号  |
|  20   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户  |
|  21   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  22   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  23   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  24   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  25   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
|  26   | reimbursement_id |   varchar   | 50 |   0    |    Y     |  N   |       |   |
|  27   | current_tax_period |   varchar   | 10 |   0    |    Y     |  N   |       | 当前税款所属期  |
|  28   | legalize_end_date |   varchar   | 10 |   0    |    Y     |  N   |       | 当前税款所属期勾选截止日  |
|  29   | legalize_end_date_begin |   varchar   | 10 |   0    |    Y     |  N   |       | 当前税款所属期可勾选发票开票日期起  |
|  30   | legalize_end_date_end |   varchar   | 10 |   0    |    Y     |  N   |       | 当前税款所属期可勾选发票开票日期至  |

**表名：** <a id="vat_input_certificates_inf_h">vat_input_certificates_inf_h</a>

**说明：** 进项发票底库接口头表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | tax_no |   varchar   | 100 |   0    |    N     |  N   |       | 纳税主体税号  |
|  3   | task_no |   varchar   | 100 |   0    |    N     |  N   |       | 批次号  |
|  4   | invoice_quantity |   varchar   | 100 |   0    |    N     |  N   |       | 发票数量  |
|  5   | current_tax_period |   varchar   | 100 |   0    |    N     |  N   |       | 当前税款所属期  |
|  6   | legalize_end_date |   varchar   | 100 |   0    |    N     |  N   |       | 当前税款所属  |
|  7   | legalize_invoice_date_begin |   varchar   | 100 |   0    |    N     |  N   |       | 期勾选截止日  |
|  8   | legalize_invoice_date_end |   varchar   | 100 |   0    |    N     |  N   |       | 当前税款所属期可勾选发票开票日期起  |
|  9   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  10   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  11   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  12   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  13   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  14   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |

**表名：** <a id="vat_input_certificates_inf_l">vat_input_certificates_inf_l</a>

**说明：** 进项发票底库接口行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | header_id |   bigint   | 20 |   0    |    N     |  N   |       | 头ID  |
|  3   | invoice_code |   varchar   | 100 |   0    |    N     |  N   |       | 发票代码  |
|  4   | invoice_no |   varchar   | 100 |   0    |    N     |  N   |       | 发票号码  |
|  5   | invoice_type |   varchar   | 100 |   0    |    N     |  N   |       | 发票类型  |
|  6   | buyer_name |   varchar   | 100 |   0    |    N     |  N   |       | 购方名称  |
|  7   | buyer_tax_number |   varchar   | 100 |   0    |    N     |  N   |       | 购方纳税识别号  |
|  8   | buyer_address_phone |   varchar   | 100 |   0    |    N     |  N   |       | 购方地址电话  |
|  9   | buyer_acount |   varchar   | 100 |   0    |    N     |  N   |       | 购方开户行及账号  |
|  10   | saler_name |   varchar   | 100 |   0    |    N     |  N   |       | 销方名称  |
|  11   | saler_tax_no |   varchar   | 100 |   0    |    N     |  N   |       | 销方税号  |
|  12   | saler_address_phone |   varchar   | 100 |   0    |    N     |  N   |       | 销方地址、电话  |
|  13   | saler_acount |   varchar   | 100 |   0    |    N     |  N   |       | 销方开户行及账号  |
|  14   | invoice_date |   timestamp   | 19 |   0    |    N     |  N   |       | 发票日期  |
|  15   | invoice_amount |   varchar   | 100 |   0    |    N     |  N   |       | 发票金额  |
|  16   | invoice_tax_amount |   varchar   | 100 |   0    |    N     |  N   |       | 发票税额  |
|  17   | total_amount |   varchar   | 100 |   0    |    N     |  N   |       | 价税合计  |
|  18   | remark |   varchar   | 100 |   0    |    N     |  N   |       | 备注  |
|  19   | invoice_status |   varchar   | 100 |   0    |    N     |  N   |       | 发票状态0：正常1：失控2：作废3：红冲4：异常  |
|  20   | legalize_state |   varchar   | 100 |   0    |    N     |  N   |       | 认证状态0：未认证1：已认证2不认证  |
|  21   | legalize_date |   varchar   | 100 |   0    |    N     |  N   |       | 认证日期  |
|  22   | tax_period |   varchar   | 100 |   0    |    N     |  N   |       | 税款所属期  |
|  23   | detail_no |   varchar   | 100 |   0    |    N     |  N   |       | 明细编号  |
|  24   | goods_name |   varchar   | 100 |   0    |    N     |  N   |       | 货物名称  |
|  25   | goods_num |   varchar   | 100 |   0    |    N     |  N   |       | 商品编码  |
|  26   | specification_model |   varchar   | 100 |   0    |    N     |  N   |       | 规格型号  |
|  27   | unit |   varchar   | 100 |   0    |    N     |  N   |       | 计量单位  |
|  28   | num |   varchar   | 100 |   0    |    N     |  N   |       | 数量  |
|  29   | unit_price |   varchar   | 100 |   0    |    N     |  N   |       | 不含税价  |
|  30   | detail_amount |   varchar   | 100 |   0    |    N     |  N   |       | 金额  |
|  31   | tax_amount |   varchar   | 100 |   0    |    N     |  N   |       | 税额  |
|  32   | car_number |   varchar   | 100 |   0    |    N     |  N   |       | 车牌号  |
|  33   | data_type |   varchar   | 100 |   0    |    Y     |  N   |       | 类型  |
|  34   | transit_begin |   varchar   | 100 |   0    |    N     |  N   |       | 通行时间起  |
|  35   | transit_end |   varchar   | 100 |   0    |    N     |  N   |       | 通行时间至  |
|  36   | purchase_num |   varchar   | 100 |   0    |    N     |  N   |       | 购买方身份证号码  |
|  37   | car_type |   varchar   | 100 |   0    |    N     |  N   |       | 车辆类型  |
|  38   | car_unit |   varchar   | 100 |   0    |    N     |  N   |       | 厂牌型号  |
|  39   | car_location |   varchar   | 100 |   0    |    N     |  N   |       | 产地  |
|  40   | certification |   varchar   | 100 |   0    |    N     |  N   |       | 合格证书  |
|  41   | certification_num |   varchar   | 100 |   0    |    N     |  N   |       | 进口证明书号  |
|  42   | commodity_cheack |   varchar   | 100 |   0    |    N     |  N   |       | 商检单号  |
|  43   | engine_no |   varchar   | 100 |   0    |    N     |  N   |       | 发动机号码  |
|  44   | car_no |   varchar   | 100 |   0    |    N     |  N   |       | 车架号码  |
|  45   | pay_tax |   varchar   | 100 |   0    |    N     |  N   |       | 完税凭证号码  |
|  46   | tonnage |   varchar   | 100 |   0    |    N     |  N   |       | 吨位  |
|  47   | limit_no |   varchar   | 100 |   0    |    N     |  N   |       | 限乘人数  |
|  48   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  49   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  50   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  51   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  52   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  53   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |

**表名：** <a id="vat_input_certificates_line">vat_input_certificates_line</a>

**说明：** 进项发票底库行表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | head_id |   bigint   | 20 |   0    |    N     |  N   |       | 发票头ID(对应底库头表ID)  |
|  3   | detail_no |   varchar   | 100 |   0    |    Y     |  N   |       | 明细编号  |
|  4   | goods_name |   varchar   | 100 |   0    |    Y     |  N   |       | 货物名称  |
|  5   | goods_num |   varchar   | 100 |   0    |    Y     |  N   |       | 商品编码  |
|  6   | specification_model |   varchar   | 100 |   0    |    Y     |  N   |       | 规格型号  |
|  7   | unit |   varchar   | 100 |   0    |    Y     |  N   |       | 计量单位  |
|  8   | num |   varchar   | 100 |   0    |    Y     |  N   |       | 数量  |
|  9   | unit_price |   varchar   | 100 |   0    |    Y     |  N   |       | 不含税价  |
|  10   | detail_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 金额  |
|  11   | tax_amount |   varchar   | 100 |   0    |    Y     |  N   |       | 税额  |
|  12   | car_number |   varchar   | 100 |   0    |    Y     |  N   |       | 车牌号  |
|  13   | data_type |   varchar   | 100 |   0    |    Y     |  N   |       | 类型  |
|  14   | transit_begin |   varchar   | 100 |   0    |    Y     |  N   |       | 通行时间起  |
|  15   | transit_end |   varchar   | 100 |   0    |    Y     |  N   |       | 通行时间至  |
|  16   | purchase_num |   varchar   | 100 |   0    |    Y     |  N   |       | 购买方身份证号码  |
|  17   | car_type |   varchar   | 100 |   0    |    Y     |  N   |       | 车辆类型  |
|  18   | car_unit |   varchar   | 100 |   0    |    Y     |  N   |       | 厂牌型号  |
|  19   | car_location |   varchar   | 100 |   0    |    Y     |  N   |       | 产地  |
|  20   | certification |   varchar   | 100 |   0    |    Y     |  N   |       | 合格证书  |
|  21   | certification_num |   varchar   | 100 |   0    |    Y     |  N   |       | 进口证明书号  |
|  22   | commodity_cheack |   varchar   | 100 |   0    |    Y     |  N   |       | 商检单号  |
|  23   | engine_no |   varchar   | 100 |   0    |    Y     |  N   |       | 发动机号码  |
|  24   | car_no |   varchar   | 100 |   0    |    Y     |  N   |       | 车架号码  |
|  25   | pay_tax |   varchar   | 100 |   0    |    Y     |  N   |       | 完税凭证号码  |
|  26   | tonnage |   varchar   | 100 |   0    |    Y     |  N   |       | 吨位  |
|  27   | limit_no |   varchar   | 100 |   0    |    Y     |  N   |       | 限乘人数  |
|  28   | tenant_id |   bigint   | 20 |   0    |    Y     |  N   |       | 租户  |
|  29   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  30   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  31   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  32   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  33   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |

**表名：** <a id="vat_input_invoice_hx_logs">vat_input_invoice_hx_logs</a>

**说明：** 进项发票日志表

**数据列：**

| 序号 | 名称 | 数据类型 |  长度  | 小数位 | 允许空值 | 主键 | 默认值 | 说明 |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
|  1   | id |   bigint   | 20 |   0    |    N     |  Y   |       |   |
|  2   | app_sec_id |   varchar   | 100 |   0    |    N     |  N   |       | 授权ID，航信提供  |
|  3   | app_sec |   varchar   | 100 |   0    |    N     |  N   |       | 签名数据  |
|  4   | app_id |   varchar   | 100 |   0    |    N     |  N   |       | 应用标识，固定：JXFP  |
|  5   | version |   varchar   | 30 |   0    |    N     |  N   |       | 接口版，v1.0  |
|  6   | interface_code |   varchar   | 30 |   0    |    N     |  N   |       | 接口编码  |
|  7   | enterprise_code |   varchar   | 30 |   0    |    N     |  N   |       | 企业代码  |
|  8   | data_exchange_id |   varchar   | 50 |   0    |    N     |  N   |       | 数据交换流水号，enterpriseCode+8位日期(YYYYMMDD)+9位序列号  |
|  9   | return_code |   varchar   | 100 |   0    |    Y     |  N   |       | 返回代码  |
|  10   | return_message |   varchar   | 100 |   0    |    Y     |  N   |       | 返回描述  |
|  11   | tenant_id |   bigint   | 20 |   0    |    N     |  N   |       | 租户  |
|  12   | version_number |   int   | 10 |   0    |    N     |  N   |       | 版本号  |
|  13   | created_by |   bigint   | 20 |   0    |    N     |  N   |       | 创建用户id  |
|  14   | created_date |   timestamp   | 19 |   0    |    N     |  N   |       | 创建日期  |
|  15   | last_updated_by |   bigint   | 20 |   0    |    N     |  N   |       | 最后更新用户id  |
|  16   | last_updated_date |   timestamp   | 19 |   0    |    N     |  N   |   CURRENT_TIMESTAMP    | 最后更新日期  |
