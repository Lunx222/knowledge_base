## 3.1 月票（MonthBill）
PS:需要用admin用户获得access_token
### 3.1.1 get接口
- 功能描述: 根据id查找该MonthBill的详细信息
- 请求地址: `http://domain/billing/monthBills/{id}?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/billing/monthBills/1009?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`

- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1009,
        "customerCarPlate": "皖A54321",
        "customerName": "孟阿瑾",
        "customerPhoneNum": "133333333335",
        "customerCardNum": "325452155845245262",
        "startMonth": 1501545600000,
        "endMonth": 1509408000000,
        "roadSectionIds": [
            1020
        ],
        "shouldPay": 10000,
        "actualPay": 10000,
        "valid": true,
        "description": null
    }
}
```
### 3.1.2 list接口
- 功能描述: 查找MonthBill列表
- 请求地址: `http://domain/billing/monthBills?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/billing/monthBills?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`

- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "id": 1009,
                "customerCarPlate": "皖A54321",
                "customerName": "孟阿瑾",
                "customerPhoneNum": "133333333335",
                "customerCardNum": "325452155845245262",
                "startMonth": 1501545600000,
                "endMonth": 1509408000000,
                "roadSectionIds": [
                    1020
                ],
                "shouldPay": 10000,
                "actualPay": 10000,
                "valid": true,
                "description": null
            },
            {
                "id": 1014,
                "customerCarPlate": "皖A12346",
                "customerName": "高颖",
                "customerPhoneNum": "133333333333",
                "customerCardNum": "325452155845245865",
                "startMonth": 1501545600000,
                "endMonth": 1509408000000,
                "roadSectionIds": [
                    1036
                ],
                "shouldPay": 10000,
                "actualPay": 10000,
                "valid": true,
                "description": null
            }
        ],
        "last": true,
        "totalElements": 2,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 2
    }
}
```
### 3.1.3 save接口
- 功能描述: 新增一个MonthBill，并保存进数据库
- 请求地址: `http://domain/billing/monthBills?access_token=token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/billing/monthBills?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
- Body：
```
{
    "customerCarPlate": "皖A12346",
    "customerName": "高颖",
    "customerPhoneNum": "133333333333",
    "customerCardNum": "325452155845245865",
    "startMonth": 1501545600000,
    "endMonth": 1509408000000,
    "roadSectionIds": [
        1036
    ],
    "shouldPay": 10000,
    "actualPay": 10000,
    "valid": true,
    "description": null
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1017,
        "customerCarPlate": "皖A12346",
        "customerName": "高颖",
        "customerPhoneNum": "133333333333",
        "customerCardNum": "325452155845245865",
        "startMonth": 1501545600000,
        "endMonth": 1509408000000,
        "roadSectionIds": [
            1036
        ],
        "shouldPay": 10000,
        "actualPay": 10000,
        "valid": true,
        "description": null
    }
}
```
### 3.1.4 update接口
- 功能描述: 传入Id，更新该MonthBill
- 请求地址: `http://domain/billing/monthBills/{id}?access_token=token`
- 请求动作: `PUT`
- 请求示例: `http://localhost:8080/billing/monthBills/1017?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
- Body：
```
{
    "customerName": "ygao"
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1017,
        "customerCarPlate": "皖A12346",
        "customerName": "ygao",
        "customerPhoneNum": "133333333333",
        "customerCardNum": "325452155845245865",
        "startMonth": 1501545600000,
        "endMonth": 1509408000000,
        "roadSectionIds": [
            1036
        ],
        "shouldPay": 10000,
        "actualPay": 10000,
        "valid": true,
        "description": null
    }
}
```
### 3.1.5 check接口
- 功能描述: 传入车牌号和路段Id，查看该车在该路段是否具有月票
- 请求地址: `http://domain/billing/monthBills/checkMonthBill?access_token=token&customerCarPlate=_customerCarPlate&roadSectionId=_roadSectionId`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/billing/monthBills/checkMonthBill?access_token=54d39cae-57d5-4219-bfc1-37ab7609490a&customerCarPlate=皖A54321&roadSectionId=1020`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": true
}
```
## 3.2 收费策略（ChargingStrategy）
### 3.1.1 save接口
- 功能描述: 新增一个收费策略，并保存进数据库
- 请求地址: `http://domain/billing/chargingStrategies?access_token=token`
- 请求动作: `POST`
- 请求示例: `http://localhost:8080/billing/chargingStrategies?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
-Body:
```
{
    "name": "肥西C级全日收费策略",
    "description": null,
    "chargingType": "time"
}
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1008,
        "name": "肥西C级全日收费策略",
        "freePeriod": null,
        "chargingType": "time",
        "freePeriodChargeable": null,
        "description": null,
        "chargingStandards": null
    }
}
```
### 3.1.2 getFee接口
- 功能描述: 计算驶出车辆此次的停车费用
- 请求地址: 
```
http://domain/billing/chargingStrategies/fee?access_token=token&
customerCarPlate=_customerCarPlate&
chargingStrategyId=_chargingStrategyId&
startTime=_startTime&
vehicleType=_vehicleType&
InParkingRoadSectionId=_InParkingRoadSectionId
```
- 请求动作: `GET`
- 请求示例: 
```
http://localhost:8080/billing/chargingStrategies/fee?
access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea&
customerCarPlate=皖A12346&
chargingStrategyId=1000&
startTime=2017-07-19 8:00:00&
vehicleType=1&
InParkingRoadSectionId=1008
```
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "fee": 11,
        "endTime": "2017-07-19 09:43:25"
    }
}
```
### 3.1.3 list接口
- 功能描述: 查找收费策略列表
- 请求地址: `http://domain/billing/chargingStrategies?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/billing/chargingStrategies?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "content": [
            {
                "name": "肥西A级全日收费策略",
                "id": 1000,
                "description": null,
                "chargingType": "time"
            },
            {
                "name": "肥西A级全日收费策略\n",
                "id": 1001,
                "description": null,
                "chargingType": "once"
            },
            {
                "name": "肥西B级全日收费策略",
                "id": 1002,
                "description": null,
                "chargingType": "time"
            },
            {
                "name": "肥西B级全日收费策略",
                "id": 1003,
                "description": null,
                "chargingType": "once"
            },
            {
                "name": "AA",
                "id": 1007,
                "description": null,
                "chargingType": null
            }
        ],
        "last": true,
        "totalElements": 5,
        "totalPages": 1,
        "number": 0,
        "size": 20,
        "sort": null,
        "first": true,
        "numberOfElements": 5
    }
}
```
### 3.1.4 get接口
- 功能描述: 根据Id查找收费策略
- 请求地址: `http://domain/billing/chargingStrategies/{id}?access_token=token`
- 请求动作: `GET`
- 请求示例: `http://localhost:8080/billing/chargingStrategies/1000?access_token=b20ba53d-0e30-4007-a8b3-ba5598fc25ea`
- 返回示例
```
{
    "status": "SUCCESS",
    "data": {
        "id": 1000,
        "name": "肥西A级全日收费策略",
        "freePeriod": 15,
        "chargingType": "time",
        "freePeriodChargeable": true,
        "description": null,
        "chargingStandards": [
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1000,
                        "interval": 30,
                        "unit": 30,
                        "unitCost": 300,
                        "sort": 1
                    },
                    {
                        "id": 1001,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 200,
                        "sort": 2
                    },
                    {
                        "id": 1002,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 100,
                        "sort": 3
                    }
                ],
                "id": 1000,
                "dateType": 1,
                "vehicleType": 1
            },
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1003,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 400,
                        "sort": 1
                    },
                    {
                        "id": 1004,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 300,
                        "sort": 2
                    },
                    {
                        "id": 1005,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 200,
                        "sort": 3
                    }
                ],
                "id": 1001,
                "dateType": 1,
                "vehicleType": 2
            },
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1006,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 400,
                        "sort": 1
                    },
                    {
                        "id": 1007,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 300,
                        "sort": 2
                    }
                ],
                "id": 1002,
                "dateType": 2,
                "vehicleType": 1
            },
            {
                "chargingStartTime": "07:30:00",
                "chargingEndTime": "19:00:00",
                "maxFee": 5000,
                "chargingRules": [
                    {
                        "id": 1008,
                        "interval": 60,
                        "unit": 30,
                        "unitCost": 500,
                        "sort": 1
                    },
                    {
                        "id": 1009,
                        "interval": 0,
                        "unit": 30,
                        "unitCost": 400,
                        "sort": 2
                    }
                ],
                "id": 1003,
                "dateType": 2,
                "vehicleType": 2
            }
        ]
    }
}
```