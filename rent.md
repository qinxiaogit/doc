####获取柜子详情列表:
- API：`/panel/club/1025/rent-cabinet/get-cabinet-details`
	1. status: 0-等待借出，1已借出(未逾期),2已借出(逾期) ,3禁用
	2. number:柜子编号
	3. backTime：归还时间信息
####出租柜子
- API:`/panel/club/1025/rent-cabinet/rent-cabinet-to-User`
- parameter：
	1. vipId:会员Id
	2. areaId区域编号
	3. cabinetId:柜子编号
	4. rentStartTime:租借开始时间
	5. rentEndTime:租借结束时间
	6. rentRemark：租借备注
	7. rentActualMoney：租借实收金额
####归还柜子
- API:`/panel/club/1025/rent-cabinet/user-back-cabinet`
- parameter：
	1. rentId:租借Id
	2. backRemark:归还备注
####禁用柜子
- API:`/panel/club/1025/rent-cabinet/enable-cabinet`
- parameter：
	1. areaId:区域编号
	2. cabinetNum：柜子编号
	3. enableReason：禁用原因
####启用柜子
- API:`/panel/club/1025/rent-cabinet/restart-cabinet`
- parameter：
	1. areaId:区域编号
	2. cabinetNum：柜子编号
	3. restartReason：禁用原因