# The triangle is an intruder from a higher dimension

Triangles, tetrahedrons and their higher-dimensional counterparts are natural geometric objects. However, they are surprisingly difficult to express in terms of points in space unless you allow a higher-dimensional perspective.

**In two dimensions**, consider the simplest case, an equilateral triangle with edge length 1. In the plane, we can define this triangle through the location of its vertices $A$, $B$ and $C$. Let $A = (0,0)$, $B = (1,0)$ and let $C$ be in the first quadrant. What are the coordinates of $C$? With basic trigonometry we see that the distance of $C$ from the x-axis is $\sin(2\pi/3) = \sqrt{3}/2$ and thus $C = (1/2, \sqrt{3}/2)$. This is not a very nice number for such a simple object. This is our first hint of the fact that the triangle does not allow itself to be represented in such a low dimension.

**In three dimensions**, the counterpart of a triangle is the tetrahedron. Say we position an equilateral tetrahedron with one vertex in the origin similar to the above case. What is the height of the tetrahedron? A <a href="https://math.stackexchange.com/questions/11085/height-of-a-tetrahedron">surprisingly lengthy argument</a> is required to see that the height is $\sqrt{6}/3$. The simplest Cartesian coordinates are obtained by for a tetrahedron with edge length 2, centered at the origin, and two level edges [<a href="https://en.wikipedia.org/wiki/Tetrahedron#Formulas_for_a_regular_tetrahedron">ref.</a>]:
$$
{\displaystyle \left(\pm 1,0,-{\frac {1}{\sqrt {2}}}\right)\quad {\text{and}}\quad \left(0,\pm 1,{\frac {1}{\sqrt {2}}}\right)}.
$$

**In four dimensions** it gets event worse, the Cartesian coordinates of the vertices of an origin-centered regular 5-cell having edge length 2 are [<a href="https://en.wikipedia.org/wiki/5-cell#Construction">ref.</a>]:
$$
\left({\frac {1}{\sqrt {10}}},\ {\frac {1}{\sqrt {6}}},\ {\frac {1}{\sqrt {3}}},\ \pm 1\right),
\left({\frac {1}{\sqrt {10}}},\ {\frac {1}{\sqrt {6}}},\ {\frac {-2}{\sqrt {3}}},\ 0\right),
\left({\frac {1}{\sqrt {10}}},\ -{\sqrt {\frac {3}{2}}},\ 0,\ 0\right),
\left(-2{\sqrt {\frac {2}{5}}},\ 0,\ 0,\ 0\right)
$$

# Higher-dimensional perspective

Instead of trying to describe a triangle within two dimensions, let's do it in three dimensions. It is very simple: A triangle is the region enclosed by the three points
$$
(1,0,0),\;(0,1,0),\;(0,0,1).
$$
That is, one vertex per axis. How about the tetrahedron? You guessed it; in four dimensions the tetrahedron is the region enclosed by the four points
$$
(1,0,0,0),\;(0,1,0,0),\;(0,0,1,0),\;(0,0,0,1).
$$
And so on for higher dimensions.

# Generalization

The notion of "region enclosed by" that was used above is made precise by the notion of <a href="https://en.wikipedia.org/wiki/Convex_hull">convex hull</a>. In this way the n-dimensional triangle can be defined as the set of points
$$
\left\{ x \in \mathbb{R}^{n+1} ~{\bigg |}~ \sum_{k=1}^{n+1} x_{k}=1 {\text{ and }}x_{k}\geq 0{\text{ for all }}k\right\}.
$$
This leads to the general notion of a <a href="https://en.wikipedia.org/wiki/Simplex">simplex</a>.
