美恰引用统一事项
---------

	MQConfig.init(context, meiqiaAppKey, new OnInitCallback() {
        @Override
        public void onSuccess(String clientId) {
            //以下用到的clientId
        }

        @Override
        public void onFailure(int code, String message) {

        }
    });

###### 1.自定义客户id
	美恰API中的setCustomizedId(String customizedId)中的定义采用以下方式组合
	业务系统中的 **customizedId=userId+clientId**

###### 2.设置统一参数
	//https://app.meiqia.com/setting/id-query
    builder.setScheduledAgent("客服id 管理后台可查");
    builder.setScheduledGroup("客服组id 管理后台可查");
   	//根据企业ID随机分配客服
    builder.setScheduleRule(MQScheduleRule.REDIRECT_ENTERPRISE);
    builder.setClientId(“设置初始成功后对应的clientId”);

###### 2.提交的用户(客户)信息
	clientInfo.put("name", "用户(客户)名称");
    clientInfo.put("avatar", “用户(客户)头像”);
    clientInfo.put("gender", "用户(客户)性别");
    clientInfo.put("tel", "电话号码");
    clientInfo.put("source", "安卓/IOS 任选一即可");
    clientInfo.put("address", "用户(客户)联系地址");
    clientInfo.put("email", "用户(客户)电子邮箱");
    clientInfo.put("comment", “渠道,示例 channel:appstore”);