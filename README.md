# Taller Formativo: Implementación de Patrones de Diseño en Aplicativos de Automóviles

### Video de explicacion
[Taller Formativo Mejores Practicas.mp4](https://udlaec-my.sharepoint.com/:v:/g/personal/ariel_cabrera_udla_edu_ec/ESRW2_oFYqdKmaazHOClB5QBrQ_cv42aDANskm3M0YEnQw?nav=eyJyZWZlcnJhbEluZm8iOnsicmVmZXJyYWxBcHAiOiJTdHJlYW1XZWJBcHAiLCJyZWZlcnJhbFZpZXciOiJTaGFyZURpYWxvZy1MaW5rIiwicmVmZXJyYWxBcHBQbGF0Zm9ybSI6IldlYiIsInJlZmVycmFsTW9kZSI6InZpZXcifX0%3D&e=OeZYeM)

## Descripción General

Este proyecto consiste en implementar patrones de diseño, principios SOLID y mejores prácticas en un aplicativo de gestión de vehículos para cumplir con los requerimientos establecidos por Codificando Con Patrones Cía. Ltda. 

El proyecto incluye la implementación de:
- Métodos de agregar vehículos.
- Un mecanismo para probar funcionalidades sin depender de la base de datos.
- Propiedades por defecto para vehículos, minimizando el impacto en futuros cambios.
- Un Factory Method para soportar la creación dinámica de nuevos modelos de vehículos.

## Requerimientos del Proyecto

### Problemas Identificados
1. **Métodos de agregar vehículos:** 
   - Los métodos de agregar vehículos en el Home Page no están implementados correctamente y no funcionan como se espera.
   - El patrón repositorio existente requiere modificaciones.

2. **Ausencia de base de datos:** 
   - El esquema de la base de datos no está listo, lo que exige una solución temporal para probar la funcionalidad sin almacenamiento persistente.

3. **Propiedades por defecto:** 
   - Se necesita agregar 20 propiedades por defecto al modelo de vehículo, además del año actual. La solución debe permitir extensibilidad para futuros sprints.

4. **Introducción de nuevos modelos:**
   - La adición de un nuevo modelo (Escape, marca Ford, color rojo) requiere implementar un Factory Method, anticipando futuras solicitudes de nuevos modelos.

### Solución Propuesta
Para abordar los problemas, se implementaron los siguientes patrones de diseño y principios:

#### Patrón Singleton
- **Propósito:** Permitir el acceso único y global a un repositorio temporal para gestionar vehículos mientras la base de datos no está lista.
- **Implementación:** Clase `MyVehiclesRepository` dentro de la carpeta `Repositories`.

#### Patrón Builder
- **Propósito:** Facilitar la construcción de vehículos con propiedades por defecto, incluyendo el año actual.
- **Implementación:** Clase `CarModelBuilder` en la carpeta `ModelBuilder`.

#### Patrón Factory Method
- **Propósito:** Estandarizar la creación de nuevos modelos de vehículos.
- **Implementación:** Clases como `FordEscapeFactory`, `FordExplorerFactory` y `FordMustangFactory` en la carpeta `Factories`.


## Justificación de los Patrones
1. Builder: Permite agregar propiedades de forma extensible, simplificando cambios futuros.
2. Factory Method: Estandariza la creación de nuevos modelos, facilitando la incorporación de futuras extensiones.
3. Singleton: Resuelve la falta de base de datos proporcionando una solución temporal sin duplicación de instancias.


## Cómo Ejecutar el Proyecto

1. **Clonar el Repositorio:**
   ```bash
   git clone https://github.com/EmilioAMVs/Taller_Formativo_Mejores_Practicas.git
   cd Best-Practices-Udla-Workshop
  
2. **Instalar Dependencias**
   ```bash
   dotnet restore
   ```
3. **Ejecutar la Aplicacion**
    ```bash
    dotnet run
    ```
4. **Pruebas Unitarias**
   ```bash
   dotnet test
   ```

