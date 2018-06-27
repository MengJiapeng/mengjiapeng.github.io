## Spring Security学习笔记

### 前言
本篇文章是我学习Spring Security时的笔记，所有内容均参考自[Spring官网](https://spring.io)的[这篇文章](https://spring.io/guides/topicals/spring-security-architecture/)，鉴于我的英文水平有限，大家在阅读本篇文章时若觉得有逻辑不通的地方，可以参考原文。

保证应用安全主要要解决两件事情：Authentication（你是谁）和Access control(or Authorization)（你被允许做什么）。

### Authentication
Authentication最主要的接口是`AuthenticationManager`，这个接口只有一个方法:
<pre>
public interface AuthenticationManager {
    Authentication authenticate(Authentication authentication) throws AuthenticationException;
}
</pre>
在`authenticate`方法中可能会出现以下3种情况:
1. 若认证成功，返回一个`Authentication`对象（`authenticated = true`）
2. 若认证失败，抛出`AuthenticationException`
3. 若无法决定，返回`null`


