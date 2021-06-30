Evictions occur when memory is over filled or greater than maxmemory setting in the cache, resulting into the engine to select keys to evict in order to manage its memory. The keys that are chosen are based on the eviction policy that is selected.

<p>

By default, Amazon ElastiCache for Redis sets the volatile-lru eviction policy to your Redis cluster. This policy selects the least recently used keys that have an expiration (TTL) value set. Other eviction policies are available can be applied as configurable maxmemory-policy parameter. Eviction policies can be summarized as the following:

```
allkeys-lfu: The cache evicts the least frequently used (LFU) keys regardless of TTL set
allkeys-lru: The cache evicts the least recently used (LRU) regardless of TTL set
volatile-lfu: The cache evicts the least frequently used (LFU) keys from those that have a TTL set
volatile-lru: The cache evicts the least recently used (LRU) from those that have a TTL set
volatile-ttl: The cache evicts the keys with shortest TTL set
volatile-random: The cache randomly evicts keys with a TTL set
allkeys-random: The cache randomly evicts keys regardless of TTL set
no-eviction: The cache doesn’t evict keys at all. This blocks future writes until memory frees up.
```

A good strategy in selecting an appropriate eviction policy is to consider the data stored in your cluster and the outcome of keys being evicted.
Generally, LRU based policies are more common for basic caching use-cases, but depending on your objectives, you may want to leverage a TTL or Random based eviction policy if that better suits your requirements.

<p>

Also, if you are experiencing evictions with your cluster, it is usually a sign that you need to scale up (use a node that has a larger memory footprint) or scale out (add additional nodes to the cluster) in order to accommodate the additional data. An exception to this rule is if you are purposefully relying on the cache engine to manage your keys by means of eviction, also referred to an LRU cache.