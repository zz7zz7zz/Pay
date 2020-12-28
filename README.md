# Pay


一、国外支付SDK：

    一、谷歌支付

    二、华为支付


二、设计思路（基于策略的逻辑设计SDK）：
    
    App_SDK_Pay：</br>

        App_SDK_Pay_GOOGLE

        App_SDK_Pay_Huawei
    
        App_SDK_Pay_ZFB
    
        App_SDK_Pay_TX

       
 具体实现如下：           
    
    Pay_Base: 
        定义接口，定义基本的数据类型
 
        Pay_Impl_A: 

        Pay_Impl_B: 

        Pay_Impl_C: 
    
            实现具体支付(也即上面的App_SDK_Pay_GOOGLE...)-->依赖Pay_Base


    Pay_Main: 调用逻辑 
        -->根据配置动态依赖Pay_Impl_A，Pay_Impl_B，Pay_Impl_C
        -->依赖Pay_Base


三、支付流程

客户端流程：
    
    方式一、
    1.创建订单
    2.支付
    3.上报给后端,后端去验证
    4.客户端消耗
    
    方式二、
    1.创建订单
    2.支付
    3.客户端消耗
    4.上报给后端,后端去验证（失败后进行重传）
    
    
服务器流程：
    
    1.提供商品列表 skulist
    2.提供配置接口，显示哪几个第三方支付可用  getPayConfig
    3.提供创建订单接口 create
    4.提供验证接口  verify
    5.提供上报结果接口 report

    6.提供订单信息接口（单用户、对多用户、所有用户）  getOrderStatusById getOrderStatusAll
    7.提供流水信息  getCoinFlowById
    8.提供账户信息(金币，会员信息)  getUserWalletById

    21.提供各类统计，以数据、图表形式
    22.与各个支付平台后端的对接，有几个平台，一般需要提供几个paycallback接口
    
    30.server与客户端的通知交互(即时通知最佳）
    
 


