HMFJSONResponseSerializerWithData
=================================

A subclass of AFJSONResponseSerializer that includes the statusCode and body of the HTTP response.

当服务器返回statusCode为500时，AFNetworking会处理为网络请求错误，也得不到相应的response信息。而有一种服务器API的风格会将code小于0的情况返回500。将这两个文件项目中添加进项目中，初始化responseSerializer时调用下面两行代码即可成功获取：
``` objective-c
AFHTTPSessionManager *sessionMgr = [AFHTTPSessionManager manager];
sessionMgr.responseSerializer = [HMFJSONResponseSerializerWithData serializer];
```
