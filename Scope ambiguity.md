# 15. Scope ambiguity 


In semantics, scope ambiguity is resolved by applying Quantifier Raising in different ways. 

- Essentially, Quantifier Raising determines the structural position at which a quantifier is interpreted.
- In sentences with multiple quantifiers, different derivations may impose different evaluation orders. These distinct configurations yield different truth conditions.

1. A student watched every movie.

> [!IMPORTANT]
> Derivation of the inverse scope reading: <br>
> 'Raise' the object quantifier to the edge of the whole sentence. 

```
F(every movie [1 a student watched pro_1])
= F('every movie')(F('1 a student watched pro_1'))
= F('every movie')(lambda x : F('a student')(lambda y : watched_f(y, x)))
= F('every movie')( lambda x : |{y : student_f(y) = 1} & {y: watched_f(y,x) = 1}| != 0)
= {x : movie_f(x) = 1} <= {x : [|{y : student_f(y) = 1} & {y: watched_f(y,x) = 1}| != 0] = 1}
```

> [!IMPORTANT]
> Derivation of the surface scope reading: <br>
> 'Raise' the object quantifier to the edge of the whole sentence and <br>
> Continue to raise the subject quantifier outside the scope of the object quantifier. 

```
F(a student [2 every movie [1 pro_2 watched pro_1]])
= F('a student')(2 every movie [1 pro_2 watched pro_1])
= F('a student')(2 F('every movie')([1 pro_2 watched pro_1]))
= F('a student')(lambda y : F('every movie')(lambda x : watched_f(y,x)))
= F('a student')(lambda y : {x : movie_f(x) = 1} <= {x: watched_f(y,x) = 1})
= |{y : student_f(y) = 1} & {y : [{x : movie_f(x) = 1} <= {x: watched_f(y,x) = 1}] = 1}| != 0
```

> **Exercise** <br>
> Please compute the scope intepretations for the following sentences: <br>
> (a) No student watched every movie. <br>
> (b) Three students watched most movies.
