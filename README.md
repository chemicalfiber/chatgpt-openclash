# Chaptgpt分流规则

为chatGPT单独创建了一份openclash分流规则选择器

基础规则：ACL4SSR_Online_Full 全分组重度用户使用(与Github同步)  致谢：ACL4SSR

使用方法(到openclash配置文件处更新订阅链接)

    http://你的subconverter后端地址/sub?target=clash&new_name=true&url=你的订阅链接（URL编码）&config=https%3A%2F%2Fraw.githubusercontent.com%2Fchemicalfiber%2Fchatgpt-openclash%2Fmain%2FFull.ini

> 为了你的节点安全,请尽可能使用自建subconverter转换后端服务,不要依赖第三方subconverter
    
控制面板中，chatGPT可以进行单独的节点选择

如果更新规则后，仍提示地区不可用，请清除浏览器数据


如果发现新的域名,请提交Issues.


# 注意事项
1. fake-ip模式存在解析异常,目前未查明原因，请使用Redir-Host 兼容 模式

2. chatgpt 的网站启用了 http3 ，基于 quic ，基于 udp 如果出现还不能指定节点的情况，请开启UDP 代理，就算开启了 UDP 代理，因为 V2RAY 不支持 http3 的域名嗅探，所以基于域名的路由规则就失效了。不要全局，要不就只能基于 geoip 来。当然，最简单的办法还是把浏览器的 http3 支持给关了：

```csharp
    chrome://flags/#enable-quic
    edge://flags/#enable-quic
```
    
降级成 http1/2 就能让域名路由规则生效了。
