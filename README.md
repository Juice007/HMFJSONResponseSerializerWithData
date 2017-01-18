HMFJSONResponseSerializerWithData
=================================

A subclass of AFJSONResponseSerializer that includes the statusCode and body of the HTTP response.

当服务器返回statusCode为500时，AFNetworking会处理为网络请求错误，也得不到相应的response信息。而有一种服务器API的风格会将code小于0的情况返回500。添加下面两行代码即可获取
```
AFHTTPSessionManager *sessionMgr = [AFHTTPSessionManager manager];
sessionMgr.responseSerializer = [HMFJSONResponseSerializerWithData serializer];
```
