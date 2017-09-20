# Travelling Saleman Problem Solution By Modified Algo

## T.S.P
> TSP problem is one of the most famous hard combinatorial optimization problems. It belongs to the class of NP-hard optimization problems.
> This means that no polynomial time algorithm is known to guarantee its global optimal solution. Consider a salesman who has to visit
> cities. The TSP problem consists of finding the shortest tour through all the cities such that no city is visited twice and the 
> salesmanreturns back to the starting city at the end of the tour.

'f' is the cost function and 'd' is the distance between two nodes  and p(i) is an array of paths by salesman
```
f = Σd(p(i))

delta = f1 -f2
```

## S.A (Simulated Annealing)
>SA algorithm is commonly said to be the oldest among the metaheuristics and surely one of the few algorithms that have explicit strategies
> to avoid local minima. The origins of SA are in statistical mechanics and it was first presented for combinatorial optimization problems.
> The fundamental idea is to accept moves resulting in solutions of worse quality than the current solution in order to escape from local 
> minima. The probability of accepting such a move is decreased during the search through parameter temperature

Here 'p' is the probability of the move and 'T' is our temperature. 

```
p = 1/(1 + e^(delta(f)/T))
```


## Modified S.A
we used the [Greedy hybrid operator](http://www.inderscience.com/info/inarticle.php?artid=71818) to move to the neighbouring node. We first choose randomly to index 'i' & 'j' and operator three operations viz inverse insert & swap and calculated the 'p' for each possible path and if it was greater then randomly genrated probability 'r' we moved forward else we continued.

1. *Inverse* operator : It reverses the sub-path from path from indexes 'i' and 'j'.
2. *Insert* operator : It cycles down the sub-path from indexes 'i' and 'j'. 
3. *swap* operator : It swapes the path[i] and path[j] elements.

## Temperator Simulation.
we used the [classical geometric cooling schedule](https://view.officeapps.live.com/op/view.aspx?src=http://www.cs.nott.ac.uk/~pszgxk/aim/notes/simulatedannealing.doc) for simulated temperature cooling. 

## Instruction

1. Clone the above repo by 
	```
	 $ git clone https://github.com/abhijeet2096/tsp_sa
	```
2. Spawn terminal in cloned folder.
3. Compile using `$ make` .
4. Run above program as 
	```
	 $ ./tsp < /TestCases/euc_100
	```
5. Check stdout for output !

## Results
Results are displayed below in table.

| TestCase      | Distance      | 
| ------------- |:-------------:| 
| euc_100       | 1522.217651   | 
| euc_250       | 2516.678467   | 
| euc_500       | 3554.416260   |
| noneuc_100    | 5216.49072    | 
| noneuc_250    | 12799.088867  | 
| noneuc_500    | 25437.474609  | 

## About
The Assignment's aim was to solve Travelling salesman problem. This Assignement was under Prof. [Deepak Khemani](https://www.iitm.ac.in/info/fac/khemani).

## Contributors

[Abhijeet sharma](http://students.iitmandi.ac.in/~abhijeet_sharma)
1. Github: http://github.com/abhijeet2096
2. Email: sharma.abhijeet2096@gmail.com
3. Mobile: +91-8629015433

[Swapnil Sharma](http://students.iitmandi.ac.in/~s_sharma)
1. Github: http://github.com/swapsha96
2. Email: swap.sha96@gmail.com
3. Mobile: +91-8629015435

## References

1. https://www.youtube.com/watch?v=dg5zUxdAE_E&list=PLbMVogVj5nJQu5qwm-HmJgjmeGhsErvXD&index=14
2. https://www.hindawi.com/journals/cin/2016/1712630/#B25
