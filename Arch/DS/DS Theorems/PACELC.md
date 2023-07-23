#devOps #architecture #database 

extension of the CAP Theorem. (PAC + ELC)
if there is **Partition**, trade off between:
- **Availability**
- **Consistency**
**E**lse (if no partition):
- **Latency**
- **Consistency**

### If No Partition
- [ ] System must replicate data. 
- [ ] Can Priority latency and compromise consistency
- [ ] or Can prioritise consistency with slower latency.

### Database Category
#### PA/EL
- [ ] if P, give up C for A. under normal operation give up C for L
- [ ] DynamoDB, Casssandra, Rik and cosmos DB

#### PC/EC
- [ ] Always choose C, giving up A and L
- [ ] BigTable, HBase, Mysql cluster

#### PA/EC
- [ ] if P, choose A over C. else choose C over L.
- [ ] MongoDB