link: https://sambo1994.github.io/life-path-predictor/









1. Life Expectancy Calculation (LE):
The life expectancy is determined based on the birth year 
𝑌
birth
Y 
birth
​
  and sex 
𝑆
S, where:

𝑆
=
0
S=0 for male, 
𝑆
=
1
S=1 for female.
Interpolation is done between predefined life expectancy values based on the birth year.
𝐿
𝐸
=
InterpolatedLifeExpectancy
(
𝑌
birth
,
𝑆
)
LE=InterpolatedLifeExpectancy(Y 
birth
​
 ,S)
If the birth year falls between two predefined years, the interpolated value is computed using linear interpolation.

2. Variation Adjustment (V):
The variation is introduced based on the birth day 
𝐷
birth
D 
birth
​
  and a name-based hash value 
𝐻
H, which is derived from the name. The hash is a numeric value representing the user's name.

𝑉
=
(
(
𝑌
birth
+
𝐻
)
 
m
o
d
 
7
)
−
(
(
𝐷
birth
+
𝐻
)
 
m
o
d
 
3
)
V=((Y 
birth
​
 +H)mod7)−((D 
birth
​
 +H)mod3)
Here, 
 
m
o
d
 
mod represents the modulo operation, ensuring that the variations are small values, influencing the lifespan slightly.

3. Predicted Lifespan (PL):
The predicted lifespan is the sum of the base life expectancy and the variation:

𝑃
𝐿
=
𝐿
𝐸
+
𝑉
PL=LE+V
This gives the final predicted lifespan in years.

4. Predicted Year of Death (Y_{\text{death}}):
The predicted death year is calculated by adding the predicted lifespan to the birth year:

𝑌
death
=
𝑌
birth
+
𝑃
𝐿
Y 
death
​
 =Y 
birth
​
 +PL
5. Predicted Month of Death (M_{\text{death}}):
The predicted death month is influenced by both the birth month 
𝑀
birth
M 
birth
​
  and the name hash value 
𝐻
H. We ensure that the result is a valid month (1 to 12):

𝑀
death
=
(
(
𝑀
birth
×
𝐻
)
 
m
o
d
 
12
)
+
1
M 
death
​
 =((M 
birth
​
 ×H)mod12)+1
6. Predicted Day of Death (D_{\text{death}}):
The predicted death day is based on the birth day 
𝐷
birth
D 
birth
​
  and the name hash value 
𝐻
H, ensuring that the result is a valid day (1 to 28):

𝐷
death
=
(
(
𝐷
birth
+
𝐻
×
3
)
 
m
o
d
 
28
)
+
1
D 
death
​
 =((D 
birth
​
 +H×3)mod28)+1
7. Final Death Date (DD):
The final predicted death date is the combination of the predicted year, month, and day:

𝐷
𝐷
=
(
𝑀
death
,
𝐷
death
,
𝑌
death
)
DD=(M 
death
​
 ,D 
death
​
 ,Y 
death
​
 )
Summary of Mathematical Formulas:
Life Expectancy:

𝐿
𝐸
=
InterpolatedLifeExpectancy
(
𝑌
birth
,
𝑆
)
LE=InterpolatedLifeExpectancy(Y 
birth
​
 ,S)
Variation:

𝑉
=
(
(
𝑌
birth
+
𝐻
)
 
m
o
d
 
7
)
−
(
(
𝐷
birth
+
𝐻
)
 
m
o
d
 
3
)
V=((Y 
birth
​
 +H)mod7)−((D 
birth
​
 +H)mod3)
Predicted Lifespan:

𝑃
𝐿
=
𝐿
𝐸
+
𝑉
PL=LE+V
Predicted Year of Death:

𝑌
death
=
𝑌
birth
+
𝑃
𝐿
Y 
death
​
 =Y 
birth
​
 +PL
Predicted Month of Death:

𝑀
death
=
(
(
𝑀
birth
×
𝐻
)
 
m
o
d
 
12
)
+
1
M 
death
​
 =((M 
birth
​
 ×H)mod12)+1
Predicted Day of Death:

𝐷
death
=
(
(
𝐷
birth
+
𝐻
×
3
)
 
m
o
d
 
28
)
+
1
D 
death
​
 =((D 
birth
​
 +H×3)mod28)+1
Final Death Date:

𝐷
𝐷
=
(
𝑀
death
,
𝐷
death
,
𝑌
death
)
DD=(M 
death
​
 ,D 
death
​
 ,Y 
death
​
 )
