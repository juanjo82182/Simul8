# Evaluación y Mejora de Desempeño Operativo en una Empresa de Servicio Técnico-Mecánico (Simul8)

## Enunciado del Problema
Se tiene una empresa de servicio técnico-mecánico con el objetivo de evaluar y mejorar su desempeño operativo. La empresa se especializa en el mantenimiento, reparación y diagnóstico de vehículos automotores, y se utilizará el software Simul8 para modelar y analizar sus procesos internos. 

La llegada de usuarios (Automóviles, Motocicletas, Vehículos Comerciales y Públicos) está dada por una distribución Weibull [0.454, 1.83, 0.61] y sus porcentajes de uso son:

- **Automóviles:** 60%  
- **Motocicletas:** 25%  
- **Vehículos Comerciales:** 10%  
- **Vehículos Públicos:** 5%  

### Proceso de Diagnóstico
Los clientes forman una fila para el diagnóstico del vehículo, realizado por una persona. 
Las probabilidades del diagnóstico son:

- **60%**: No aceptables, requieren reparación.
- **30%**: No requieren reparación, solo mantenimiento preventivo.
- **10%**: Exentos de la técnico-mecánica (por antigüedad, tipo, etc.).

Si el vehículo no pasa el diagnóstico, no continúa en el proceso. Si es aceptado, se le entrega un formulario para obtener sus datos. El tiempo de diagnóstico sigue una distribución **log-normal** con un promedio de **14.8** y desviación estándar de **2.46**.

### Pago del Servicio
Los clientes pasan a una segunda fila (capacidad máxima: 20) para pagar la técnico-mecánica. Hay **2 cajas de pago** con un tiempo de verificación en el sistema distribuido de manera **uniforme entre 2.2 y 5.9 minutos**.

### Preparación y Reparación
Después del pago:

1. **Ubicación en una estación**: Manejado por **3 mecánicos**, con tiempo **exponencial** de **1.73 minutos**.
2. **Asignación de trabajo**:
   - **Mantenimiento Preventivo**: 1 mecánico, tiempo **uniforme de 25 a 30.9 minutos**.
   - **Reparación de vehículos defectuosos** (2 mecánicos, tiempos **uniformes de 30 a 65.8 minutos**):
     - Reparación de motor: **10%**
     - Reparación de transmisión: **20%**
     - Reparación de frenos: **15%**
     - Reparación de suspensión y dirección: **35%**
     - Reparación del sistema electrónico: **20%**

3. **Revisión final**: Cola de revisión de **10 minutos**.
4. **Entrega del vehículo**: Cualquiera de los 3 mecánicos, con un tiempo promedio de **1.16 minutos**.

---

## Definición de Variables de Respuesta

1. **Número de vehículos certificados**: Cantidad de vehículos que obtienen certificación técnico-mecánica.
2. **Número de vehículos exentos**: Vehículos que no pueden ser procesados.
3. **Tasa de abandono**: Clientes que abandonan el sistema sin ser atendidos.
4. **Costo de mano de obra**: Gasto total en mecánicos, cajeros, etc.

---

## Preguntas a Responder con el Modelo

- ¿Cuántos vehículos fueron exentos del proceso técnico-mecánico?
- ¿Cuántos automóviles, motocicletas, vehículos comerciales y públicos fueron certificados?
- ¿Cuál es el costo total de mano de obra asociado a la operación?
- ¿Cuáles son los ingresos obtenidos por la prestación de los servicios?
- ¿Cuáles son las utilidades mensuales por operación?

---

## Escenarios de Optimización

### **Escenario 1**: Incremento de Vehículos Finalizados y Reducción de Clientes Perdidos
- Se incrementa el recurso de diagnóstico.
- Se añade una **tercera caja de pago**.
- Se elimina una estación para **reducir costos**.

### **Escenario 2**: Optimización de Costos y Flujo de Trabajo
- Se prioriza la **cola de reparación**.
- Se añade una estación de mantenimiento para minimizar la cola.
- Se mantiene **3 mecánicos**:
  - **2** en estaciones de reparación.
  - **1** en la nueva estación de mantenimiento.
  - **1** encargado de certificados.
- **Escenario recomendado** debido a su balance entre costos y ganancias (análisis en el archivo Excel "anexos").
