## Bienvenida/os!

El TP Integrador consiste de tres notebooks cuyos nombres consisten de "TP Integrador - Grupo 1 - #", siendo "#" el número correspondiente a la notebook seleccionada.

Al correr la notebook "TP Integrador - Grupo 1- 1" se descarga la base de datos. Si se presenta algún problema descargar la base de datos de este link [Google Drive](https://drive.google.com/file/d/1ab2YSVnRP9qLu8CFz9wTC9Lb8rdnjWOY/view?usp=sharing)

<br>

----

### Objetivo 

Una compañía de seguros quiere mejorar la estimación de sus reservas de siniestros pendientes y para ello necesita un modelo que calcule de la mejor manera posible cuál será el monto que deberá pagar por cada siniestro.  

Las reservas de las compañías de seguro representan el compromiso técnico que se tiene frente a los asegurados y las mismas son auditadas periódicamente por organismos que regulan la actividad aseguradora. Por lo tanto, es muy relevante que los cálculos de las mismas reflejen fidedignamente la responsabilidad que se tiene a cada momento.  

Cada vez que una compañía de seguros recibe una denuncia de siniestro, se abre un proceso automático por el cual se reserva un importe de dinero que se espera pagar por el siniestro en cuestión, de modo tal que el balance de la compañía contemple el compromiso adeudado al asegurado. Si esa reserva es sobreestimada, la cía estará reteniendo mayor dinero del necesario y perdiendo la posibilidad de usarlo para otro fin. Si la reserva en cambio está subestimada, la cía podría disponibilizar capital para otros fines y luego incurrir en faltantes para afrontar los compromisos técnicos.

### Descripción del producto a analizar

Para este trabajo los siniestros a analizar serán referidos a un producto que cubre ante fallas mecánicas de equipos electrónicos y electrodomésticos.  

Al momento de adquirir un electrodoméstico nuevo, se otorga la posibilidad de adquirir un seguro que otorgue cobertura por un plazo determinado de tiempo ante eventuales desperfectos/roturas/fallas de fabricación que puedan ocurrir. Generalmente los plazos ofrecidos van entre 1 y 4 años de protección, y los mismos se activan una vez terminada la garantía de fábrica del producto asegurado, o bien, cubren aquello que el fabricante no contemple.  

Es importante resaltar que esta cobertura no cubre ante daños accidentales, robos, y/o siniestros ocasionados por la mala utilización/movilidad/translado/ejecución del producto.  

Cada siniestro puede derivar en una reparación del equipo o bien en el reemplazo del mismo.  

Dado que la variable objetivo es un importe, se abordará un problema de regresión.

---

## Dataset

El dataset fue obtenido internamente, cuenta con mas de 26.000 registros y presenta las siguientes variables:



| Variable | Descripción |
| ------ | ------ |
| **Dealer**| Identificación de cliente|
| **Product_Group**| Categoría de producto|
| **Product_SubGroup**| Categoría Ampliada de producto|
| **Product_Code**| Descripción del producto|
| **Manufacturer**| Marca/Fabricante|
| **Model**| Modelo|
| **Insurance_Term_months**| Plazo contratado|
| **Product_Purchase_Price**| Precio de Compra del producto|
| **FX_Sales_Date**| Tipo de cambio (USD) al momento de la compra|
| **FX_Sales_Date_Blue**| Tipo de cambio (USD Blue) al momento de la compra|
| **Solution**| Reparación/Reemplazo|
| **FX_Loss_Date_prev**| Tipo de cambio (USD) del día anterior a la denuncia|
| **FX_Loss_Date_prev_Blue**| Tipo de cambio (USD Blue) del día anterior a la denuncia|
| **Service_Center**| Código interno del servicio Técnico utilizado. Si reemplazó: No Aplica|
| **Manufacturer_Warranty**| Plazo de garantía de Fábrica|
| **Months_at_loss**| Antigüedad del producto al momento de la denuncia del siniestro|
| **Cost**| Costo Total Pagado (target)|

<br>

----

## Contenido de las notebooks

### Notebook 1

- Análisis Descriptivo de las variables Categóricas y Numéricas. Dentro de estas últimas, se hace un análisis de las Variables en USD y se eliminan Outliers.
- Se crea un nuevo dataset sin outliers ("Base_TP_clean.csv").

### Notebook 2

- Carga del dataset generado en la Notebook 1 ("Base_TP_clean.csv").
- Modelado de los datos. Se toma como modelo base Linear Regression, por lo que se espera obtener un mejor resultado con los modelos elegidos para fitting: XGBoost, Random Forest, SVR (Support Vector Regression) y AdaBoost]
- Sección con gráficos conparativos de los modelos y sus performances.

### Notebook 3

- Carga del dataset generado en la Notebook 1 ("Base_TP_clean.csv").
- Carga del modelado de datos producido en la notebook 1, para el uso del modelo elegido y features.
- Interpretación del modelo elegido, feature importance y R² por producto.
- Por último, comparativa con la Metodología Actual utilizada por la empresa.