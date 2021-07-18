---
prerequisites:
  - operation
---

# Algebraic structure

::::definition[Algebraic structure]
An algebraic structure is a tuple $(A_1, \ldots, A_n, *_1, \ldots, *_m)$ where $A_1, \ldots, A_n$ are sets and $*_1, \ldots, *_m$ are [binary operations](binary-operation).

:::remark[Standard abuse of notation]
If $S = (A_1, \ldots, A_n, *_1, \ldots, *_m)$ is an algebraic structure, then we write $x \in S$ to denote $x \in A_1$.
:::
::::

:::definition[Abelian]
An algebraic structure $(A, *)$ is *abelian* or *commutative* if $*$ is commutative.
:::

:::definition[Homomorphism]
A _homomorphism_ between two algebraic structures is a map between the algebraic structures that preserves the structure.
:::

:::definition[Isomorphism]
An _isomorphism_ is a [homomorphism](#homomorphism) whose [inverse](inverse-function) is a [homomorphism](#homomorphism).
:::

## Overview of algebraic structures

[Here](https://en.wikipedia.org/wiki/Template:Group-like_structures) is a table showing an overview of algebraic structures. Below we show code for implementing the group axioms for finite groups.

## Code example

```julia
# In the following we let:
# - s be short for set, acting as the domain
# - op or * be a binary operator on s
# - e be an identity for *
# - i be the inverse for *

function hasclosure(s, *)
    for x ∈ s, y ∈ s
        if x * y ∉ s
            println("closure does not hold because $(x) * $(y) = $(x * y) is not in the domain")
            return false
        end
    end
    return true
end

ismagma = hasclosure

function isinversefunction(s, *, i, e)
    for x ∈ s
        if x * i(x) != e || i(x) * x != e
            println("inverse does not hold because $(x) * ($(x))^{-1} ≠ e = $(e)")
            return false
        end
    end
    return true
end

function isassociative(s, *)
    for a ∈ s, b ∈ s, c ∈ s
        if (a * b) * c != a * (b * c)
            println("associativity does not hold because ($(a) * $(b)) * $(c) ≠ $(a) * ($(b) * $(c)))")
            return false
        end
    end
    return true
end

function isidentity(s, *, e)
    for a ∈ s
        if e * a ≠ a
            println("identity does not hold because $(e) * $(a) ≠ $(a)")
            return false
        elseif a * e ≠ a
            println("identity does not hold because $(a) * $(e) ≠ $(a)")
            return false
        end
    end
    return true
end

ismonoid(s, *, e) = ismagma(s, *) && isidentity(s, *, e) && isassociative(s, *)

isgroup(s, *, i, e) = ismonoid(s, *, e) && isinversefunction(s, *, i, e)

isring(s, op1, i1, e1, op2, e2) = isgroup(s, op1, i1, e1) && ismonoid(s, op2, e2)


# Code for generating groups

function get_add_group(n)
    s = 0:(n-1)
    op = (a, b) -> mod(a + b, n)
    e = 0
    i = a -> mod(-a, n)
    return (s, op, i, e)
end

function get_mult_group(n)
    get_coprimes(n) = filter(a -> gcd(a, n) == 1, 0:(n-1))

    function multinv(s, *, a, e)
        # This is a brute force method, it can be done faster with the Extended Euclidean algorithm
        for b ∈ s
            if a * b == e # The operation * is abelian, so left inverse implies inverse
                return b
            end
        end
        println("$(a) has no inverse")
        return nothing
    end

    s = get_coprimes(n)
    println("the domain is $(s)")
    op = (a, b) -> mod(a * b, n)
    e = 1
    i = a -> multinv(s, op, a, e)

    return (s, op, i, e)
end

println(isgroup(get_add_group(5)...))
println(isgroup(get_mult_group(5)...))
```
