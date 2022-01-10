# Kod (Mathematica)

## Dane:
p = 1.260;<br>
s[t_] := p t^2;<br>
T = 2;<br>
\[Omega]0 = 2 \[Pi]/T;
## Szereg Fouriera:
a0 = 1/T Integrate[s[t], {t, -1, 1}]<br>
a1 = 2/T Integrate[s[t] Cos[\[Omega]0 t], {t, -1, 1}]<br>
a2 = 2/T Integrate[s[t] Cos[2 \[Omega]0 t], {t, -1, 1}]<br>
f[t_] := a0 + a1 Cos[\[Omega]0 t] + a2 Cos[2 \[Omega]0 t]<br>
Plot[{s[t], f[t]}, {t, -1, 1}]

## Wyznaczanie współczynników:
w[t_] := a t^2 + b t + c<br>
Integrate[(f[t] - w[t]) t^2, {t, -1, 1}]<br>
Integrate[(f[t] - w[t]) t, {t, -1, 1}]<br>
Integrate[(f[t] - w[t]), {t, -1, 1}]<br>


eq1 = 0.49989733989533847\` - 0.4\` a - 0.6666666666666666\` c == 0;<br>
eq2 = 0.\` - 0.6666666666666666\` b == 0;<br>
eq3 = -0.6666666666666666\` (-1.26\` + a + 3.\` c) == 0;<br>
Solve[{eq1, eq2, eq3}, {a, b, c}]
 
