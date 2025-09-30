Este ejercicio requiere el diseño y verificación preliminar de una presa en arco de radio constante. Dado que no se adjuntan el croquis de la garganta ni los valores numéricos de los niveles (NNE, NME, $L_{cuerda}$), la respuesta se centrará en describir y fundamentar el procedimiento de cálculo requerido, utilizando las fórmulas y los criterios mencionados en las fuentes.

El proyecto y cálculo de una presa bóveda se realiza por **aproximaciones sucesivas** debido a su gran complejidad estructural. En esta etapa se aplican fórmulas simplificadas.

---

### Datos Iniciales (Proporcionados por el usuario y las fuentes)

*   **Resistencia Admisible del Hormigón** ($\sigma_{adm}$): $13000 \, \text{kPa}$
*   **Coeficiente Sísmico Horizontal** ($\beta$): $0,05$ (Sismo Básico Operativo, SBO)
*   **Período de la Presa** ($T$): $1 \, \text{seg}$.
*   **Empuje de Sedimentos** ($\gamma_{sed}$): $1,4$ (Se asume $\gamma_{sed} \approx 1,4 \, \text{t/m}^3$, o $13,73 \, \text{kN/m}^3$ si usamos unidades del SI, o $14 \, \text{kPa/m}$ para simplificar, dependiendo de las unidades adoptadas para la presión hidrostática).
*   **Peso Específico del Hormigón** ($\gamma_{hor}$): $2,40 \, \text{t/m}^3$.

---

## 1. Diseño de una presa en arco de radio constante

Las **Presas de Radio Constante** son convenientes en valles en forma de "U" donde la cuerda de los arcos varía poco con la altura. Se define por una serie de arcos horizontales que forman una superficie de revolución cilíndrica de eje vertical, permitiendo que los radios sean iguales a distintas alturas.

### a) Planteo de los arcos

El diseño se basa en la definición geométrica de una serie de arcos horizontales que se adaptan al terreno (el "encaje de la presa").

Para una presa de radio constante, se establece un **radio único** ($R$) que define la directriz del paramento aguas arriba y aguas abajo.

### b) Determinación del radio y el ángulo central

#### Determinación del Radio ($R_{eje}$)

El predimensionamiento se realiza con el criterio del Bureau of Reclamation:

$$R_{eje} = 0,6 \cdot L_{cuerda}$$

Donde $L_{cuerda}$ es la longitud de la cuerda en el coronamiento. Para realizar este cálculo, es necesario conocer el valor de $L_{cuerda}$ (longitud de la cuerda al nivel del coronamiento) del croquis adjunto (dato faltante).

Una vez definido $R_{eje}$ (el radio del eje del arco), el radio interior y exterior de cada arco dependerá del espesor ($e$) que se determine.

#### Determinación del Ángulo Central ($2\alpha$)

El ángulo central ($2\alpha$) se determina geométricamente para cada arco a una cota dada, utilizando la cuerda ($L$) correspondiente a esa cota y el radio $R$:

$$R = \frac{L}{2 \sin \alpha}$$

Aunque el radio $R$ es constante (en este diseño), las cuerdas $L$ disminuirán hacia la base, lo que provocará que el ángulo central $2\alpha$ varíe ligeramente con la altura.

**Consideración del Ángulo Óptimo:**
Para la economía de volumen, la función $V \propto (\alpha / \sin^2 \alpha)$ tiene un mínimo cuando el ángulo central es $2\alpha = 133^\circ 34'$. Sin embargo, se acepta un rango genérico entre **$100^\circ$ y $150^\circ$** ya que esto permite una buena aproximación y mayor flexibilidad estructural.

### c) Fijación de espesores en primera aproximación

La primera aproximación de los espesores se realiza con el **criterio simplificado de la Fórmula de los Tubos** (o tubos delgados), que supone que cada arco es independiente y resiste el empuje hidrostático de una faja de 1 metro de altura.

La fórmula de los tubos delgados (o cilindros) para un espesor $e$ sometido a una presión radial uniforme $p$ es:

$$e = \frac{p \cdot R}{\sigma} = \frac{\gamma h \cdot R}{\sigma}$$

Donde:
*   $R$: Radio del arco [m].
*   $p$: Presión hidrostática ($\gamma h$) [kPa].
*   $\sigma$: Tensión admisible del material [kPa].
*   $h$: Profundidad (altura de agua sobre el arco) [m].

#### Tensión Admisible Reducida

Para fijar los espesores en primera aproximación, se utiliza una **tensión admisible reducida del hormigón**.

Se debe tomar la tensión admisible ($\sigma_{adm}$) del material **del orden de la mitad de su valor**. Esto se hace para tener en cuenta el efecto de las reacciones de apoyo en las laderas que generan momentos e incluso tracciones, aunque este efecto se compensa con la interacción de los arcos (que reduce las cargas).

**Cálculo de la Tensión Reducida:**
$$\sigma_{red} = \frac{\sigma_{adm}}{2} = \frac{13000 \, \text{kPa}}{2} = 6500 \, \text{kPa}$$

**Cálculo del Espesor ($e$)**
Se calcularía el espesor para el **Nivel Normal de Embalse (NNE)**, utilizando la altura de agua $h_{NNE}$ sobre el arco considerado y la tensión reducida:

$$e_{NNE} = \frac{\gamma_{agua} \cdot h_{NNE} \cdot R}{\sigma_{red}}$$

Este cálculo se debe realizar para una serie de arcos horizontales definidos por las cotas de verificación indicadas en el croquis (datos faltantes).

### d) Determinación de tensiones en los arcos (Fórmula de los Tubos)

Para verificar las tensiones en los arcos bajo diferentes estados de carga, se utiliza la fórmula de los tubos despejando la tensión ($\sigma$):

$$\sigma = \frac{P_{total} \cdot R}{e}$$

Donde $P_{total}$ es la presión total actuante (estática + sismo + sedimentos) sobre el arco considerado, y $e$ es el espesor previamente calculado.

#### Cargas Actuantes y Estados de Carga

Los estados de carga requeridos son combinaciones específicas. La verificación de tensiones se comparará con los Factores de Seguridad (Fs) del Bureau of Reclamation.

| Combinación | Categoría (BoR) | Factor de Seguridad (Fs) |
| :--- | :--- | :--- |
| NNE + Sedimentos | Usualmente **USUAL** (Si NNE y temperaturas usuales) | 3 |
| NME + Sedimentos | **INUSUAL** | 2 |
| NNE + SBO | **EXTREMA** (Usual + Sismo Máximo Creíble) | 1 |

**1. Nivel Normal de Embalse (NNE) + Presión de Sedimentos**

$$P_{total} = P_{hidrostática(NNE)} + P_{sedimentos}$$

*   **Presión Hidrostática:** $p_{hidro} = \gamma_{agua} \cdot h_{NNE}$.
*   **Presión de Sedimentos:** Se considera el empuje de sedimentos con $\gamma_{sed} = 1,4$. La presión de sedimentos ($p_{sed}$) se debe calcular en función de la altura de sedimentos ($h_{sed}$) y su densidad sumergida, aunque la consulta simplemente indica $\gamma_{sed}=1,4$ para el empuje.
*   **Tensión del Arco:** $\sigma_{1} = \frac{(P_{hidro} + P_{sed}) \cdot R}{e}$

Se debe verificar que $\sigma_{1} \leq \sigma_{adm} / 3$ (para Fs=3).

**2. Nivel Máximo de Embalse (NME) + Presión de Sedimentos**

$$P_{total} = P_{hidrostática(NME)} + P_{sedimentos}$$

*   Se utiliza la altura de agua $h_{NME}$ y el empuje de sedimentos correspondiente.
*   **Tensión del Arco:** $\sigma_{2} = \frac{(P_{hidrostática(NME)} + P_{sed}) \cdot R}{e}$

Se debe verificar que $\sigma_{2} \leq \sigma_{adm} / 2$ (para Fs=2).

**3. Nivel Normal de Embalse (NNE) + Sismo Básico Operativo (SBO)**

Este estado de carga incluye el efecto sísmico en la masa del hormigón y la sobrepresión sísmica del agua (hidrodinámica).

$$P_{total} = P_{hidrostática(NNE)} + P_{sísmica(masa)} + P_{sobrepresión(agua)}$$

*   **Efecto Sísmico en la masa:** Se calcula la fuerza inercial ($F_i$) de la masa del arco. La masa por metro lineal del arco es $M = e \cdot 1,0 \cdot \gamma_{hor}$. La fuerza sísmica horizontal es $F_i = M \cdot a = M \cdot \beta \cdot g$, o $F_i = W \cdot \beta$. Esta fuerza no es puramente radial y complejiza el uso estricto de la Fórmula de los Tubos, ya que esta fórmula es válida para cargas radiales uniformes sin coacción. Para una primera aproximación con la fórmula de los tubos, el componente radial debe ser considerado.
*   **Sobrepresión Sísmica (Presión Hidrodinámica):** Se utiliza la fórmula de Zanger o Westergaard (como se solicita) para determinar la presión dinámica adicionada.
    *   La fórmula de Westergaard, por ejemplo, proporciona la presión dinámica horizontal ($P_d$) en función de la profundidad $h$, el coeficiente sísmico $\beta$, y la densidad del agua.
    *   La consulta pide usar $T=1$ seg.
*   **Tensión del Arco:** $\sigma_{3} = \frac{(P_{hidro(NNE)} + P_{sobrepresión}) \cdot R}{e} + \sigma_{efecto\_masa}$ (el componente de tensión generado por el efecto de masa debe ser evaluado o estimado radialmente).

Se debe verificar que $\sigma_{3} \leq \sigma_{adm} / 1$ (para Fs=1).

### e) Determinación de posibilidades de tracciones (Criterio de Jakobsen)

El Criterio de Jakobsen permite verificar la posibilidad de tracciones en los arcos en función de su geometría. Este criterio relaciona el **espesor/radio medio ($e/r$)** con el **ángulo central ($2\theta$ o $2\alpha$)**.

Este criterio se limita a darnos los ángulos límites para que el esfuerzo en el trasdós de los arranques (apoyos) sea cero.

**Análisis según el Criterio de Jakobsen:**

1.  Se calcula la relación geométrica **$e/r$** para el arco analizado, donde $r$ es el radio medio.
2.  Se localiza el punto definido por ($e/r$, $2\alpha$) en el gráfico del Criterio de Jakobsen (no adjunto en las fuentes, pero conceptualmente descrito).
3.  **Interpretación:**
    *   Si el punto cae **bajo la curva** de referencia, "existirá tracción en el trasdós de los arranques y probablemente en el intradós de la clave".
    *   Si el punto cae **encima de la curva**, esto indica compresión en ambos paramentos.
    *   Incluso si aparecen tracciones y fisuración, las presas en arco tienen una gran capacidad de adaptación, y usualmente queda un "arco activo" (resistente) sometido íntegramente a compresión con gran capacidad de resistencia.

Para aplicar este criterio, se necesitarían los valores calculados de $e$ y $R$ para los arcos principales.


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

La determinación del espesor de una presa en arco se basa principalmente en cálculos estructurales para garantizar que el material soporte las tensiones. Por lo tanto, el **espesor mínimo no es un valor fijo universal**, sino que está implícitamente determinado por los requisitos de resistencia y la geometría.

Sin embargo, los textos proporcionan información relevante sobre cómo se determina el espesor y ejemplos de dimensiones:

### Determinación Estructural del Espesor

El proceso de cálculo preliminar para una presa bóveda se realiza por aproximaciones sucesivas.

1.  **Fórmula de los Tubos:** En una primera aproximación, se calcula el espesor ($e$) del arco horizontal utilizando la fórmula de los tubos delgados, que supone que cada arco es independiente y está sometido a una presión radial uniforme ($p$):
    $$e = \frac{p \cdot R}{\sigma} = \frac{\gamma h \cdot R}{\sigma} \quad$$
    Donde $\sigma$ es la tensión admisible del material. El espesor resultante ($e$) en esta fórmula representa el **espesor mínimo requerido** para resistir la carga hidrostática ($p$) a una profundidad ($h$) determinada, con un radio ($R$) y una tensión admisible ($\sigma$) dada.
2.  **Tensión Admisible Reducida:** Para la fijación de los espesores en primera aproximación, se suele tomar la **tensión admisible del hormigón del orden de la mitad de su valor** para tener en cuenta los efectos de las reacciones de apoyo en las laderas que pueden generar momentos e incluso tracciones. Esto obliga a un espesor preliminar mayor, lo que actúa como un factor de seguridad inicial.
3.  **Variación Vertical:** El espesor debe aumentar hacia la base debido a que la carga ($h$) y el radio ($R$) varían con la profundidad (fórmula de los tubos). Por lo tanto, el espesor más delgado generalmente se encontrará en el coronamiento (la parte superior).

### Ejemplos de Espesores Mínimos Prácticos

Aunque no se establece un requisito mínimo absoluto para el espesor de la clave del arco en una presa bóveda general, existe un ejemplo concreto de dimensiones mínimas en presas de bóvedas múltiples, un tipo de presa en arco:

*   La presa Bartlett Dam, un ejemplo de bóveda múltiple en Arizona, utiliza una serie de arcos con un radio de 7 m (24 ft). Estos arcos miden **2 m (7 ft) en la base y solo 0,6 m (2 ft) en la cresta**. Este valor (0,6 m) es un ejemplo de un espesor real muy reducido en la parte superior.

### Clases de Presas por Espesor

El espesor de la presa en arco se relaciona con su esbeltez, definida por la relación entre el ancho de la base ($B$) y la altura estructural ($H$):

*   **Presas Esbeltas:** $B/H \le 0,20$ (e.g., Dique El Cajón, $B/H = 0,077$; Dique Los Alazanes, $B/H = 0,192$).
*   **Presas Semiesbeltas:** $0,20 \le B/H \le 0,30$.
*   **Presas de Gran Espesor (Arco-Gravedad):** $B/H \ge 0,30$. Estas presas son gruesas y su baja curvatura hace que resistan parte de las cargas por efecto arco y parte por gravedad.

En resumen, el espesor mínimo en una presa en arco es el que resulta de los cálculos de ingeniería ($e = \gamma h R / \sigma$) para resistir las tensiones admisibles, y no un valor fijo de normativa, aunque la práctica constructiva impone límites funcionales.
