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


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------

La verificación de tensiones en los arcos de una presa bóveda se realiza como parte de un **proceso iterativo de cálculo y proyecto por aproximaciones sucesivas**, dada la gran complejidad estructural de este tipo de presas.

La verificación tensional ocurre principalmente en dos etapas de cálculo:

### 1. Verificación en Primera Aproximación (Fórmulas Simplificadas)

En la fase de predimensionamiento, la presa se considera definida por una serie de **arcos horizontales** independientes. Cada arco resiste el empuje del agua correspondiente a una faja de $1,00 \, \text{m}$ de altura.

Para comprobar el comportamiento resistente de estos arcos, se utiliza la **Fórmula de los Tubos delgados** (o cilindros). Una vez que se ha calculado el espesor ($e$) del arco para una cota determinada, se verifica la tensión ($\sigma$) producida por la presión total ($p$) actuante en ese nivel, despejando $\sigma$ de la fórmula fundamental:

$$\sigma = \frac{p \cdot R}{e}$$

Donde $R$ es el radio del arco y $p$ es la presión radial uniforme.

**Consideraciones y Limitaciones de la Fórmula de los Tubos:**
Esta fórmula se considera una **primera aproximación** porque:
1.  Supone la **independencia de los arcos**, aunque en realidad están trabados por la coherencia del material y la estructura trabaja en conjunto.
2.  Es válida para formas circulares cerradas con cargas radiales y **sin coacción**. Los arcos reales se apoyan en las laderas (estribos), recibiendo reacciones de apoyo que generan momentos e incluso **tracciones**.

Para tener en cuenta estos efectos no analizados en la fórmula, es práctica habitual tomar la tensión admisible del hormigón ($\sigma_{adm}$) del orden de **la mitad de su valor** durante la primera aproximación para fijar los espesores. La disminución de la tensión admisible se compensa con la interacción real de los arcos (que reduce las cargas), dando un resultado satisfactorio para esta etapa.

### 2. Verificación Detallada (Comportamiento Resistente)

Una vez que se ha definido la geometría inicial, la **comprobación del comportamiento resistente** debe realizarse para **todos los estados de carga** considerados.

Para el cálculo más preciso de tensiones y deformaciones, las fórmulas simplificadas resultan insuficientes. Se recurre a métodos de análisis más complejos:

#### A. Método de la Carga de Prueba (Trial Load)
Este método concibe la estructura formada por elementos horizontales (**arcos**) y elementos verticales (**ménsulas** o *cantilevers*) trabados entre sí y colaborando conjuntamente en la resistencia de las cargas.

El proceso incluye la verificación de tensiones al final de una serie de iteraciones:
1.  Se divide el empuje hidrostático en dos partes, una que carga sobre la ménsula y otra que carga sobre los arcos.
2.  Se supone un reparto de presiones inicial y se calculan los desplazamientos de los puntos comunes para los arcos y las ménsulas.
3.  Se corrigen las distribuciones de presiones hasta conseguir que los desplazamientos sean prácticamente iguales, asegurando la unicidad del desplazamiento en los puntos de intersección.
4.  **Se calculan las tensiones** en los arcos y en las ménsulas para verificar que son **aceptables**.
5.  Si las tensiones no son aceptables (es decir, menores que las admisibles), se modifican los espesores o la geometría de los arcos y se repite el proceso.

#### B. Método de Elementos Finitos
Este método permite el **análisis tridimensional** de la estructura. Utiliza elementos hexaédricos o prismáticos para ajustarse a la geometría compleja de la presa y de la garganta, y posibilita estudiar el funcionamiento tridimensional y conjuntamente con la fundación. Permite determinar el estado tensional y de deformación.

### 3. Criterios de Aceptación de Tensiones

Las tensiones calculadas deben compararse con la resistencia admisible del hormigón, ajustada por los **Factores de Seguridad (Fs)**, según la clasificación de los estados de carga (definidos por el Bureau of Reclamation):

| Combinación de Carga | Factor de Seguridad (Fs) | Tensión Admisible ($\sigma_{adm}$) |
| :--- | :--- | :--- |
| **USUALES** (Ej: NNE) | $Fs = 3$ | $\sigma_{comp} \leq \sigma_{adm}/3$ |
| **INUSUALES** (Ej: NME) | $Fs = 2$ | $\sigma_{comp} \leq \sigma_{adm}/2$ |
| **EXTREMAS** (Ej: SBO) | $Fs = 1$ | $\sigma_{comp} \leq \sigma_{adm}/1$ |

Para las presas en arco, las tensiones admisibles a tracción aumentan de las combinaciones usuales a las inusuales y a las extremas.

### 4. Verificación de Tracciones (Criterio de Jakobsen)

Además de verificar las compresiones, se debe determinar si existen posibilidades de **tracciones** (tensiones negativas) en los arcos, especialmente cerca de los estribos, donde las reacciones generan momentos.

El **Criterio de Jakobsen** es una formulación utilizada para este fin, limitándose a verificar los **ángulos límites** para que el esfuerzo en el trasdós (paramento aguas abajo) de los arranques sea cero. Este criterio relaciona la relación **espesor/radio medio ($e/r$)** con el **ángulo central ($2\theta$)**.

*   Si la geometría del arco cae **debajo de la curva** definida por el criterio, existirá tracción en el trasdós de los arranques y probablemente en el intradós de la clave.
*   Si el punto cae **por encima de la curva**, esto indica compresión en ambos paramentos.

Incluso si se detectan tracciones y fisuración en posiciones extremas de la línea de presiones, en las presas en arco **siempre quedará un arco activo o resistente** con espesor reducido y sometido íntegramente a compresión, lo que confiere a la estructura una gran capacidad de resistencia.


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------


El fragmento al que usted se refiere aborda la complejidad de aplicar un **estado de carga horizontal** (el efecto sísmico en la masa) dentro del **método simplificado de la Fórmula de los Tubos**, que por definición es aplicable solo a cargas **radiales uniformes**.

A continuación, se explica el significado de las variables y cómo se considera el componente radial en esta aproximación:

### Definición de las variables $\boldsymbol{a, \beta, \text{y } g}$

Estas variables están relacionadas con el análisis sísmico de tipo **pseudoestático**, donde el efecto dinámico del sismo se simula mediante fuerzas estáticas horizontales proporcionales a la masa de la estructura:

*   **$\boldsymbol{\beta}$ (Coeficiente Sísmico Horizontal):**
    *   Es el **coeficiente de aceleración** (o coeficiente sísmico).
    *   Representa la relación entre la aceleración sísmica esperada ($a$) y la aceleración de la gravedad ($g$). En el ejercicio se proporciona $\beta = 0,05$.
*   **$\boldsymbol{g}$ (Aceleración de la gravedad):**
    *   Es la aceleración estándar de la gravedad terrestre (generalmente $9,81 \, \text{m/s}^2$).
*   **$\boldsymbol{a}$ (Aceleración Sísmica):**
    *   Es la **aceleración horizontal** real que experimenta la masa del arco durante el Sismo Básico Operativo (SBO).
    *   Se calcula como $a = \beta \cdot g$. Para estructuras simples, se puede asumir una **aceleración uniforme** desde la base hasta la cresta, igual a la aceleración estimada del sitio para calcular las cargas de inercia en análisis pseudoestáticos.

### Componente Radial del Efecto Sísmico en la Masa

La fuerza inercial horizontal total por metro de altura ($\text{F}_i$) se calcula como: 
$$\text{F}i = \text{M} \cdot a = (\text{Masa por metro lineal}) \cdot (\beta \cdot g)$$
$$\text{F}{hor} \cdot e \cdot 1,0) \cdot \beta \cdot g$$(Donde $e$ es el espesor y $\gamma{hor}$ es el peso específico del hormigón).

#### Descomposición de la Fuerza

Para poder utilizar la simplificación de la Fórmula de los Tubos ($\sigma = P \cdot R / e$), que asume que la carga ($P$) es **radial y uniforme**, la fuerza inercial horizontal $\text{F}_i$ debe ser descompuesta para obtener su componente normal (radial) al paramento del arco.

**Consideración del componente radial:**

1.  **Dirección de la fuerza:** El sismo impone una fuerza inercial $\text{F}_i$ que actúa **horizontalmente** en una única dirección (o en la dirección que produzca la estructura menos estable). Esta fuerza actúa sobre el centro de gravedad del arco horizontal considerado.
2.  **Necesidad radial:** En un arco curvo, una fuerza horizontal no es radial excepto en el punto donde el paramento es vertical (si la fuerza sísmica es transversal al cañón) o en la clave del arco (si la fuerza sísmica es paralela al cañón).
3.  **Aproximación:** Para incluir esta carga en la Fórmula de los Tubos (una simplificación extrema), se debe considerar únicamente la **componente de la fuerza inercial $\text{F}_i$ que actúa en la dirección radial (o normal) al arco en el punto de análisis.**
    *   Si el arco es circular y la fuerza sísmica es transversal al eje del cañón (dirección usual para el análisis de arco), el componente radial de la fuerza inercial en cualquier punto del arco es proporcional al coseno del ángulo ($\theta$) que dicho punto forma con la clave.
    *   Esta componente radial es la que debe sumarse, en términos de **presión equivalente** ($P_{sísmico}$), al empuje hidrostático y de sedimentos para obtener la $P_{total}$ en la fórmula $\sigma = P_{total} \cdot R / e$.

En resumen, la consideración del componente radial se realiza **proyectando la fuerza horizontal de inercia ($F_i$) sobre la dirección normal a la superficie del arco** en el punto que se está analizando. No obstante, esta aproximación es laboriosa y la Fórmula de los Tubos resulta muy limitada para modelar correctamente los efectos sísmicos, que son inherentemente complejos y no uniformes a lo largo del arco. Para un cálculo más preciso, es necesario recurrir a métodos más sofisticados como el Método de la Carga de Prueba (*Trial Load*) o el Método de Elementos Finitos.


-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------


Su pregunta es fundamental para entender el método simplificado de cálculo utilizado en el predimensionamiento de las presas en arco.

La expresión $$\sigma = \frac{P_{total} \cdot R}{e}$$ es la fórmula de la **Tensión Tangencial (o Circunferencial)** en un **cilindro delgado** sometido a presión interna, conocida en este contexto como la **Fórmula de los Tubos delgados**.

A continuación, se explica el sentido y la justificación de por qué el estado tensional se calcula de esta manera, según lo descrito en las fuentes:

### 1. Contexto: Presas en Arco y Primera Aproximación

El proyecto y el cálculo de una presa bóveda son de gran complejidad estructural, por lo que se realizan por **aproximaciones sucesivas**.

En la primera aproximación (o etapa de anteproyecto), la presa se concibe simplificadamente como si estuviera formada por una **serie de arcos horizontales independientes**. Esta simplificación permite aplicar principios básicos de resistencia de materiales.

Se establece la hipótesis de que **cada arco resiste el empuje del agua** (y otras cargas) correspondiente a una **faja de $1,00 \, \text{m}$ de altura** y a la profundidad correspondiente.

### 2. Origen y Sentido de la Fórmula

El arco horizontal, que soporta la presión del agua, se modela como un **tubo** (o cilindro) delgado sometido a una presión radial uniforme.

La fórmula de los tubos delgados (cilindros) relaciona la presión ($p$) con la tensión interna ($\sigma$) que se genera en el material, el radio ($R$), y el espesor ($e$) del cilindro.

Las fuentes establecen la fórmula para determinar el **espesor** ($e$) que debe tener el arco para resistir una presión $p$ con una tensión admisible $\sigma$:

$$e = \frac{p \cdot R}{\sigma}$$

La fórmula que usted pregunta, $\sigma = \frac{P_{total} \cdot R}{e}$, es simplemente el **despeje de la tensión ($\sigma$)** de esta fórmula original.

### 3. Significado Físico de la Relación

Esta fórmula describe el **equilibrio de fuerzas** en la pared del arco por unidad de altura:

*   **Presión ($P_{total}$ o $p$):** Representa la fuerza externa (presión total, incluyendo agua, sedimentos o sismo) que intenta **romper o abrir el arco**. Esta fuerza es proporcional a la presión ($p$) y al radio ($R$) del arco.
*   **Tensión ($\sigma$):** Representa la **tensión tangencial o circunferencial** (es decir, el esfuerzo interno) que se desarrolla en el hormigón y que actúa a lo largo de la curva para **resistir y contener la presión interna**.

#### Componentes de la Fórmula:

1.  **$P_{total} \cdot R$ (Fuerza Interna Total):** Esta parte representa la fuerza total por unidad de longitud (vertical) que debe ser resistida por la sección del arco.
2.  **$e$ (Espesor):** El espesor es la sección sobre la que se distribuye la tensión.

La tensión ($\sigma$) resultante es la fuerza interna ($P_{total} \cdot R$) dividida por el área de la sección ($e \cdot 1,0 \, \text{m}$ de altura).

$$\boldsymbol{\sigma = \frac{\text{Fuerza a resistir}}{\text{Área resistente}}}$$

**Implicaciones del Sentido:**

*   **Proporcionalidad con el Radio ($R$):** Cuanto mayor es el radio del arco (más plana es la curva), mayor debe ser la tensión generada para resistir la misma presión.
*   **Inversamente Proporcional al Espesor ($e$):** Cuanto mayor sea el espesor del arco, la misma fuerza se distribuye en más material, por lo que la tensión ($\sigma$) disminuye.

### 4. Limitaciones de la Fórmula (Por qué solo es una aproximación)

Aunque es satisfactoria para el predimensionamiento, es crucial entender que esta fórmula tiene limitaciones en el contexto de una presa en arco real:

1.  **Cargas Radiales Uniformes:** La fórmula solo es válida para formas circulares cerradas con cargas perfectamente radiales y uniformes.
2.  **Coacción de los Apoyos:** En la realidad, los arcos no son cerrados; **se apoyan en las laderas (estribos)**. Estas reacciones de apoyo en los estribos generan momentos internos e incluso **tracciones** (tensiones negativas) que la Fórmula de los Tubos no considera.
3.  **Interacción Vertical:** La fórmula supone la **independencia de los arcos**. Sin embargo, la estructura trabaja en conjunto; los arcos están trabados por la coherencia del material y transmiten cargas a los arcos adyacentes (superior e inferior) y a las ménsulas verticales.

Debido a estas limitaciones, en la práctica, se suele tomar la tensión admisible ($\sigma_{adm}$) del hormigón a la mitad de su valor en esta etapa para **compensar** los efectos no considerados (momentos, tracciones) antes de usar la fórmula.
