# 🧑‍💻 Revisión de Código - Patrones de Comportamiento (GoF)

### 👤 Revisor: Emmanuel Isai Chavez Hernandez 23211005

### 📌 PR Revisado: #135
(https://github.com/JohanHerrera21/pdd/tree/main/practicas/comportamiento/temas/fix/Se%20usa%20una%20clase%20Notificador%20con%20if%20para%20decidir%20si%20se%20env%C3%ADa%20correo%2C%20SMS%20o%20notificaci%C3%B3n%20push.%20%E2%9D%8C%20%E2%86%92%20Falta%20Strategy%20o%20Command.)

---

## ✅ Checklist Técnica

| Ítem | ¿Cumple? | Comentarios |
|------|----------|-------------|
| **1. Identifica al menos un code smell estructural real** | [x] Sí / [ ] No | _¿Cuál fue? Violación del Principio Open/Closed  ¿Se justifica bien? Sí, porque cada vez que se necesita agregar un nuevo tipo de notificación, se debe modificar la clase `Notificador` (alterando el diccionario en el constructor), en lugar de poder extenderla sin modificarla._ |
| **2. Aplica un patrón estructural adecuado** | [x] Sí / [ ] No | _¿Cuál patrón usó? Patrón Command ¿Es el más apropiado? Sí, es apropiado porque desacopla el objeto que invoca la operación (Notificador) de los objetos que la ejecutan (los comandos concretos), permitiendo parametrizar objetos con operaciones._ |
| **3. La solución es coherente y mejora el diseño** | [x] Sí / [ ] No | _¿Hay redundancias o errores aún? No hay redundancias significativas. El diseño es coherente y sigue una estructura clara. Los comandos están bien separados y el invoker maneja adecuadamente la ejecución._ |
| **4. El código es legible y está bien estructurado** | [x] Sí / [ ] No | _¿Se entiende fácilmente? El código es muy legible, con nombres descriptivos en español, estructura clara y comentarios adecuados que explican cada componente._ |
| **5. El PR está bien documentado y argumentado** | [x] Sí / [ ] No | _¿Explica claramente el cambio? El código incluye comentarios explicativos que documentan el propósito de cada clase y método, facilitando la comprensión del patrón implementado._ |

---

## 🧠 Observaciones Técnicas

_Comentarios sobre lo que se hizo bien, con base en principios de diseño estructural:_

-  **Separación de responsabilidades:** Cada comando tiene una única responsabilidad específica
-  **Principio de inversión de dependencias:** El `Notificador` depende de la abstracción `INotificacionCommand`, no de implementaciones concretas
-  **Encapsulamiento:** La lógica de cada tipo de notificación está encapsulada en su propia clase
-  **Extensibilidad:** Es fácil agregar nuevos tipos de notificación implementando la interfaz
-  **Interface segregation:** La interfaz es pequeña y específica

---

## 🛠️ Sugerencias de Mejora

_Al menos una mejora concreta sobre nombres, estructura, implementación, SRP, etc._

## 1. Aplicar el Principio Open/Closed completamente
## 2. Mejorar el manejo de errores
## 3. Considerar usar un enum para los tipos de notificación

---

## 🎯 Entrega Final

_Un resumen general como revisor:_

> "Excelente implementación del patrón Command. El código demuestra una comprensión sólida de los principios de diseño orientado a objetos, especialmente en la separación de responsabilidades y la inversión de dependencias. La estructura es clara, legible y fácil de mantener. La única mejora significativa sería hacer la clase `Notificador` más abierta a extensión aplicando completamente el principio Open/Closed. El trabajo es de alta calidad y sigue las mejores prácticas de desarrollo."
---

🔚 **Gracias por compartir tu código. Todo feedback busca mejorar nuestra práctica como desarrolladores.**

