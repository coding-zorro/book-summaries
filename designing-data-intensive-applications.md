# Designing Data Intensive Applications

## Partitioning
- Breaking up data and storing them into different nodes is partitioning. Its also referred as sharding.
- Scalability is the main reason for partitioning.
  - A large dataset can be distributed across many nodes.
  - Query load can be distributed across many processors.
- Challenges in partitioning
  - *skew*: Some partitions have more data or queries than the others.
  - *hotspot*: A partition with a disproportionately high load.

### Partitioning Techniques
#### Key Range

- Assign a continuous range of keys to one partition. 
- If you know the boundaries between the ranges, you can easily determine which partition contains a given key.
- If you also know which partition is assigned to which node, then you can make your request directly to the appropriate node.
- Downside: Certain access patterns can lead to hotspots.
