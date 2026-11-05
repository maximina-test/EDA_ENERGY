# # ⚡ ¿Dónde pagan más las familias de EE. UU. por la electricidad?

Análisis exploratorio de datos (EDA) del precio, el consumo y la factura de la electricidad residencial en los 50 estados de EE. UU. (2010–2025), y de su relación con el mix energético de cada estado. Datos oficiales de la U.S. Energy Information Administration (EIA).

## Pregunta

**¿Dónde pagan más las familias estadounidenses por la electricidad, y se debe al precio, a cuánto consumen o a cómo se produce la electricidad en su estado?**

Este análisis puede servir, por ejemplo, a una empresa de placas solares que quiere decidir en qué estados expandirse (donde la electricidad es más cara, cada placa ahorra más) o a un gobierno que reparte ayudas a las familias.

## Hipótesis

1. Hay grandes diferencias entre estados: el más caro paga más del doble que el más barato. ✅
2. El Noreste, California y Hawái tienen la electricidad más cara. ✅
3. Donde la electricidad es más cara, los hogares consumen menos. ✅
4. El precio ha subido en todas las regiones desde 2010. ✅

## Principales conclusiones

- **El precio cambia más del triple entre estados:** el estado típico paga ≈ 15 ¢/kWh y Hawái ≈ 40 ¢.
- **Los 5 estados más caros** son Hawái, California, Massachusetts, Rhode Island y Connecticut: 3 de 5 son del Noreste.
- **Electricidad barata no significa factura baja:** el Sur (≈ 15 ¢/kWh) paga al mes lo mismo que el Noreste (≈ 26 ¢/kWh), unos 158 $, porque consume mucho más.
- **Donde la electricidad es más cara, se consume menos** (correlación r = −0,75).
- **El precio sube en todas las regiones**, sobre todo desde 2021. El Noreste sube ≈ +65 % desde 2010, frente a +40–50 % en el resto.
- **El mix energético explica solo una parte del precio:**
  - Carbón (r = −0,47): los estados con más carbón tienen la electricidad más barata.
  - Renovables (r = −0,08) y nuclear (r = 0,03): sin relación con el precio.
  - Petróleo (r = 0,56): efecto casi exclusivo de Hawái.

> **En resumen:** el Noreste paga por el precio y el Sur por el consumo. Mirar solo el precio del kWh no basta para saber dónde sufren más las familias.

![Precio frente a factura por región](src/img/02_precio_vs_factura_region.png)

## Datos

Fuente: [EIA – Detailed State Data](https://www.eia.gov/electricity/data/state/)

| Dataset | Qué contiene |
|---|---|
| *Annual sales to ultimate customers by state and sector (EIA-861), 2010–2025* | Precio, consumo, ingresos y nº de clientes residenciales por estado y año |
| *Net Generation by State by Type of Producer by Energy Source (EIA-906, EIA-920, and EIA-923)* | Electricidad producida por cada estado según la fuente (carbón, gas, nuclear, renovables…), 1990–2025 |

**Variables creadas:**
- Factura mensual por hogar = ingresos ÷ nº de hogares ÷ 12
- Consumo anual por hogar = electricidad vendida ÷ nº de hogares
- Región = las 4 regiones del censo de EE. UU.
- % de cada fuente de energía en la producción de cada estado

## Limitaciones

- Precios en dólares de cada año, sin descontar la inflación.
- No incluye horas de sol ni ayudas o regulación de cada estado.
- Un estado puede comprar electricidad a otros, así que lo que produce no es exactamente lo que consumen sus hogares.
- El análisis muestra relaciones entre variables, no causas.

## Estructura del repositorio

```
├── README.md
├── presentacion.pdf
└── src/
    ├── memoria.ipynb      # Notebook principal con todo el análisis
    ├── data/              # Datos originales y limpios
    ├── notebooks/         # Notebooks de pruebas
    ├── utils/             # Funciones de limpieza
    └── img/               # Gráficos
```

## Tecnologías

Python · pandas · NumPy · matplotlib · seaborn · SciPy · openpyxl · Jupyter Notebook

## Autora

**Maxima Milano** – Proyecto del bootcamp de Data Analysis de The Bridge
[LinkedIn](https://www.linkedin.com/in/[tu-usuario])