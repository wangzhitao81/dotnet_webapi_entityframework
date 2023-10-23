# dotnet_webapi_entityframework
check request header's sign,
每次请求 API 接口时，均需要提供 5 个 HTTP Request Header，具体如下：
名称	类型	说明
appkey	String	服务端分配的 appkey。
nonce	String	随机数，36字符以内
timestamp	String	时间戳，从 1970 年 1 月 1 日 0 点 0 分 0 秒开始到现在的毫秒数。
sign	String	数据签名。
Content-Type	String	application/json
sign (数据签名)计算方法：将系统分配的 appkey、nonce (随机数)、timestamp (时间戳)三个字符串按先后顺序拼接成一个字符串并进行 MD5加密（小写）。
如果调用的数据签名验证失败，接口调用会返回错误信息。
