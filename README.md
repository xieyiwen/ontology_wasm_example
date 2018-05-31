# ontology_wasm_example
ontology_wasm_example   
move to :github.com/xieyiwen/ontology-wasm/example


### how to generator .wasm file

> link: https://wasdk.github.io/WasmFiddle/

### 使用注意事项
###### 1.ontology_wasm注册的一些方法需要序列化
原因：在读取是，会根据序列化值的第一个来判断后面的值的类型

###### 2.操作内存
根据内存偏移量来操作，存储需要分为存储基本类型和结构体
`engine.GetVM().SetMemory(string(res))`
`engine.GetVM().SetStructMemory(struct)`

###### 3.获取方法的入参
通过`engine.GetVM().GetEnvCall().GetParams()`获取，数组中的值为地址指针，如果要获取参数的值，
可以通过`engine.GetMemory().GetPointerMemory(params[0])`来获取


