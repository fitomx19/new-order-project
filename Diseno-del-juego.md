# MathWorld: Guerra Fría 2026

## Objetivo del portafolio

Mi objetivo es construir y documentar un producto completo para demostrar mis habilidades en **ciencia de datos, ingeniería de software, desarrollo con AWS y agentes de IA**. Quiero que quien revise el proyecto pueda jugar una demo, reproducir un experimento y entender qué decisiones tomé y por qué.

| Área | Qué voy a construir | Cómo se podrá comprobar |
| --- | --- | --- |
| Ciencia de datos | Modelos de economía y elecciones, simulaciones con azar y comparación de estrategias. | Un experimento con hipótesis, versión del motor, semillas, métricas y resultados reproducibles. |
| Ingeniería de software | Motor de turnos, API, persistencia y tablero web adaptable. | Una partida que se pueda guardar y retomar, pruebas del motor y una guía para instalar la demo. |
| AWS | Entorno integrado desde la primera versión con un emulador, infraestructura como código y ejecución de simulaciones por lotes. | Una instalación desde cero que permita jugar, lanzar un lote y recuperar sus resultados. El despliegue en AWS real se contempla como un hito posterior. |
| Agentes de IA | Un gabinete que consulta pronósticos y recomienda acciones usando la información disponible para el jugador. | Casos de evaluación sobre validez de acciones, fidelidad de cifras, manejo de incertidumbre, tiempo de respuesta y respaldo local. |

## Objetivo del juego y trama

En 2026, tres superpotencias ficticias compiten por dirigir un mundo que depende de cadenas de energía, chips, comercio y crédito. La carrera por la inteligencia artificial general (AGI) agrava esa dependencia. Los bloques neutrales aprovechan la rivalidad para negociar suministro, financiamiento y protección.

Controlas al gobierno de una superpotencia. Heredas deuda, contratos, divisiones internas y proyectos en marcha. Buscas imponerte sin perder el apoyo que te permite gobernar. Si pierdes el cargo, termina tu campaña y un epílogo cuenta qué pasó con tu país y con sus rivales.

La primera campaña completa tendrá rutas de victoria por AGI, alianzas y finanzas. La visión ampliada incluye rutas de influencia cultural o religiosa, control territorial, transición política y cooperación en crisis extraordinarias. La inestabilidad interna y la escalada entre potencias pueden cerrar la partida. Los umbrales, las reglas para victorias simultáneas y las condiciones de empate se validarán con pruebas.

## Cómo se elige y se juega

- **País.** Los perfiles propuestos son Asteria (ciencia y economía), Varkania (defensa), Meridia (finanzas), Liria (diplomacia), Serevia (influencia cultural y religiosa) y Novera (industria y energía). Cada ventaja trae una dependencia o un costo.
- **Gobierno.** Se plantean repúblicas presidenciales y parlamentarias, y regímenes centralizados. La descentralización modifica la coordinación con las regiones. La selección cambia cómo se aprueban medidas, qué información llega y qué puede terminar el mandato.
- **Escenario.** El prototipo será *Elecciones bajo apagón*. El catálogo propuesto también incluye *El giro de 2026*, *Las primeras 72 horas*, *Invierno financiero* y *Amenaza exterior*.
- **Turno.** Lees el informe, eliges una iniciativa y, si hay crisis, puedes responder. El motor resuelve las acciones de las potencias y actualiza recursos, relaciones y apoyo. El tablero, los informes y el historial explican los resultados.
- **Campaña.** La meta es ocho turnos, tres potencias activas y seis bloques neutrales. Se propone una mediana de 15 a 18 minutos y que al menos el 80 % de quienes prueben termine en 20 minutos o menos.

## Primera prueba jugable: Elecciones bajo apagón

Gobiernas Asteria y tienes una elección al cierre del tercer turno. Un proveedor neutral reduce el suministro de energía mientras tu país está cerca de un hito científico. Una región concentra hogares y servicios. La otra concentra industria y centros de datos.

1. **Turno 1.** Decides si subsidias hogares, negocias importaciones o reasignas energía de los centros de datos. Ves los efectos en la caja, la producción, la aprobación y el avance científico.
2. **Turno 2.** Cambia el pronóstico del apagón y aparecen indicios de sobrecostos. Puedes ajustar la medida, abrir una revisión o buscar un acuerdo de suministro, según las acciones disponibles.
3. **Turno 3.** Se resuelve la elección. El epílogo explica el resultado regional, el avance científico y los compromisos que deja el gobierno.

## Simulación, aplicación y agentes

El motor relaciona recursos, deuda, industria, elecciones, gobernabilidad y diplomacia. Los modelos propuestos incluyen redes de insumos, voto por grupos y regiones, riesgos de salida política, actualización de pronósticos ante nueva evidencia y simulación Monte Carlo para comparar estrategias. Los parámetros son sintéticos y se calibrarán para el mundo ficticio. El primer experimento comparará subsidios, importaciones y reasignación de energía con escenarios y semillas compartidos.

La propuesta inicial es React con TypeScript para el navegador, Python con FastAPI para la API y PostgreSQL como opción de persistencia. El motor será independiente de la interfaz. El diseño contempla guardar la versión, las decisiones y el azar usado en cada turno, y evitar que un reintento lo resuelva dos veces. La aplicación empieza en web adaptable. Una app para tiendas queda para una fase posterior.

El emulador de AWS debe permitir probar el flujo de partidas y los lotes que usan el mismo motor. La elección depende de comprobar las operaciones de almacenamiento, cola y ejecución que pida la demo. Los servicios concretos y la compatibilidad se documentarán al hacer esa prueba.

Los rivales simulados toman decisiones con sus propias políticas. El asesor de IA consulta el estado visible, las acciones válidas y los pronósticos. Puede comparar alternativas y explicar sus supuestos. El motor valida acciones y resuelve los turnos. El gabinete tendrá un resumen local de respaldo.

## Cómo se toman y revisan las decisiones

1. Anotar la pregunta y las opciones. Por ejemplo, qué emulador cubre los flujos o qué política energética conviene en cada escenario.
2. Elegir una prueba y un criterio. Para el emulador, levantar los flujos en limpio. Para la energía, comparar costos, producción, apoyo electoral y avance científico con las mismas semillas.
3. Registrar en el Excel la decisión, el motivo, la evidencia y el siguiente paso. Si cambia, conservar el acuerdo anterior y explicar qué resultado motivó el cambio.
4. Vincular cada decisión a su tarea y a su hito. El caso de estudio final mostrará la secuencia desde la pregunta hasta el resultado.

El documento maestro ya da una ruta de diseño y un primer escenario. Quedan por validar la duración de la partida, los umbrales de victoria, los emparejamientos de rivales, la cobertura del emulador y los resultados de las pruebas. El [Excel](Planeacion-e-hitos.xlsx) organiza ese avance.

## Seguimiento de la planeación

La hoja **Plan** tiene 40 tareas distribuidas entre 10 hitos. Cada hito se lleva a un objetivo de trabajo, dos subobjetivos y cuatro tareas. Las fechas de inicio y fin son propuestas. Las notas indican qué revisar, qué supuesto se usa o qué evidencia conviene guardar. Al cambiar una fecha, revisa las tareas que dependen de ella y actualiza el cierre del hito en el Excel.
