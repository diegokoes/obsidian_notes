> [!quote] Cambios marcados Los recuadros morados aplican la propuesta 1 y los azules la propuesta 2. Los recuadros verdes y el texto ==resaltado== aplican la propuesta 3.

## Apartado 1

Para que el sistema sea compatible determinado, necesitamos (==Rouché-Frobenius==) que ==$\text{rango}(A)=\text{rango}(A^*)=3$==, que es el número de incógnitas. ==Como $A$ es una matriz cuadrada de orden 3 y hay 3 incógnitas, $\text{rango}(A)=3$ si y solo si $\det(A)\neq0$.== Si $A$ ya tiene rango 3, la ampliada también porque no puede pasar de 3 filas.

Calculo $\det(A)$ desarrollando por la primera fila:

$$\det(A)=5\begin{vmatrix}1&-7\6&m\end{vmatrix}+5\begin{vmatrix}6&-7\4&m\end{vmatrix}+3\begin{vmatrix}6&1\4&6\end{vmatrix}=5(m+42)+5(6m+28)+3\cdot32=35m+446$$

> [!info] Propuesta 2, signos del desarrollo Los signos salen de la matriz de signos $\begin{pmatrix}+&-&+\-&+&-\+&-&+\end{pmatrix}$. El segundo término lleva signo $-$, así que $-(-5)=+5$.

==Luego $\det(A)=0$ si y solo si $35m+446=0$, es decir, cuando $m=-\dfrac{446}{35}$.== Por tanto, el sistema sí es compatible determinado para todo $m\neq-\dfrac{446}{35}$.

> [!example] Propuesta 1, el caso que anula el determinante Si $m=-\dfrac{446}{35}$, entonces $\det(A)=0$, así que $\text{rango}(A)<3$. El menor de orden 2 $\begin{vmatrix}5&-5\6&1\end{vmatrix}=5+30=35$ no es cero, así que $\text{rango}(A)=2$.
> 
> La matriz ampliada $A^_$ es $3\times4$, así que su rango es como mucho 3. Tomo el menor de orden 3 formado por las columnas 1 y 2 y por la columna de términos independientes. Este menor no depende de $m$. $$\begin{vmatrix}5&-5&86\6&1&12\4&6&-44\end{vmatrix}=5(-44-72)+5(-264-48)+86(36-4)=-580-1560+2752=612\neq0$$ Por tanto $\text{rango}(A^_)=3$. Como $\text{rango}(A)=2\neq\text{rango}(A^*)=3$, el teorema de Rouché-Frobenius dice que el sistema es **incompatible**.

> [!success] Conclusión del apartado 1
> 
> - Si $m\neq-\dfrac{446}{35}$, entonces $\text{rango}(A)=\text{rango}(A^*)=3$, que es el número de incógnitas. El sistema es **compatible determinado**.
> - Si $m=-\dfrac{446}{35}$, entonces $\text{rango}(A)=2$ y $\text{rango}(A^*)=3$. El sistema es **incompatible**.

## Apartado 2

Con $m=-4$, $\det(A)=35\cdot(-4)+446=306\neq0$, el sistema es cuadrado y el determinante no es nulo, así que tiene solución única y se puede aplicar Cramer.

> [!info] Propuesta 2, desarrollo de los determinantes de Cramer Llamo $A_1$, $A_2$ y $A_3$ a las matrices que resultan de sustituir la columna 1, 2 y 3 de $A$ por la columna de términos independientes $b$. Por la regla de Cramer, $x=\dfrac{|A_1|}{|A|}$, $y=\dfrac{|A_2|}{|A|}$ y $z=\dfrac{|A_3|}{|A|}$.
> 
> Desarrollo cada determinante por la primera fila. Multiplico cada elemento por su menor complementario, con los signos $+,-,+$ de la matriz de signos. Por eso el $-5$ de la primera fila de $A_1$ y de $A_3$ queda como $-(-5)=+5$. $$|A_1|=86\begin{vmatrix}1&-7\6&-4\end{vmatrix}+5\begin{vmatrix}12&-7\-44&-4\end{vmatrix}+3\begin{vmatrix}12&1\-44&6\end{vmatrix}=86\cdot38+5\cdot(-356)+3\cdot116=1836$$ $$|A_2|=5\begin{vmatrix}12&-7\-44&-4\end{vmatrix}-86\begin{vmatrix}6&-7\4&-4\end{vmatrix}+3\begin{vmatrix}6&12\4&-44\end{vmatrix}=5\cdot(-356)-86\cdot4+3\cdot(-312)=-3060$$ $$|A_3|=5\begin{vmatrix}1&12\6&-44\end{vmatrix}+5\begin{vmatrix}6&12\4&-44\end{vmatrix}+86\begin{vmatrix}6&1\4&6\end{vmatrix}=5\cdot(-116)+5\cdot(-312)+86\cdot32=612$$

$$x=\frac{\begin{vmatrix}86&-5&3\12&1&-7\-44&6&-4\end{vmatrix}}{306}=\frac{3268-1780+348}{306}=\frac{1836}{306}=\mathbf{6}$$

$$y=\frac{\begin{vmatrix}5&86&3\6&12&-7\4&-44&-4\end{vmatrix}}{306}=\frac{-1780-344-936}{306}=\frac{-3060}{306}=\mathbf{-10}$$

$$z=\frac{\begin{vmatrix}5&-5&86\6&1&12\4&6&-44\end{vmatrix}}{306}=\frac{-580-1560+2752}{306}=\frac{612}{306}=\mathbf{2}$$

Y para concluir, toca comprobar el resultado sustituyendo $x=6$, $y=-10$, $z=2$ en las ecuaciones originales con $m=-4$, ==es decir, escribiendo $A\cdot X=b$ con $X=(x,y,z)^T$==.

$$\begin{aligned} 5\cdot6-5\cdot(-10)+3\cdot2&=30+50+6=86\ 6\cdot6+(-10)-7\cdot2&=36-10-14=12\ 4\cdot6+6\cdot(-10)-4\cdot2&=24-60-8=-44 \end{aligned}$$

> [!success] Conclusión del apartado 2 Se cumplen las tres ecuaciones, así que la solución del sistema para $m=-4$ es $(x,y,z)=(6,-10,2)$.