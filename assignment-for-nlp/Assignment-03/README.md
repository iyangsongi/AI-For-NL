
## Assignments for Week-03

### 1. Re-code the titanic machine learning

###### 1. Random Choose Method to get optimal *k* and *b*
###### 2.Supervised Direction to get optimal *k* and *b*
###### 3.Gradient Descent to get optimal *k* and *b*  
详见titanic-ml.ipynb

## 2. Answer following questions:


###### 1. Why we need machine learning methods instead of creating a complicated formula?


Ans:相比于固定公式的算法，在实际生活中，数据具有多样性和复杂性。固定公式的方法无法满足各类公式的需求，而机器学习方法，能够针对数据进行分析帮助建立模型，并且面对新的数据能够对模型进行优化改进。

###### 2.  Wha't's the disadvantages of `the 1st Random Choosen` methods in our course? 

Ans:他对最优解数据具有猜测性，在有限的操作次数内，一般无法得到最优解或十分趋近最优解。同时，针对习题中的k,b的取值范围也是假设的数据，最有解可能超出此范围。

###### 3. Is the `2nd method supervised direction` better than 1st one?  What's the disadvantages of `the 2nd supversied directin` method? 

Ans:相对于第一种方法，它具有方向性

###### 4. Why do we use `Derivative / Gredient` to fit a target function? 

Ans:我们要求得loss函数最低点，沿着梯度的反向能够更快的趋近于最低点。

###### 5. In the words 'Gredient Descent', what's the `Gredient` and what's the `Descent`?

Ans:梯度为函数在某一点出，该点沿着某一方向会取得变化的最大值，这个方向即为梯度。下降表示减少，在该点梯度的负方向下降最大。

###### 6. What's the advantages of `the 3rd gradient descent method` compared to the previous methods?

Ans:首先，梯度下降具有方向性，沿着一个方向逐步减少，其次该方向为减少最大的方向,能够最快找到最优解。

###### 7. Using the simple words to describe: What's the machine leanring.

Ans:能够帮助人类解决复杂甚至人类无法实现的工作，从而减轻人类工作负担的一种工具。

## 3. Finish the search problem

Please using the search policy to implement an agent. This agent receives two input, one is @param start station and the other is @param destination. Your agent should give the optimal route based on Beijing Subway system. 

详见search_subway.ipynb

#### Dataflow: 

##### 1.	Get data from web page.

> a.	Get web page source from: https://baike.baidu.com/item/%E5%8C%97%E4%BA%AC%E5%9C%B0%E9%93%81/408485

> b.	You may need @package requests page to get the response via url

> c.	You may need save the page source to file system.

> d.	The target of this step is get station information of all the subway lines;

> e.	You may need install @package beautiful soup  to get the url information, or just use > Regular Expression to get the url.  Our recommendation is that using the Regular Expression and BeautiflSoup both. 

> f.	You may need BFS to get all the related page url from one url. 
Question: Why do we use BFS to traverse web page (or someone said, build a web spider)?  Can DFS do this job? which is better? 

##### 2.	Preprocessing data from page source.

> a.	Based on the page source gotten from url. You may need some more preprocessing of the page. 

> b.	the Regular Expression you may need to process the text information.

> c.	You may need @package networkx, @package matplotlib to visualize data. 

> d.	You should build a dictionary or graph which could represent the connection information of Beijing subway routes. 

> e.	You may need the defaultdict, set data structures to implement this procedure. 

##### 3. Build the search agent

> a.	Build the search agent based on the graph we build.

> b.	As much as you can to use the already implemented search agent. You just need to define the is_goal, get_successor, strategy three functions. 


##### 4.	Create different policies for transfer system.

> a.	Define different policies for transfer system. 

> b.	Such as Shortest Path Priority（路程最短优先）, Minimum Transfer Priority(最少换乘优先), Comprehensive Priority(综合优先)

> c.	Implement Continuous transfer. Based on the Agent you implemented, please add this feature: Besides the @param start and @param destination two stations, add some more stations, we called @param by_way, it means, our path should from the start and end, but also include the  @param by_way stations. 

e.g 
```
1. Input:  start=A,  destination=B, by_way=[C] 
    Output: [A, … .., C, …. B]
2. Input: start=A, destination=B, by_way=[C, D, E]
    Output: [A … C … E … D … B]  
    # based on your policy, the E station could be reached firstly. 
![image.png](attachment:image.png)
```

##### 5.	Test your result with commercial applications. 

将你的结果和高德地图或者百度地图进行比较，如果有不同，请分析原因

