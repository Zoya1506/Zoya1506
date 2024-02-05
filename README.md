1. What is the average size of block data in bytes. 
```SQL
SELECT AVG(size) AS `average_size` FROM `bigquery-public-data.crypto_litecoin.blocks`
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/131328d0-1c82-4f04-8498-5295569a2622)

2. What is the total weight of the blocks in the data?
```SQL
SELECT sum(weight) AS `Total weight` FROM `bigquery-public-data.crypto_litecoin.blocks` 
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/8a469c33-4487-4205-9a8a-fbe564dfcedd)

3. Find out the total weight of blocks where the number is less than 10000.
```SQL
  SELECT sum(weight) AS `Total weight` FROM `bigquery-public-data.crypto_litecoin.blocks` 
  Where number < 10000
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/538e4c9c-4912-49d1-9b01-571abde61835)

4.Find out the top 5 months where average transaction count is highest. 
```SQL
SELECT timestamp_month, AVG(transaction_count) AS `average_transaction_count`
FROM `bigquery-public-data.crypto_litecoin.blocks`
GROUP BY timestamp_month 
Order by 2 DESC
Limit 5
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/3c5d5865-637d-4c13-9941-2a60b822cfdb)

5.Find out the average size of blocks of different months whose number is above 10000.
```
SELECT timestamp_month, AVG(size) AS `Average Size`
FROM `bigquery-public-data.crypto_litecoin.blocks`
Where number > 10000
GROUP BY timestamp_month 
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/6927eb75-32d6-4fe3-a1c2-416aefcb7368)

6. Find out the minimum and maximum size of 10 blocks with least average size grouped timestamp.
```SQL
SELECT timestamp_month, min(size) AS `Minimum Size`, max(size) as `Maximum size`, avg(size) as `Average size`
FROM `bigquery-public-data.crypto_litecoin.blocks`
GROUP BY timestamp_month 
Order by 4 
LIMIT 10
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/54baeaca-9e76-413d-b8d7-ef8e35936801)

7. Find out the average size and total transaction count for different versions.
```SQL
SELECT version, avg(size) as `Average size`, sum(transaction_count) as `Total transaction_count`
FROM `bigquery-public-data.crypto_litecoin.blocks`
GROUP BY 1 
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/d68affa2-b587-4c45-9b1e-7599a3b68b38)

8. Find out the total weight of blocks for each month in 2023.
```SQL
 SELECT timestamp_month, SUM(weight) AS `total_weight`
FROM `bigquery-public-data.crypto_litecoin.blocks`
WHERE timestamp_month BETWEEN '2023-01-01' AND '2023-12-31'
GROUP BY 1
```
![image](https://github.com/Zoya1506/Zoya1506/assets/159045446/ff2b17b9-300a-4b49-91d5-b066f23ba8a4)

9. 

