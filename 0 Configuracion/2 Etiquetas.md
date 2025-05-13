# ETIQUETAS BASADAS EN EL NIVEL DE INTERÉS Y ETAPA DEL PROCESO

- Si es el inicio de la conversación y el usuario está haciendo preguntas generales sobre Dawere o sus programas, sin especificar uno, asigna la etiqueta 'consulta_inicial'.
- Si el usuario ya ha enfocado su interés en uno o más programas particulares y pregunta detalles sobre ellos (costos, duración, requisitos de ESE programa), asigna la etiqueta 'interes_programa_especifico'.
- Si el usuario pregunta explícitamente "cómo me inscribo", "quiero inscribirme", "cuáles son los pasos para la inscripción", o muestra una intención clara de iniciar el proceso, asigna la etiqueta 'interes_inscripcion'.
- Si el LLM está actualmente guiando al usuario a través de alguno de los 9 pasos del "PROCESO DE INSCRIPCION" detallado en el prompt, asigna la etiqueta 'proceso_inscripcion_activo'.
- Si el usuario confirma haber completado todos los pasos del proceso de inscripción, incluyendo el agendamiento de la llamada de inducción, asigna la etiqueta 'inscripcion_completada'.
- Si el usuario muestra interés en inscribirse pero indica explícitamente que lo hará en otro momento o más adelante, asigna la etiqueta 'inscripcion_pospuesta'.
- Si el usuario indica claramente que no desea continuar con la inscripción o que los programas no son adecuados para él/ella en este momento, asigna la etiqueta 'sin_interes_actual'.

# ETIQUETAS BASADAS EN EL PERFIL DEL PROSPECTO

- Si el usuario menciona que está consultando "para mi hijo", "para mi hija", "para un representado", o usa un lenguaje similar que indique que no es el estudiante final, asigna la etiqueta 'prospecto_representante'.
- Si el usuario indica que la consulta es "para mí", "soy yo el que quiere estudiar", o usa un lenguaje similar que indique que es el futuro estudiante, asigna la etiqueta 'prospecto_estudiante_directo'.
- Si el usuario que se identifica como el estudiante directo menciona tener 18 años o más, o habla de combinar estudios con trabajo o responsabilidades familiares, asigna la etiqueta 'prospecto_adulto'.
- Si el usuario indica que el estudiante tiene entre 11 y 13 años inclusive, asigna la etiqueta 'prospecto_menor_edad_limite'.
- Si el usuario menciona que sus notas certificadas o estudios previos son de un país que no es Estados Unidos, asigna la etiqueta 'prospecto_extranjero_notas_otro_pais'.
- Si el usuario menciona que ya posee un título de bachiller, preparatoria o high school, asigna la etiqueta 'prospecto_con_titulo_previo'.
- Si el usuario menciona explícitamente motivaciones como "bullying", "soy atleta", "mi hijo es artista", "tiene TDAH", "viajamos mucho", "vivimos lejos de un colegio", o "necesita educación especial" como razón para buscar Dawere, asigna la etiqueta 'prospecto_necesidad_especial_mencionada'.

# ETIQUETAS BASADAS EN EL PROGRAMA DE INTERÉS PRINCIPAL (asigna la etiqueta del programa si la conversación se centra en él)

- Si la consulta o respuesta del LLM se centra principalmente en el programa "Bachillerato Online USA" (el estándar de 7mo a 12mo), asigna la etiqueta 'bachillerato_online_usa'.
- Si la consulta o respuesta del LLM se centra principalmente en el programa "Bachillerato Online Acelerado USA", asigna la etiqueta 'bachillerato_online_acelerado_usa'.
- Si la consulta o respuesta del LLM se centra principalmente en el programa "Bachillerato Online Adultos USA", asigna la etiqueta 'bachillerato_online_adultos_usa'.
- Si la consulta o respuesta del LLM se centra principalmente en el programa "Doble Titulación Bachillerato USA", asigna la etiqueta 'doble_titulacion_bachillerato_usa'.
- Si la consulta o respuesta del LLM se centra principalmente en el programa "US Dual High School Diploma", asigna la etiqueta 'us_dual_high_school_diploma'.
- Si la consulta o respuesta del LLM se centra principalmente en las "Pruebas de convalidación" como el servicio o "programa" que el usuario necesita seleccionar en la plataforma para ser ubicado, asigna la etiqueta 'pruebas_de_convalidacion'.

# ETIQUETAS BASADAS EN PUNTOS CRÍTICOS Y OBSTÁCULOS

- Si el LLM informa al usuario que sus notas deben ser enviadas al Departamento de Control de Estudios (mencionando a <alexis.ruiz@dawere.com> o el departamento), asigna la etiqueta 'requiere_revision_control_estudios'.
- Si el usuario indica no tener notas certificadas y el LLM le ofrece o el usuario pregunta por las "pruebas de convalidación" para suplir este requisito, asigna la etiqueta 'necesita_convalidacion'.
- Si el usuario menciona explícitamente tener problemas para conseguir las notas certificadas, el documento de identidad u otro documento esencial para la inscripción, asigna la etiqueta 'dificultad_documentacion'.
- Si el usuario pregunta varias veces por el costo de los programas, planes de pago, o si menciona que el precio es un factor muy importante o una posible barrera, asigna la etiqueta 'preocupacion_costo'.
- Si el usuario solicita explícitamente hablar por teléfono con un asesor o pide el número de Ray Martínez, asigna la etiqueta 'solicitud_llamada_humano'.
- Si el usuario reporta un problema técnico específico con la plataforma Dawere durante el proceso de inscripción guiado (ej. "no me deja registrarme", "la página de pago da error", "no puedo subir mi perfil"), asigna la etiqueta 'consulta_tecnica_plataforma'.
- Si el LLM responde a una pregunta relevante para el proceso de admisión (ej. sobre un requisito específico, detalle de un programa) indicando que no tiene la información o que no puede ayudar con eso, y esa información SÍ debería estar en su conocimiento, asigna la etiqueta 'informacion_no_encontrada_relevante'.
- Si la solicitud del usuario es claramente inviable según las políticas descritas en el prompt o KB (ej. quiere inscribir a un niño de 9 años, quiere convalidar Middle School USA, quiere un programa que no existe), asigna la etiqueta 'caso_fuera_de_politica'.

# ETIQUETAS BASADAS EN EL RESULTADO/SENTIMIENTO DE LA INTERACCIÓN

- Si el LLM logra responder de manera completa y clara una duda o pregunta compleja del usuario sobre los programas o el proceso de admisión, asigna la etiqueta 'resolucion_exitosa_duda'.
- Si el usuario expresa de forma explícita "gracias, muy útil", "excelente explicación", "me quedó claro", o un sentimiento positivo similar tras una respuesta del LLM, asigna la etiqueta 'usuario_satisfecho'.
- Si el usuario expresa repetidamente "no entiendo", "esto es confuso", o muestra signos claros de frustración con las respuestas o el proceso, asigna la etiqueta 'usuario_confundido_o_frustrado'.
- Si el LLM, basándose en la complejidad de la consulta o por no poder resolverla, sugiere al usuario contactar directamente a Ray Martínez o utilizar el sistema de tickets de ayuda (para estudiantes existentes), asigna la etiqueta 'escalado_a_humano_sugerido_por_bot'.

# ETIQUETAS ADICIONALES DEL EJEMPLO (Adaptadas)

- Si la respuesta del LLM indica que no tiene información suficiente para responder a la consulta del usuario o la respuesta es irrelevante para los servicios de Dawere, asigna la etiqueta 'bot_sin_respuesta_adecuada'.
- Si el usuario proporciona información de contacto completa y válida (nombre, correo Y teléfono) y muestra claro interés, asigna la etiqueta 'lead_valioso_capturado'.


---

| id | nombre de la etiqueta      | descripcion                                                                                                                                                              |
|----|----------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 1  | `consulta_inicial`         | Si es el inicio de la conversación y el usuario está haciendo preguntas generales sobre Dawere o sus programas, sin especificar uno.                                         |
| 2  | `interes_prog_especifico`  | Si el usuario ya ha enfocado su interés en uno o más programas particulares y pregunta detalles sobre ellos (costos, duración, requisitos de ESE programa).                   |
| 3  | `interes_inscripcion`      | Si el usuario pregunta explícitamente "cómo me inscribo", "quiero inscribirme", "cuáles son los pasos para la inscripción", o muestra una intención clara de iniciar el proceso. |
| 4  | `proceso_inscrip_activo`   | Si el LLM está actualmente guiando al usuario a través de alguno de los 9 pasos del "PROCESO DE INSCRIPCION" detallado en el prompt.                                        |
| 5  | `inscrip_completada`       | Si el usuario confirma haber completado todos los pasos del proceso de inscripción, incluyendo el agendamiento de la llamada de inducción.                                   |
| 6  | `inscrip_pospuesta`        | Si el usuario muestra interés en inscribirse pero indica explícitamente que lo hará en otro momento o más adelante.                                                          |
| 7  | `sin_interes_actual`       | Si el usuario indica claramente que no desea continuar con la inscripción o que los programas no son adecuados para él/ella en este momento.                                  |
| 8  | `prospecto_representante`  | Si el usuario menciona que está consultando "para mi hijo", "para mi hija", "para un representado", o usa un lenguaje similar que indique que no es el estudiante final.    |
| 9  | `prospecto_estud_directo`  | Si el usuario indica que la consulta es "para mí", "soy yo el que quiere estudiar", o usa un lenguaje similar que indique que es el futuro estudiante.                       |
| 10 | `prospecto_adulto`         | Si el usuario que se identifica como el estudiante directo menciona tener 18 años o más, o habla de combinar estudios con trabajo o responsabilidades familiares.          |
| 11 | `prospecto_menor_edad_lim` | Si el usuario indica que el estudiante tiene entre 11 y 13 años inclusive.                                                                                               |
| 12 | `prospecto_notas_extranjero` | Si el usuario menciona que sus notas certificadas o estudios previos son de un país que no es Estados Unidos.                                                              |
| 13 | `prospecto_con_titulo_prev`| Si el usuario menciona que ya posee un título de bachiller, preparatoria o high school.                                                                                   |
| 14 | `prospecto_necesidad_esp`  | Si el usuario menciona explícitamente motivaciones como "bullying", "soy atleta", "mi hijo es artista", "tiene TDAH", "viajamos mucho", "vivimos lejos de un colegio", o "necesita educación especial" como razón para buscar Dawere. |
| 15 | `prog_bto_online_usa`      | Si la consulta o respuesta del LLM se centra principalmente en el programa "Bachillerato Online USA" (el estándar de 7mo a 12mo).                                            |
| 16 | `prog_bto_acelerado_usa`   | Si la consulta o respuesta del LLM se centra principalmente en el programa "Bachillerato Online Acelerado USA".                                                            |
| 17 | `prog_bto_adultos_usa`     | Si la consulta o respuesta del LLM se centra principalmente en el programa "Bachillerato Online Adultos USA".                                                              |
| 18 | `prog_doble_tit_usa`       | Si la consulta o respuesta del LLM se centra principalmente en el programa "Doble Titulación Bachillerato USA".                                                             |
| 19 | `prog_us_dual_diploma`     | Si la consulta o respuesta del LLM se centra principalmente en el programa "US Dual High School Diploma".                                                                   |
| 20 | `prog_pruebas_convalid`    | Si la consulta o respuesta del LLM se centra principalmente en las "Pruebas de convalidación" como el servicio o "programa" que el usuario necesita seleccionar en la plataforma para ser ubicado. |
| 21 | `requiere_rev_ctrl_estud`  | Si el LLM informa al usuario que sus notas deben ser enviadas al Departamento de Control de Estudios (mencionando a <alexis.ruiz@dawere.com> o el departamento).             |
| 22 | `necesita_convalidacion`   | Si el usuario indica no tener notas certificadas y el LLM le ofrece o el usuario pregunta por las "pruebas de convalidación" para suplir este requisito.                      |
| 23 | `dificultad_documentacion` | Si el usuario menciona explícitamente tener problemas para conseguir las notas certificadas, el documento de identidad u otro documento esencial para la inscripción.        |
| 24 | `preocupacion_costo`       | Si el usuario pregunta varias veces por el costo de los programas, planes de pago, o si menciona que el precio es un factor muy importante o una posible barrera.           |
| 25 | `solicitud_llamada_humano` | Si el usuario solicita explícitamente hablar por teléfono con un asesor o pide el número de Ray Martínez.                                                                  |
| 26 | `consulta_tecnica_plat`    | Si el usuario reporta un problema técnico específico con la plataforma Dawere durante el proceso de inscripción guiado (ej. "no me deja registrarme", "la página de pago da error", "no puedo subir mi perfil"). |
| 27 | `info_no_encontrada_relev` | Si el LLM responde a una pregunta relevante para el proceso de admisión (ej. sobre un requisito específico, detalle de un programa) indicando que no tiene la información o que no puede ayudar con eso, y esa información SÍ debería estar en su conocimiento. |
| 28 | `caso_fuera_de_politica`   | Si la solicitud del usuario es claramente inviable según las políticas descritas en el prompt o KB (ej. quiere inscribir a un niño de 9 años, quiere convalidar Middle School USA, quiere un programa que no existe). |
| 29 | `resolucion_exitosa_duda`  | Si el LLM logra responder de manera completa y clara una duda o pregunta compleja del usuario sobre los programas o el proceso de admisión.                                |
| 30 | `usuario_satisfecho`       | Si el usuario expresa de forma explícita "gracias, muy útil", "excelente explicación", "me quedó claro", o un sentimiento positivo similar tras una respuesta del LLM.        |
| 31 | `usuario_confund_frustrado`| Si el usuario expresa repetidamente "no entiendo", "esto es confuso", o muestra signos claros de frustración con las respuestas o el proceso.                               |
| 32 | `escalado_humano_sug_bot`  | Si el LLM, basándose en la complejidad de la consulta o por no poder resolverla, sugiere al usuario contactar directamente a Ray Martínez o utilizar el sistema de tickets de ayuda (para estudiantes existentes). |
| 33 | `bot_sin_resp_adecuada`    | Si la respuesta del LLM indica que no tiene información suficiente para responder a la consulta del usuario o la respuesta es irrelevante para los servicios de Dawere.       |
| 34 | `lead_valioso_capturado`   | Si el usuario proporciona información de contacto completa y válida (nombre, correo Y teléfono) y muestra claro interés.                                                     |