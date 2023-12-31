### MESI

![image-20240101015457854](https://clorf-imagehost.oss-cn-shanghai.aliyuncs.com/2024/01/image-20240101015457854-1a2984.png)

在 MSI 的基础上，将 Shared 状态细分为了 Exclusive（独占，即只有自己含有数据）与 Shared（共享，即有多个含有数据）状态。

因此，当 Exclusive 被修改时，只需把状态改为 Modified 即可，不需要给其他发 Invalid 信号。

### Berkeley

多了 Owned 状态，保证了对数据的唯一更改权。其中 Owned 状态要求一定存在其他 Shared 也拥有数据备份，这时后 Shared 状态不一定保证 clean，即 Shared 状态可能也和主存不一致。

具体而言，假如有多个 Shared 状态，此时一个核想要获得这个数据，就会向总线发 Read 请求，此时多个 Shared 中只有 Owned 状态能够提供数据。同时，Owned 状态被写时也能够直接向其他 Shared 状态提供新的数据。