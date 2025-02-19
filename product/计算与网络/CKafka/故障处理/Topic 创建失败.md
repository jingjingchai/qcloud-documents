**问题概述**

Topic 创建失败。

**可能原因**

1. 已创建的所有Topic的分区数之和达到实例规格的分区数上限。

   ![](https://main.qcloudimg.com/raw/94904051a2fba64bb4d191b50abbf703.jpg)

2. Topic 删除是异步操作，下发删除指令后，系统会异步的删除该 Topic 的元数据。若在此期间创建同名 Topic，系统会提示 Topic 已经存在。

3. Topic 已经存在集群当中，创建重名的 Topic 就会提示 Topic 已经存在。



**解决方法**

1. 如果已创建的所有 Topic 的分区数之和达到实例规格的分区数上限，建议对Kafka实例扩容，或者删除不需要的Topic。
2. Topic 删除是异步操作，下发删除指令后，系统会异步的删除该 Topic 的元数据。若在此期间创建同名 Topic，系统会提示 Topic 已经存在，届时请您稍后重试。这里需要等待1分钟左右，再进行重建操作。
3. 如果 Topic 已经存在集群当中，建议重新设置 Topic 名称。
