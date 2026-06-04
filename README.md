# Amazon Sales Analytics — Microsoft Fabric

> *"Proyecto construido íntegramente en Microsoft Fabric Service — sin Desktop, sin atajos."*

---

## Problema

Una empresa de e-commerce con ventas en India no tenía visibilidad sobre qué categorías, estados de pedido y períodos temporales impulsaban o frenaban sus ventas. Los datos eran un CSV plano sin estructura analítica, sin dimensiones, sin capacidad de filtrado cruzado.

## Proceso

1. **Ingesta** — CSV cargado directamente en el Lakehouse (`lh_practica`) via Microsoft Fabric
2. **Limpieza y transformación** — Notebooks PySpark para convertir la columna `Date` → `DateConverted` y generar la tabla `DimDate`
3. **Modelo en estrella** — 1 tabla de hechos + 5 dimensiones creadas con PySpark
4. **Medidas DAX** — 5 KPIs accionables definidos en el Semantic Model en Direct Lake
5. **Report Power BI** — 4 páginas temáticas construidas en el Fabric Service

## Herramienta

**Microsoft Fabric Service íntegramente** — sin Power BI Desktop, sin pasos intermedios:

| Componente | Detalle |
|---|---|
| Lakehouse | `lh_practica` — ingesta y almacenamiento |
| Notebooks | PySpark — limpieza, transformación y creación de dimensiones |
| Semantic Model | Direct Lake — sin import, sin scheduled refresh |
| Power BI | Report de 4 páginas construido en el Service |
| Capacidad | F2 PAYG — Spain Central |

## Modelo en estrella

```
amazonsalereport (hechos)
    ├── dimdate
    ├── dimproducte   (ASIN único)
    ├── dimgeografia
    ├── dimstatus
    └── dimfulfilment
```

## Medidas DAX

| Medida | Valor |
|---|---|
| Total Ventas | 78,59 M |
| Total Pedidos | 129 K |
| Total Ventas Enviadas | 50,32 M |
| Ticket Medio | 609,36 |
| % Cancelaciones | 8,80% |

## Resultado

Report de 4 páginas con visibilidad completa sobre el negocio:

- **Portada** — 5 KPIs principales + navegación
- **Página 1** — Visión general de ventas
- **Productos** — Análisis por categoría y talla
- **Tendencias** — Evolución temporal de ventas
- **Geografía** — Distribución por estado (mapa + barras)

## Impacto

- Identificación de patrones de cancelación por categoría y estado
- Concentración geográfica: Maharashtra, Karnataka y Telangana lideran las ventas
- Visibilidad de estacionalidad para orientar decisiones de stock y campaña

---

## Tecnologías

![Microsoft Fabric](https://img.shields.io/badge/Microsoft%20Fabric-000000?style=flat&logo=microsoft&logoColor=white)
![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=flat&logo=powerbi&logoColor=black)
![PySpark](https://img.shields.io/badge/PySpark-E25A1C?style=flat&logo=apachespark&logoColor=white)
![DAX](https://img.shields.io/badge/DAX-0078D4?style=flat&logo=microsoft&logoColor=white)

---

## Autor

**Carles Sancho Sales**
[carlessales.com](https://carlessales.com) · [LinkedIn](https://linkedin.com/in/carlessanchosales/) · [PL-300 Certified](https://learn.microsoft.com/en-us/credentials/certifications/data-analyst-associate/)
