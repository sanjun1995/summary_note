#### 场景：
 * 某节点磁盘需要维修，故下线某集群的一个数据节点
 
#### 步骤一
 * 迁移分片，排除该节点ip
```
curl -XPUT http://10.10.1.110:9200/_cluster/settings?pretty -d'{"transient":{"cluster.routing.allocation.exclude._ip":"10.10.1.111"}}'
```

#### 步骤二
 * 迁移完成后，kill掉该进程
 * 待节点磁盘维修完成，重新让节点回到集群
 * 解除“排除”

```
curl -XPUT http://10.10.1.110:9200/_cluster/settings?pretty -d'{"transient":{"cluster.routing.allocation.exclude._ip":"null"}}'
```

#### 注意点
 * null需要看es版本，可能是"null"。


#### 欢迎关注公众号：JavaWeb学徒（JavaWebLearner）
