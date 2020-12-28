# Pay


国外：

    一、谷歌支付

    二、华为支付

基于策略的逻辑设计SDK
App_SDK_Pay
            App_SDK_Pay_GOOGLE
            App_SDK_Pay_Huawei
            App_SDK_Pay_ZFB
            App_SDK_Pay_TX
            
            
       
            
Pay_Base: 
    定义接口，定义基本的数据类型
 
 
Pay_Impl_A: 

Pay_Impl_B: 

Pay_Impl_C: 
    实现具体支付(也即上面的App_SDK_Pay_GOOGLE...)-->依赖Pay_Base


Pay_Main: 调用逻辑 
    -->根据配置动态依赖Pay_Impl_A，Pay_Impl_B，Pay_Impl_C
    -->依赖Pay_Base





