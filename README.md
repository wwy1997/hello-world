
##API列表

魔蝎API采用REST基础的接口规范，所有API都是通过向魔蝎的REST Sever发送HTTP请求来实现。查询数据接口提供**一次性获取银行理财产品全部数据的聚合接口**。

#### 获取银行理财产品全部数据的聚合接口

1. [查询银行理财产品全量信息](#getv1-data)
2. [分页查询银行理财产品信息](#getv1-datapaging)

***以上接口在使用时，http header中需要有
Authorization: “token value” ，value值由魔蝎提供***

#### 获取银行理财产品全部数据的聚合接口

<h5 id="getv1-data"> 1. 查询银行理财产品全量信息</h5>

接口名称  |  查询银行理财产品信息
------------- | -------------
接口描述  | 根据bank_code查询银行理财产品信息
接口类型  | https get
url  | https://api.51datakey.com/gateway/bankproduct/v1/{bank_code}/data
使用场景| 根据bankcode查询银行理财产品数据接口

#####request
调用url，url path参数为bank_code

#####response
返回如下信息:

```javascript
{
  "code": "string",
  "message": "string",
  "data": {
    "product_list": [
      {
        "base_info": {
          "bankCode": "string",
          "proCode": "string",
          "proName": "string",
          "proAttr": "string",
          "proType": "string",
          "sellObject": "string",
          "status": "string",
          "currency": "string",
          "crFlag": "string",
          "startDate": "date",
          "endDate": "date",
          "openDate": "date",
          "nextOpenDate": "date",
          "nextEndDate": "date",
          "realEndDate": "date",
          "cycleTime": "string",
          "incomeRateName":"string",
          "incomeRate": "string",
          "nextIncomeRate": "string",
          "interestType": "string",
          "riskLevel": "string",
          "redRule": "string",
          "buyRule": "string",
          "openTime": "string",
          "closeTime": "string",
          "proManager": "string",
          "sellArea": "string",
          "sellChannel": "string",
          "currentPurchases": "string",
          "firstAmount": "string",
          "firstSubMinAmount": "string",
          "minPurBalance": "string",
          "minRedBalance": "string",
          "minSubUnit": "string",
          "minPurUnit": "string",
          "minRedUnit": "string",
          "maxSingleSub": "string",
          "maxSinglePur": "string",
          "maxSingleRed": "string",
          "minSingleSub": "string",
          "minSinglePur": "string",
          "minSingleRed": "string",
          "maxOneDaySub": "string",
          "plainHold": "string",
          "proNetValue": "string",
          "allowedResRed": "string",
          "allowedRelRed": "string"
        },
        "detail_info": {
          "bankCode": "string",
          "proCode": "string",
          "proName": "string",
          "overviewUrl": "string",
          "infoUrl": "string",
          "noticeUrl": "string",
          "netWorthUrl": "string",
          "reportUrl": "string",
          "commentUrl": "string",
          "instructionUrl": "string",
          "riskDisclosureUrl": "string"
        }
      },
      {...}
    ]
  }
}
```

字段说明

字段名  |   字段描述 |   备注 |
------------- | ------------- | ------------- |
**base_info** |**基本信息** |
bankCode |银行缩写 |
proCode |产品代码 |
proName |产品名称 |
proAttr |产品类别 |
proType |投资类型 |
sellObject |销售对象 |
status |产品状态 |
currency |产品币种 |
crFlag |钞汇标志 |
startDate |募集开始日 |
endDate |募集截止日 |
openDate |产品成立日 |即起息日
nextOpenDate |下一开放日 |
nextEndDate |下下开放日 |
realEndDate |产品到期日 |
cycleTime |投资周期 |
incomeRateName |产品收益率名称 |
incomeRate |本期预期收益率 |
nextIncomeRate |下期预期收益率 |
interestType |计息基准类型 |
riskLevel |风险等级 |
redRule |赎回规则 |
buyRule |买入规则 |
openTime |开市时间 |
closeTime |闭市时间 |
proManager |代理机构 |
sellArea |销售区域 |
sellChannel |销售渠道 |
currentPurchases |当前购买人数 |
firstAmount |起购金额 |
firstSubMinAmount |首次认购下限 |
minPurBalance |最低申购余额 |
minRedBalance |最低赎回余额 |
minSubUnit |认购基数 |
minPurUnit |申购基数 |
minRedUnit |赎回基数 |
maxSingleSub |单笔认购上限 |
maxSinglePur |单笔申购上限 |
maxSingleRed |单笔赎回上限 |
minSingleSub |单笔认购下限 |
minSinglePur |单笔申购下限 |
minSingleRed |单笔赎回下限 |
maxOneDaySub |当日购买上限 |
plainHold |最低持仓份额 |
proNetValue |产品净值 |
allowedResRed |是否允许预约赎回 |
allowedRelRed |是否允许实时赎回 |
**detail_info** |**详细信息** |
bankCode |银行缩写 |
proCode |产品代码 |
proName |产品名称 |
overviewUrl |产品概览 |
infoUrl |产品信息 |
noticeUrl |产品公告 |
netWorthUrl |产品净值 |
reportUrl |产品报告 |
commentUrl |产品评论 |
instructionUrl |产品说明书 |
riskDisclosureUrl |风险揭示书 |


#####样例数据

```javascript
{
  "code": "0",
  "message": "请求数据成功",
  "data": {
    "product_list": [
      {
        "base_info": {
          "bankCode": "CMBC",
          "proCode": "FSAB13917B",
          "proName": "非凡资产管理翠竹13W理财产品周一高端09款",
          "proAttr": "资产类",
          "proType": "定期开放型",
          "sellObject": "个人",
          "status": "开放期",
          "currency": "人民币",
          "crFlag": "现钞",
          "startDate": "2017-12-21",
          "endDate": "2017-12-23",
          "openDate": "2017-12-24",
          "nextOpenDate": "2018-09-24",
          "nextEndDate": "2018-12-23",
          "realEndDate": "2099-12-30",
          "cycleTime": "91天",
          "incomeRateName":"年化收益率",
          "incomeRate": "5.00%",
          "nextIncomeRate": "0.00%",
          "interestType": "ACT\\/365",
          "riskLevel": "较低风险(二级)",
          "redRule": "每日0:00-24:00 赎回费率为0",
          "buyRule": "现在买入，07.04开始计算收益",
          "openTime": "09:00:00",
          "closeTime": "09:00:00",
          "proManager": "招商银行",
          "sellArea": "全国",
          "sellChannel": "网上，手机，PAD，网点",
          "currentPurchases": "16,273,935",
          "firstAmount": "5万",
          "firstSubMinAmount": "200,000.00",
          "minPurBalance": "10,000.00",
          "minRedBalance": "10,000.00",
          "minSubUnit": "10,000.00",
          "minPurUnit": "0",
          "minRedUnit": "0",
          "maxSingleSub": "100,000,000",
          "maxSinglePur": "0",
          "maxSingleRed": "0",
          "minSingleSub": "0",
          "minSinglePur": "0",
          "minSingleRed": "0",
          "maxOneDaySub": "200,000.00",
          "plainHold": "200,000.00",
          "proNetValue": "1.000000000000",
          "allowedResRed": "是",
          "allowedRelRed": "否"
        },
        "detail_info": {
          "bankCode": "CMBC",
          "proCode": "FSAB13917B",
          "proName": "非凡资产管理翠竹13W理财产品周一高端09款",
          "overviewUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodintro",
          "infoUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodinfo",
          "noticeUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodnotice",
          "netWorthUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodvalue",
          "reportUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodir",
          "commentUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodcomment",
          "instructionUrl": "hhttp://www.cmbc.com.cn/Personal/productdetail.aspx?code=11&type=prodexplain",
          "riskDisclosureUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodrisk"
        }
      },
      {...}
    ]
  }
}
```

<h5 id="getv1-datapaging"> 2. 分页查询银行理财产品信息</h5>

接口名称  |  分页查询银行理财产品信息
------------- | -------------
接口描述  | 根据bank_code查询银行理财产品信息
接口类型  | https get
url  | https://api.51datakey.com/gateway/bankproduct/v1/{bank_code}/datapaging
使用场景| 根据bankcode分页查询银行理财产品数据接口

#####request
调用url，url path参数为bank_code，query参数为page,limit

#####response
返回如下信息:

```javascript
{
  "code": "string",
  "message": "string",
  "data": {
    "product_list": [
      {
        "base_info": {
          "bankCode": "string",
          "proCode": "string",
          "proName": "string",
          "proAttr": "string",
          "proType": "string",
          "sellObject": "string",
          "status": "string",
          "currency": "string",
          "crFlag": "string",
          "startDate": "date",
          "endDate": "date",
          "openDate": "date",
          "nextOpenDate": "date",
          "nextEndDate": "date",
          "realEndDate": "date",
          "cycleTime": "string",
          "incomeRateName":"string",
          "incomeRate": "string",
          "nextIncomeRate": "string",
          "interestType": "string",
          "riskLevel": "string",
          "redRule": "string",
          "buyRule": "string",
          "openTime": "string",
          "closeTime": "string",
          "proManager": "string",
          "sellArea": "string",
          "sellChannel": "string",
          "currentPurchases": "string",
          "firstAmount": "string",
          "firstSubMinAmount": "string",
          "minPurBalance": "string",
          "minRedBalance": "string",
          "minSubUnit": "string",
          "minPurUnit": "string",
          "minRedUnit": "string",
          "maxSingleSub": "string",
          "maxSinglePur": "string",
          "maxSingleRed": "string",
          "minSingleSub": "string",
          "minSinglePur": "string",
          "minSingleRed": "string",
          "maxOneDaySub": "string",
          "plainHold": "string",
          "proNetValue": "string",
          "allowedResRed": "string",
          "allowedRelRed": "string"
        },
        "detail_info": {
          "bankCode": "string",
          "proCode": "string",
          "proName": "string",
          "overviewUrl": "string",
          "infoUrl": "string",
          "noticeUrl": "string",
          "netWorthUrl": "string",
          "reportUrl": "string",
          "commentUrl": "string",
          "instructionUrl": "string",
          "riskDisclosureUrl": "string"
        }
      },
      {...}
    ]
  }
}
```

字段说明

字段名  |   字段描述 |   备注 |
------------- | ------------- | ------------- |
**base_info** |**基本信息** |
bankCode |银行缩写 |
proCode |产品代码 |
proName |产品名称 |
proAttr |产品类别 |
proType |投资类型 |
sellObject |销售对象 |
status |产品状态 |
currency |产品币种 |
crFlag |钞汇标志 |
startDate |募集开始日 |
endDate |募集截止日 |
openDate |产品成立日 |即起息日
nextOpenDate |下一开放日 |
nextEndDate |下下开放日 |
realEndDate |产品到期日 |
cycleTime |投资周期 |
incomeRateName |产品收益率名称 |
incomeRate |本期预期收益率 |
nextIncomeRate |下期预期收益率 |
interestType |计息基准类型 |
riskLevel |风险等级 |
redRule |赎回规则 |
buyRule |买入规则 |
openTime |开市时间 |
closeTime |闭市时间 |
proManager |代理机构 |
sellArea |销售区域 |
sellChannel |销售渠道 |
currentPurchases |当前购买人数 |
firstAmount |起购金额 |
firstSubMinAmount |首次认购下限 |
minPurBalance |最低申购余额 |
minRedBalance |最低赎回余额 |
minSubUnit |认购基数 |
minPurUnit |申购基数 |
minRedUnit |赎回基数 |
maxSingleSub |单笔认购上限 |
maxSinglePur |单笔申购上限 |
maxSingleRed |单笔赎回上限 |
minSingleSub |单笔认购下限 |
minSinglePur |单笔申购下限 |
minSingleRed |单笔赎回下限 |
maxOneDaySub |当日购买上限 |
plainHold |最低持仓份额 |
proNetValue |产品净值 |
allowedResRed |是否允许预约赎回 |
allowedRelRed |是否允许实时赎回 |
**detail_info** |**详细信息** |
bankCode |银行缩写 |
proCode |产品代码 |
proName |产品名称 |
overviewUrl |产品概览 |
infoUrl |产品信息 |
noticeUrl |产品公告 |
netWorthUrl |产品净值 |
reportUrl |产品报告 |
commentUrl |产品评论 |
instructionUrl |产品说明书 |
riskDisclosureUrl |风险揭示书 |


#####样例数据

```javascript
{
  "code": "0",
  "message": "请求数据成功。共914条数据，每页10条数据，共92页，当前第3页。",
  "data": {
    "product_list": [
      {
        "base_info": {
          "bankCode": "CMBC",
          "proCode": "FSAB13917B",
          "proName": "非凡资产管理翠竹13W理财产品周一高端09款",
          "proAttr": "资产类",
          "proType": "定期开放型",
          "sellObject": "个人",
          "status": "开放期",
          "currency": "人民币",
          "crFlag": "现钞",
          "startDate": "2017-12-21",
          "endDate": "2017-12-23",
          "openDate": "2017-12-24",
          "nextOpenDate": "2018-09-24",
          "nextEndDate": "2018-12-23",
          "realEndDate": "2099-12-30",
          "cycleTime": "91天",
          "incomeRateName":"年化收益率",
          "incomeRate": "5.00%",
          "nextIncomeRate": "0.00%",
          "interestType": "ACT\\/365",
          "riskLevel": "较低风险(二级)",
          "redRule": "每日0:00-24:00 赎回费率为0",
          "buyRule": "现在买入，07.04开始计算收益",
          "openTime": "09:00:00",
          "closeTime": "09:00:00",
          "proManager": "招商银行",
          "sellArea": "全国",
          "sellChannel": "网上，手机，PAD，网点",
          "currentPurchases": "16,273,935",
          "firstAmount": "5万",
          "firstSubMinAmount": "200,000.00",
          "minPurBalance": "10,000.00",
          "minRedBalance": "10,000.00",
          "minSubUnit": "10,000.00",
          "minPurUnit": "0",
          "minRedUnit": "0",
          "maxSingleSub": "100,000,000",
          "maxSinglePur": "0",
          "maxSingleRed": "0",
          "minSingleSub": "0",
          "minSinglePur": "0",
          "minSingleRed": "0",
          "maxOneDaySub": "200,000.00",
          "plainHold": "200,000.00",
          "proNetValue": "1.000000000000",
          "allowedResRed": "是",
          "allowedRelRed": "否"
        },
        "detail_info": {
          "bankCode": "CMBC",
          "proCode": "FSAB13917B",
          "proName": "非凡资产管理翠竹13W理财产品周一高端09款",
          "overviewUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodintro",
          "infoUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodinfo",
          "noticeUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodnotice",
          "netWorthUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodvalue",
          "reportUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodir",
          "commentUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodcomment",
          "instructionUrl": "hhttp://www.cmbc.com.cn/Personal/productdetail.aspx?code=11&type=prodexplain",
          "riskDisclosureUrl": "http://www.cmbc.com.cn/productdetail.aspx?code=11&type=prodrisk"
        }
      },
      {...}
    ]
  }
}
```
##安全认证

所有的HTTP请求必须带上头部  Authorization: “token $token” ，
或 Authorization: “apikey $apikey”，$token和$apikey由魔蝎为合作机构分配.

