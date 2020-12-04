# Frequent-Itemset-Mining-Project
Apriori Algorithm
Strategies Implemented
● ​ Transaction Reduction
○ ​ It is based on the fact that a transaction that does not contain any frequent k-itemsets cannot contain any frequent (k + 1) - itemsets. Therefore, such a
transaction can be removed from further consideration. We sorted our database according to the length of the transactions, whenever
in an iteration if we are going to count the k-frequent itemsets we first remove
the transactions whose item-sets length is less than k.
○ Then from Lk we calculate Lk+1 frequent itemsets by generating candidates and
counting them in the transaction list.
○
○ ​ This way database size gets reduced for further iterations and thus a good optimisation to naive apriori algorithm.
● ​ Hash Based Technique
○ ​ When scanning each transaction in the database to generate the frequent
1-itemsets, L1 we can generate all the frequent 2-itemsets for each transaction,
hash them into the different buckets of a hash table structure, and increase the
corresponding bucket counts. A 2-itemset with a corresponding bucket count
in the hash table that is below the support threshold cannot be frequent and
thus should be removed from the candidate set.
○ ​ We iterate through all the transitions in the database and remove the 1 -
itemsets which are not frequent from each transaction . For each transaction
we then form all the 2 - ​ candidates and hash them into the table with
the help of hash function and increment their count.
○ ​ Hash Function : ​ ( ​ sum of ascii values of both items)%p ,
p - > Prime Number. Eg -> Hash(Milk,Jam) , p =7 => 5
○ ​ The ones whose bucket count greater than or equal to minSupport are a part
of frequent 2 - itemsets.Sign Dataset
Observations
● ​ Hashing and Transaction Reduction techniques produce significant
improvement in the sign dataset for low support count. Optimised algorithms
give results in almost half the time.
● ​ Hash Based approach performs almost the same as combination of
both(hidden behind green line).
● In this ​ dataset the average length of the transactions is less because, on
increasing support count transaction reduction technique behaves good and
hence some optimization happens and total items are also less because almost
same optimisation of both algorithms.Retail Dataset
Observations
● ​ Hashing and Transaction Reduction techniques combined produce significant
improvement in the Retail dataset especially at low support count optimisations
give much faster results. Naive gives result in about 35 sec and optimised
techniques gives in less than 5 seconds.
● ​ Transaction
Reduction is slower than a hash based approach.
● ​ In this dataset not many transactions get deleted until the later stages of
the algorithm. More Items are there in the dataset. Frequent Items are
distributed between various transactions. Number of unique elements is
less as compared to transactions.
