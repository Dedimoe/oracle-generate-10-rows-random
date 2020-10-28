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
        U          V
---------- ----------
    178749         10 
    244588          7 
    407905          3 
    418829          2 
    466241          9 
    500790          8 
    649773          4 
    653990          1 
    688023          5 
    700457          6 

 10 rows selected 
```

order by v:
```
         U          V
---------- ----------
    210045          1 
    422547          2 
    345348          3 
    523620          4 
    471339          5 
    198962          6 
    771305          7 
    999466          8 
    545928          9 
    913993         10 

 10 rows selected 
 ```
 
