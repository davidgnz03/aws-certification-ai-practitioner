# AWS Bedrock — CloudWatch Integration

## Introducción
**Amazon CloudWatch** se integra nativamente con **AWS Bedrock** para ofrecer **monitoreo, trazabilidad y métricas operativas** sobre el uso de modelos fundacionales (FMs), agentes, RAGs y guardrails.  
Esta integración permite a los equipos de IA y DevOps **visualizar el rendimiento, registrar invocaciones y detectar anomalías** en tiempo real, garantizando el control y la observabilidad de las aplicaciones de IA generativa en producción.

---

## Model Invocation Logging
La característica de **Model Invocation Logging** en AWS Bedrock habilita el registro detallado de todas las invocaciones a modelos fundacionales, incluyendo:
- Prompts enviados por el usuario.  
- Parámetros de configuración del modelo (por ejemplo, `temperature`, `maxTokenCount`, etc.).  
- Respuestas generadas.  
- Resultados de evaluación o errores de ejecución.

Estos registros se envían automáticamente a **Amazon CloudWatch Logs**, donde pueden ser analizados, auditados o visualizados mediante dashboards personalizados.

### Beneficios:
- 🔍 **Auditoría completa** de solicitudes y respuestas de modelos.  
- ⚙️ **Depuración de prompts y errores de inferencia.**  
- 📊 **Análisis de uso por modelo, aplicación o usuario.**  
- 🔐 **Cumplimiento y trazabilidad**, especialmente en entornos regulados.  

**Ejemplo de evento registrado en CloudWatch Logs:**
```json
{
  "modelId": "amazon.titan-text-express-v1",
  "timestamp": "2025-10-29T19:30:00Z",
  "invocationId": "1234abcd-5678efgh",
  "inputTokens": 750,
  "outputTokens": 200,
  "latencyMs": 3200,
  "userId": "app-bot-01",
  "status": "Success"
}
```
---
## CloudWatch Metrics

AWS Bedrock publica **métricas automáticas en CloudWatch** para ayudar a monitorear el rendimiento, la eficiencia y la seguridad de los modelos.  

Estas métricas se pueden visualizar en la consola de CloudWatch, incluir en **dashboards personalizados**, o utilizar en **alarmas automáticas** que detecten comportamiento anómalo o violaciones de políticas.  


### Métricas principales de Bedrock
| Métrica                  | Descripción                                                         |
| ------------------------ | ------------------------------------------------------------------- |
| **InvocationCount**      | Número total de invocaciones al modelo.                             |
| **InputTokenCount**      | Total de tokens de entrada procesados.                              |
| **OutputTokenCount**     | Total de tokens generados como salida.                              |
| **InvocationLatency**    | Tiempo promedio de respuesta del modelo (ms).                       |
| **ContentFilteredCount** | Número de respuestas bloqueadas o modificadas por los *Guardrails*. |
| **ErrorCount**           | Número de fallas o errores durante invocaciones.                    |
| **RejectedRequestCount** | Solicitudes rechazadas por políticas de seguridad o cuotas.         |


---

### Métrica destacada: ```ContentFilteredCount```

La métrica **ContentFilteredCount** indica cuántas respuestas del modelo fueron **filtradas, censuradas o bloqueadas** debido a:

- Activación de Guardrails (contenido sensible, sesgo, lenguaje inapropiado).

- Cumplimiento de reglas de seguridad o moderación de contenido.

- Detección de datos personales o temas restringidos.

Uso típico:

- Detectar si un modelo está generando contenido fuera de las políticas establecidas.

- Ajustar los parámetros de prompting o guardrails para mejorar la calidad y seguridad de las respuestas.

- Establecer alarmas cuando la frecuencia de filtrado supera un umbral.

**Ejemplo:**
```text
Metric: ContentFilteredCount
Threshold: > 10 por hora
Alarm Action: Notificar al equipo de IA/Seguridad
```
---

## CloudWatch Alarms

Las **alarmas de CloudWatch** permiten automatizar la supervisión de métricas críticas de Bedrock.
Se configuran para enviar notificaciones o ejecutar acciones cuando una métrica excede un valor definido.

### Ejemplo de alarmas comunes
| Alarma                           | Condición                      | Acción                                        |
| -------------------------------- | ------------------------------ | --------------------------------------------- |
| **Alta latencia**                | `InvocationLatency > 4000ms`   | Notificar al canal DevOps o escalar recursos. |
| **Errores frecuentes**           | `ErrorCount > 5` en 10 minutos | Crear incidente en AWS Incident Manager.      |
| **Exceso de contenido filtrado** | `ContentFilteredCount > 10`    | Alertar al equipo de cumplimiento.            |
| **Umbral de tokens alto**        | `InputTokenCount > 100000`     | Revisar costos o límites de API.              |

**Ejemplo (CLI):**
```bash
aws cloudwatch put-metric-alarm \
  --alarm-name "Bedrock-FilteredContent-Alarm" \
  --metric-name ContentFilteredCount \
  --namespace "AWS/Bedrock" \
  --statistic Sum \
  --period 300 \
  --threshold 10 \
  --comparison-operator GreaterThanThreshold \
  --evaluation-periods 1 \
  --alarm-actions arn:aws:sns:us-east-1:123456789012:IA-Alerts
```
---

## Buenas Prácticas de Monitoreo

- ✅ Habilitar CloudWatch Logs en todos los endpoints de Bedrock.

- ✅ Separar métricas por modelo y aplicación para mayor granularidad.

- ✅ Combinar logs y métricas para identificar correlaciones (por ejemplo, latencia alta con contenido filtrado).

- ✅ Integrar con AWS Chatbot o SNS para recibir notificaciones en tiempo real.

- ✅ Analizar tendencias de uso para optimizar costos y rendimiento.Buenas Prácticas de Monitoreo

- ✅ Habilitar CloudWatch Logs en todos los endpoints de Bedrock.

- ✅ Separar métricas por modelo y aplicación para mayor granularidad.

- ✅ Combinar logs y métricas para identificar correlaciones (por ejemplo, latencia alta con contenido filtrado).

- ✅ Integrar con AWS Chatbot o SNS para recibir notificaciones en tiempo real.

- ✅ Analizar tendencias de uso para optimizar costos y rendimiento.

---

## Conclusión

La integración de **AWS Bedrock con Amazon CloudWatch** proporciona un marco robusto de observabilidad para aplicaciones de IA generativa.  


Permite **registrar invocaciones, monitorear rendimiento y activar alarmas automáticas** basadas en métricas clave como ```ContentFilteredCount```, asegurando un control operativo completo sobre el comportamiento de los modelos y la seguridad de las respuestas.