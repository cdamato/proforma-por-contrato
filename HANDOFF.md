# HANDOFF · Detalle costes por proveedor

Tarea 3 del Design Roadmap (Epic 4, PROC-451). PM: Pol. Estado a 27/11/2026: en revisión de Pol; José (Ops) elige entre la versión A y la B.

## Dónde está

- **Proto:** rama `tarea-3-detalle-costes` (último commit `c51d5e5`), desplegada a mano con `npx vercel --prod --yes --scope cdamato` desde el worktree `claude files/detalle-costes-propuesta`.
  - Versión A: https://detalle-costes-propuesta.vercel.app/#detalle
  - Versión B: https://detalle-costes-propuesta.vercel.app/#detalle-agrupar
  - Ficha del proveedor: https://detalle-costes-propuesta.vercel.app/#detalle-proveedor
  - `main` y proforma-por-contrato.vercel.app no tienen la tarea 3.
- **Figma:** MASTER - PROCUREMENT, página «Control de costes - Apuntes contables - proformas», sección «Detalle costes por proveedor · versiones A y B»: https://www.figma.com/design/xgqGVHd2g7hCtrHjnp7Bci/MASTER---PROCUREMENT?node-id=4058-45556
  - Versión A (5 pantallas): https://www.figma.com/design/xgqGVHd2g7hCtrHjnp7Bci/MASTER---PROCUREMENT?node-id=4069-70870
  - Versión B (6 pantallas): https://www.figma.com/design/xgqGVHd2g7hCtrHjnp7Bci/MASTER---PROCUREMENT?node-id=4069-70871
  - Componentes comunes (no borrar): «Componentes · Detalle costes (comunes a A y B)», debajo de las dos versiones.
  - Cada pantalla lleva título y notas de Dev Mode con el comportamiento.

## Decidido

- Árbol categoría › proveedor › contrato, todo desplegado al entrar. «Plegar todo» pliega los proveedores y pasa a «Desplegar todo».
- Todo proveedor tiene su fila con el total y «· N contratos», también con un solo contrato.
- Código de contrato completo (HC-…). Columnas fijas: «Proveedor · Contrato» (420 px) y «Agrupación de compra» (200 px).
- Línea de traspaso: Badge gris «CD → CI», sin importes de contrato («—»), tooltip «Traspaso de coste directo a coste indirecto». La leyenda de la barra solo sale si hay traspaso a la vista.
- «Agrupación de compra» se puede ocultar desde «Configurar columnas»; se ve por defecto (Pol, 27/11).
- Ficha del proveedor: los contratos van bajo su categoría, sin fila de proveedor, sin «Plegar todo» ni «Agrupar por».
- Versión B: «Agrupar por» es una etiqueta fuera del Select, como «Periodo». Opciones: Proveedor (por defecto, igual que la A) o Contrato. Por contrato: columnas Contrato · Proveedor · Agrupación de compra, un contrato por fila, ordenado por código.
- Excel: siempre desplegado aunque en pantalla esté plegado. En la A, por proveedor; en la B, según «Agrupar por».

## Pendiente

- **Pol** valida la tarea y pasa la A y la B a José para que elija.
- **Pol con Oscar:** si backend puede generar dos Excels (necesario solo para la B).
- **Cuando José elija:**
  - Figma: borrar la sección de la versión descartada entera. Los componentes se quedan.
  - Proto: quitar la versión descartada y fusionar la rama en `main`.
