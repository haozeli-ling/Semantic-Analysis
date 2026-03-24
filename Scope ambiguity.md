# Scope ambiguity 


In semantics, scope ambiguity is resolved by applying Quantifier Raising in different ways. 

- Essentially, Quantifier Raising determines the structural position at which a quantifier is interpreted.
- In sentences with multiple quantifiers, different derivations may impose different evaluation orders. These distinct configurations yield different truth conditions.

1. A student watched every movie.

> [!IMPORTANT]
> Derivation of the inverse scope reading: <br>
> 'Raising' the object quantifier to the edge of the whole sentence. 

```
F(every movie [1 a student watched pro_1])
= F('every movie')(F('1 a student watched pro_1'))
= F('every movie')(lambda x : F('a student')(lambda y : watched_f(y, x)))
= F('every movie')( lambda x : |{y : student_f(y) = 1} & {y: watched_f(y,x) = 1}| != 0)
= {x : movie_f(x) = 1} <= {x : [|{y : student_f(y) = 1} & {y: watched_f(y,x) = 1}| != 0] = 1}
```
