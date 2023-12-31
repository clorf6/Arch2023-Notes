### Error

* fault 是 error 的原因，当潜在的 error 呈现出问题就会导致 failure 发生，而 failure 又会导致一个或多个潜在的 error。

* dependability 指永久可靠，reliability 要弱一些，availability 指存在问题但可用，recoverability 指出故障后可恢复。
* fault-tolerance（容错）指防止 errors 变成 failures，disaster-tolerance（容灾）指防止一个站点的 error 导致整个服务的 failure。

### Queue theory

* Little's Law: $L _{q}=rT _{q}$，其中 $L _{q}$ 为队列长度，$r$ 为平均顾客到达的速度，$T _{q}$ 为顾客平均等待时间。
* $T _{sys}=T _{q}+T _{ser}$，其中 $T _{sys}$ 为顾客平均在整个系统中的时间，$T _{ser}$ 为顾客平均服务时间。
* $L _{sys}=rT _{sys}$，$L _{sys}$ 即为系统的容量（能容纳多少个任务）。