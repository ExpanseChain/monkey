# monkey
模拟矿工行为



| 确认方式 | 代表 | 说明 | 攻击 | 优势 | 劣势 |
| -------- | --- | --- | --- | -------- | -------- |
| POW | 比特币、以太坊 | 1. 每个块指定难度，完成难度目标则算是承认的块。 <br>2. 跟随最长的链。<br>3. 下一个块的难度有前面块确定。 | 分叉攻击，需要算出比正常链更长的链 | 无预置条件，按算力分配，直接挖矿即可 | 算力竞赛，消耗能源 |
| POS | 以太坊Casper | 1. 质押币成为验证者<br>2. 随机一部分人为提议者，其他验证者押注<br>3. 一旦产生终块(2/3验证者押注)则奖励 | 若能说服1/3人放弃质押币，则配合另外1/3也可以撤销终块并生成新的终块 | 终块大概率是确定的，比POW方式只是概率性确定终块好一些 | 随机数？ |
| POS | ADA共识算法Ouroboros拜占庭式 | 1. Genisis Data协商出随机数，按随机数选出下个epoch的出块顺序<br>2. 每个被选中的人按顺序接连出块 | 选中了不出块，或者合伙新开另一个epoch? | pos算法优势 | 也许我没看论文，但是感觉不会那么完美 |
| POS POW |  | 1. 按质押顺序出块，限制个数<br>2. 未检测到出块则允许POW方式出块，并跳过当前出块者<br>3. 实施POS块奖励，最后一个POW块获得奖励机制 | 即使检测到出块也用pow出块进行覆盖 | 有pos优势，遇到不能解决的时候就转pow解决问题 | 终局性不太好 |
| POS |  | 1. 按质押顺序出块，限制个数<br>2. 遇到没有的块，跳过即可，奖励上块越多奖励越多 | 故意分叉区块 |  | 终局性不好 |

难以接受拜占庭式，因为面对区块链这样一种以去中心化为信仰的系统， 任何协商式都是扯后腿

对于POS几乎有特别大量(预计有百万千万)参与者来说，协商是灾难



目前最有希望的是，每个发布块的人，都添加一部分信息，然后利用这部分信息可以选出下一个出块者，如果能达成这个目标，POS还是极有可能实现的

目前没有完美的共识方式，我可以接受的是，POW，同时，对POS+POW抱有希望，对于完全的POS我认为现在的技术达不到要求，我暂时没有精力去研究这方面内容，，我想设计的区块链，还是先采取POW和POS+POW方式。
