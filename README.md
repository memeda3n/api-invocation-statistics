# api-invocation-statistics
api下线工具，统计api是否有用户使用，提供邮件通知方式

1、api调用监控方案
（1）定义注解@ApiStatistics
        作用：标记接口为待下线，利用切面统计接口调用情况
（2）定义切面 ApiStatisticsAspectJ.class
       统计被@ApiStatistics注解标记的api调用情况，调用的数据保存在redis中
（3）定时任务 Task
       同步redis中api调用信息，将调用信息发送email到指定人。

2、从Excel中统计接口api调用情况

3、参考流程 ：
（1）确定需下线接口
（2）通知调用方对应下线接口
（3）在项目中将接口标记为待下线，开始监控
（4）监控一段时间
（5）在email中的Excel中，查看接口调用情况
（6）下线未使用接口
