# API接口

## 一、概述

足量的数据是支撑预言机的基础。对于房贷利率数据，我们以两种形式对外提供服务。第一种是http的API接口。第二种通过合约直接调取。

本文档为方便使用http接口提供指南与支持。

API接口分为两个部分，一部分提供房贷利率信息，另一部分提供房价变化信息

## 二、房贷利率接口

### 1.抵押利率查询

#### 1.1 接口地址：[https://api.fan.finance/api/getRate](https://api.fan.finance/api/getRate)

```html
https://api.fan.finance/api/getRate?limit=10&page=1&loanType=purchase&propertyValue=100000&propertyType=SingleFamily&propertyUse=PrimaryResidence&cashOutAmount=0&zipCode=90210&loanAmount=80,000&fico=740&points=all&product_name=30&firstTimeHomebuyer=false
```

#### 1.2 请求方式

```
get
```

#### 1.3 请求参数

| No   | key           | type    | description                                                  |
| ---- | ------------- | ------- | ------------------------------------------------------------ |
| 1    | limit         | number  | 单页条数                                                     |
| 2    | page          | number  | 页码                                                         |
| 3    | loanType      | string  | 贷款类型                                                     |
| 4    | propertyValue | number  | 例：`100000`, `200000`, `500000`, `1000000`, `2000000`       |
| 5    | propertyType  | enum    | 例：`SingleFamily`, `MultiFamily2Units`, `Condo4OrFewerStories`, `Townhouse`, `MultiFamily3Units`, `MultiFamily4Units` |
| 6    | propertyUse   | enum    | 例：`PrimaryResidence`, `SecondaryOrVacation`, `InvestmentOrRental` |
| 7    | cashOutAmount |         |                                                              |
| 8    | zipCode       | varchar | 邮编                                                         |
| 9    | loanAmount    | enum    | 例：`purchase`, `refinance`                                  |
| 10   | creditScore   | enum    | 例：`740`, `730`, `710`, `690`, `670`, `650`, `630`, `600`   |
| 11   | points        |         |                                                              |

#### 1.4 返回示例

```json
{
    "code":0,
    "msg":"success",
    "data":{
        "page":"1",
        "limit":"10",
        "total":"5",
        "content":[
            "{"id":"6d0e2c46-608e-4afe-9209-311d45dfa1c3","advertiser":{"city":"","description":"","email":"","features":[],"hoursOfOperation":"","id":0,"isFeatured":false,"isFuse":false,"logo":{},"name":"LincolnWay Community Bank","nmlsLicense":"","note":{"isHyperLinkable":false,"text":""},"phone":"","reviews":{"averageRating":0,"count":0},"score":0,"seoName":"","specials":[],"state":"","stateLicense":"","surveyInstitutionId":0},"apr":2.856,"date":"2021-01-06T08:29:31.626Z","estimatedPayment":326.59,"fees":[{"description":"Upfront Fees","amount":1085,"HUDLine":0,"required":false}],"fiveYearCost":10392.34,"isPaid":false,"lockDays":30,"source":"mortgage-portal","product":{"term":360,"size":"conforming","isInterestOnly":false,"type":"fixed","name":"30 year fixed","isFHA":false,"id":166,"purpose":"purchase","pointsBand":"Zero","isVA":false,"fixedMonths":360,"points":0},"rate":2.75,"armDetails":null,"type":"editorial","upFrontCosts":1085,"displayTargets":["desktopRateTable","mobileRateTable"],"tags":[],"phone":"","isFeatured":false}",
            "{"id":"aaba55c0-6b7d-4f9a-8c23-cde709be9328","advertiser":{"city":"","description":"","email":"","features":[],"hoursOfOperation":"","id":0,"isFeatured":false,"isFuse":false,"logo":{},"name":"Schools First FCU","nmlsLicense":"","note":{"isHyperLinkable":false,"text":""},"phone":"","reviews":{"averageRating":0,"count":0},"score":0,"seoName":"","specials":[],"state":"","stateLicense":"","surveyInstitutionId":0},"apr":2.972,"date":"2021-01-06T08:29:31.626Z","estimatedPayment":331.91,"fees":[{"description":"Upfront Fees","amount":995,"HUDLine":0,"required":false}],"fiveYearCost":10876.79,"isPaid":false,"lockDays":30,"source":"mortgage-portal","product":{"term":360,"size":"conforming","isInterestOnly":false,"type":"fixed","name":"30 year fixed","isFHA":false,"id":166,"purpose":"purchase","pointsBand":"Zero","isVA":false,"fixedMonths":360,"points":0},"rate":2.875,"armDetails":null,"type":"editorial","upFrontCosts":995,"displayTargets":["desktopRateTable","mobileRateTable"],"tags":[],"phone":"","isFeatured":false}",
            "{"id":"ae3f736d-ef41-41f9-a044-c126610f3272","advertiser":{"city":"","description":"","email":"","features":[],"hoursOfOperation":"","id":0,"isFeatured":false,"isFuse":false,"logo":{},"name":"Star One Credit Union","nmlsLicense":"","note":{"isHyperLinkable":false,"text":""},"phone":"","reviews":{"averageRating":0,"count":0},"score":0,"seoName":"","specials":[],"state":"","stateLicense":"","surveyInstitutionId":0},"apr":2.635,"date":"2021-01-06T08:29:31.626Z","estimatedPayment":321.32,"fees":[{"description":"Upfront Fees","amount":105,"HUDLine":0,"required":false}],"fiveYearCost":9908.72,"isPaid":false,"lockDays":30,"source":"mortgage-portal","product":{"term":360,"size":"conforming","isInterestOnly":false,"type":"fixed","name":"30 year fixed","isFHA":false,"id":166,"purpose":"purchase","pointsBand":"Zero","isVA":false,"fixedMonths":360,"points":0},"rate":2.625,"armDetails":null,"type":"editorial","upFrontCosts":105,"displayTargets":["desktopRateTable","mobileRateTable"],"tags":[],"phone":"","isFeatured":false}",
            "{"id":"059ff0dd-4c1c-4792-ac55-81e84d3a5efd","advertiser":{"city":"","description":"","email":"","features":[],"hoursOfOperation":"","id":0,"isFeatured":false,"isFuse":false,"logo":{},"name":"BBVA","nmlsLicense":"","note":{"isHyperLinkable":false,"text":""},"phone":"","reviews":{"averageRating":0,"count":0},"score":0,"seoName":"","specials":[],"state":"","stateLicense":"","surveyInstitutionId":0},"apr":2.83,"date":"2021-01-06T08:29:31.626Z","estimatedPayment":321.32,"fees":[{"description":"Discount Points","amount":1000,"HUDLine":841,"required":true}],"fiveYearCost":10908.72,"isPaid":false,"lockDays":30,"source":"mortgage-portal","product":{"term":360,"size":"conforming","isInterestOnly":false,"type":"fixed","name":"30 year fixed","isFHA":false,"id":168,"purpose":"purchase","pointsBand":"OneToTwo","isVA":false,"fixedMonths":360,"points":1.25},"rate":2.625,"armDetails":null,"type":"editorial","upFrontCosts":1000,"displayTargets":["desktopRateTable","mobileRateTable"],"tags":[],"phone":"","isFeatured":false}",
            "{"id":"f997fa81-7341-4504-b85a-0ea3eda660f6","advertiser":{"city":"","description":"","email":"","features":[],"hoursOfOperation":"","id":0,"isFeatured":false,"isFuse":false,"logo":{},"name":"First Citizens Bank","nmlsLicense":"","note":{"isHyperLinkable":false,"text":""},"phone":"","reviews":{"averageRating":0,"count":0},"score":0,"seoName":"","specials":[],"state":"","stateLicense":"","surveyInstitutionId":0},"apr":2.706,"date":"2021-01-06T08:29:31.626Z","estimatedPayment":321.32,"fees":[{"description":"Upfront Fees","amount":842,"HUDLine":0,"required":false}],"fiveYearCost":9908.72,"isPaid":false,"lockDays":30,"source":"mortgage-portal","product":{"term":360,"size":"conforming","isInterestOnly":false,"type":"fixed","name":"30 year fixed","isFHA":false,"id":166,"purpose":"purchase","pointsBand":"Zero","isVA":false,"fixedMonths":360,"points":0},"rate":2.625,"armDetails":null,"type":"editorial","upFrontCosts":842,"displayTargets":["desktopRateTable","mobileRateTable"],"tags":[],"phone":"","isFeatured":false}"
        ]
    }
}
```

### 2.美国十大城市平均房贷利率列表

#### 2.1 接口地址：https://api.fan.finance/api/getRateAvg

#### 2.2 请求方式

```
get
```

#### 2.3 请求参数

```
无
```

#### 2.4 返回示例

```json
{
    "code":0,
    "msg":"success",
    "data":[
        {
            "city":"Philadelphia",
            "product":[
                {
                    "name":"10/1 ARM refinance",
                    "interestRate":"3.305",
                    "APR":"3.231"
                },
                {
                    "name":"15 year fixed refinance",
                    "interestRate":"2.432",
                    "APR":"2.695"
                },
                {
                    "name":"15 year jumbo refinance",
                    "interestRate":"2.644",
                    "APR":"2.845"
                }
            ]
        }
    ]
}
```

## 三、房产价值接口

### 1.房产价值变化查询接口

#### 1.1 接口地址https://api.fan.finance/api/getZillowInfo

```
https://api.fan.finance/api/getZillowInfo?zipCode=00501
```

#### 1.2 请求方式

```
get
```

#### 1.3 请求参数

| No   | key     | type   | description |
| ---- | ------- | ------ | ----------- |
| 1    | zipCode | number | 邮编        |

#### 1.4 返回示例

```json
{
    "code":0,
    "msg":"success",
    "data":{
        "zipCode":"00501",
        "city":"Holtsville",
        "shortState":"NY",
        "regionId":"58001",
        "priceArr":[
            {
                "timestamp":"1296432000000",
                "price":"76940"
            },
            {
                "timestamp":"1298851200000",
                "price":"76819"
            },
            ...
        ],
        "forecastArr":[
            {
                "timestamp":"1612051200000",
                "price":"111497"
            },
            {
                "timestamp":"1614470400000",
                "price":"112917"
            },
            ...
        ]
    }
}
```

