# 🛡️ Hoja de Observación - Prueba cruzada de guerreros

**Nombre del equipo que prueba:** Maria Fernanda Arzate Tolentino  
**Nombre del equipo dueño del código:** Kevin Tijerina del Castillo  
**Fecha:** 2025-08-12

---

## 1. Datos generales del guerrero evaluado

| Atributo        | Valor |
|-----------------|-------|
| Nombre del guerrero | No definido (genérico) |
| Vida base       | No implementada |
| Ataque base     | Fuerza (10 base) |
| Defensa base    | Resistencia (10 base) |
| Velocidad       | No implementada |

---

## 2. Pruebas de combate con enemigos personalizados

Prueba el guerrero con enemigos que tengan distintos niveles de fuerza, vida y velocidad.

| Enemigo # | Vida | Ataque | Velocidad | ¿Ganó el guerrero? | Observaciones |
|-----------|------|--------|-----------|---------------------|----------------|
| 1         | No definido | No definido | No definido | Variable | Poder enemigo se calcula con nivel y valores aleatorios. No hay vida ni defensa real. |
| 2         | -    | -      | -         | -                   | Combate es simple, basado en comparación de poderes. |
| 3         | -    | -      | -         | -                   | No se simula vida ni velocidad, lo que limita la estrategia. |
| 4         | -    | -      | -         | -                   | Se requiere al menos 30 energía para pelear. |
| 5         | -    | -      | -         | -                   | Derrota reduce energía en 10, sin experiencia ganada. |

---

## 3. Evaluación del sistema de entrenamiento

### A. Entrenar fuerza

- ¿Aumenta la fuerza después de entrenar? ✅  
- ¿Consume energía de forma proporcional a las horas? ✅  
- ¿El entrenamiento respeta el límite de 6 horas? ✅  
- Observaciones:  
  El entrenamiento consume 10 puntos de energía por hora y aumenta fuerza y experiencia proporcionalmente.

### B. Entrenar resistencia

- ¿Aumenta la resistencia? ✅  
- ¿Afecta otras estadísticas? (por ejemplo, menos energía) ✅  
- ¿Tiene sentido el impacto por hora entrenada? ✅  
- Observaciones:  
  Similar a fuerza, el entrenamiento consume energía y aumenta resistencia y experiencia.

### C. Dormir / Descansar

- ¿Recupera energía al descansar? ✅  
- ¿Se evita sobrecargar la energía (por ejemplo, pasar de 100)? ✅  
- Observaciones:  
  La energía se regenera en 15 puntos por hora de descanso, con límite máximo en 100.

---

## 4. Progresión y balance

- ¿El personaje sube de nivel correctamente con la experiencia acumulada? ✅  
- ¿Se siente balanceado el avance del personaje? ✅  
- ¿Hay consecuencias claras si no tiene energía (por ejemplo, no puede entrenar)? ✅  
- Observaciones:  
  El sistema de niveles aumenta estadísticas y permite el progreso continuo; se penaliza la falta de energía para entrenar o pelear.

---

## 5. Revisión de requisitos técnicos del código

| Requisito                                                        | Cumple ✅ / ❌ | Comentarios |
|------------------------------------------------------------------|---------------|-------------|
| Menú interactivo con `switch` que se repite                     | ✅            | Menú con bucle y switch para seleccionar acción |
| Al menos una función por actividad (Ej: `EntrenarFuerza()`)     | ✅            | Funciones separadas para entrenar, descansar, pelear |
| Uso de operadores aritméticos, lógicos y de comparación         | ✅            | Uso en cálculos y validaciones |
| Condiciones para subir de nivel, agotarse o perder una batalla | ✅            | Revisión de nivel y control de energía implementados |
| Validaciones de energía y límites                               | ✅            | Validación de energía mínima, máxima y horas |
| Decisión del usuario sobre cuántas horas invertir por acción   | ✅            | El usuario elige horas para entrenar o descansar |
| Uso de estructuras de control (`if`, `for`, `do-while`, etc.)   | ✅            | Uso de if, switch y ciclo do-while implícito |

---

## 6. Retroalimentación general

- El código es funcional, claro y sencillo de entender.  
- Se recomienda implementar atributos como vida y velocidad para un combate más realista.  
- El sistema de combate actual es muy simplificado y no permite estrategias complejas.  
- Mejorar la gestión de errores para entradas inválidas (no numéricas).  
- Mostrar estado de energía antes de solicitar horas para entrenar o descansar mejoraría la experiencia.  
- Añadir opción para definir nombre y atributos iniciales del guerrero.  
- Potenciar el sistema de niveles con nuevas habilidades o ítems para enriquecer el juego.
