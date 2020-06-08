# mpay.js
- [使用步骤][0]
- [安装使用][1]
- [api][2]

# 使用步骤
  1. 引入`mpay.js`
  2. 如若想要授权登录，配置app_key然后调用mpay.auth
  ```js
    mpay.config({
      app_key: '', // 必须
    })
  ```
  3. 在`mpay.ready`里执行其他交互操作
  ```js
    mpay.ready(function () {
      // 调用其他接口
    })
  ```
  
# 安装使用
  - mpay.js线上地址[(http://www.abc.com/mpay.js)](http://www.abcdefg.com/mpay.js?_blank)
  - mpay.js支持`amd`,`commonjs`规范

## 配置
  使用`mpay.config`
  ```js
    mpay.config({
      app_key: '', //app_key
    })
  ```
  配置之后的api需要在`mpay.ready`里运行
  ```js
    mpay.ready(function () {
      // 调用其他接口
    })
  ```
## 授权
  1. 获取code
  2. 根据获取的code和app_key去取得`access_token`
  3. 根据access_token获得mpay用户的相关信息
  
  - mpay.auth
  ```js
    mpay.auth({
      success: function (res) {
        var data = res.code // 返回的code
      },
      fail: function (res) {
        var msg = res.msg // 返回错误信息
        var type = res.type // 错误类型
      }
    })
  ```
  - 获取access_token
  
  url:  
  
          /appauth/pbauthcode.do
  
  请求参数
  
  ```js
    {
        "app_key":"ZROXL6DLtFBHEsIJuutl*%dByyTT@EnL", // app_key
        "code":"423699316729843712" // 授权返回的授权码
    }
  ```
  
  返回
  
  
  
## 支付

### 下单

  `mpay.pay`
  
  ```js
    mpay.pay({
      orderId: '238923237', //订单id
      // 支付成功
      success: function (res) {
        var orderId = res.orderId // 返回订单id
      },
      // 支付失败
      fail: function (res) {
        var msg = res.msg  //错误信息
        var type = res.type // 错误类型
      }
    })
  ```

  |name|default|desc|
  |:---|:---|:---|
  |good|name|desc|


?> info

!> warning

> custom


  
[0]: #使用步骤
[1]: #安装使用
[2]: #api