####会员搜索接口新增数据
	/app/club/membership/receptionist/member-search
	ringList:
			expiredCount：逾期手环数量
			isSign:今日是否签到
			notExpiredCount:未逾期手环数量
			ringNum:最新租借手号(数字)
####会员签到签退接口
	/app/club/membership/receptionist/replace-sign
	参数:
		status： (in:签到,out签退)
		vipUserId : 会员Id
		ringNum:手环号(字符串)

####会员归还手环接口
	/app/club/membership/receptionist/back-ring
	参数:
		vipUserId : 会员Id
		ringNum:手环号(字符串)