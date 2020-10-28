# oracle-generate-10-rows-random
Oracle generate random number

```
select u,v from (
SELECT round(DBMS_RANDOM.value(100000,999999)) u, v FROM dual 
MODEL DIMENSION BY (0 AS R)       
MEASURES (0 AS V)       
RULES ITERATE (10) (V[ITERATION_NUMBER] = ITERATION_NUMBER+1) ORDER BY 1
) order by u
```
sample output:
```
```
