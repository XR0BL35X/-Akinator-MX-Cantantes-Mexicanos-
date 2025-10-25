Manual de Usuario — “Akinator MX — Cantantes Mexicanos”
1) ¿Qué es?
“Akinator MX — Cantantes Mexicanos” es un juego de adivinanza guiada: tú piensas en un cantante mexicano y el sistema te hace preguntas de SÍ/NO/NO SÉ. Con tus respuestas, calcula probabilidades y adivina automáticamente cuando alcanza ≥ 90% de confianza. Si no acierta, aprende del caso para mejorar la próxima vez.
________________________________________
2) Requisitos
•	Un navegador moderno (Chrome, Edge, Firefox o Safari).
•	El archivo index.html (y, si usas imágenes locales, la carpeta assets/).
•	No requiere instalación ni conexión a servidor: funciona local/offline.
________________________________________
3) Cómo iniciar una partida
1.	Abre index.html en el navegador.
2.	En la parte superior izquierda verás Candidatos, Preguntas y Confianza top.
3.	Haz clic en Iniciar.
o	El juego seleccionará automáticamente la mejor pregunta (la que reduce más la incertidumbre).
________________________________________
4) Cómo se juega (flujo básico)
1.	Lee la pregunta en el panel central (por ejemplo: “¿Canta Ranchera?” o “¿Suele usar sombrero?”).
2.	Responde haciendo clic en uno de los tres botones:
o	SÍ
o	NO
o	NO SÉ (si no estás seguro o no aplica)
3.	El sistema actualiza el ranking de candidatos (lista de posibles artistas con barra de confianza).
4.	Repite hasta que el sistema auto-adivine (≥ 90% de confianza).
o	Aparecerá un cuadro: “Creo que es X (confianza 90+%). ¿Acerté?”
________________________________________
5) Auto-adivinanza (≥ 90%)
•	Automático: No necesitas presionar “Adivinar”.
•	Si aceptas (Sí, acertó), la partida termina con éxito.
•	Si No acertó, el sistema penaliza ese candidato y continúa preguntando para converger a otra opción.
Consejo: si la confianza top sube muy rápido, es porque tus respuestas están encajando claramente con un perfil de la KB.
________________________________________
6) Aprendizaje (cuando el sistema falla)
Si el sistema se equivoca:
1.	En el panel derecho, en Aprendizaje guiado (si el sistema falla):
o	En Quién era, escribe el nombre correcto.
o	(Opcional) Pega una Imagen (URL) del artista.
o	Elige un Atributo clave (genmus, origen, vivo, tipo, etc.).
o	Escribe el Valor del atributo (ej.: ranchera, Jalisco, true, grupo).
2.	Pulsa Aprender diferencia.
o	El juego registra la nueva información y mejora para futuras partidas.
La KB (base de conocimiento) se guarda en tu navegador (localStorage).
________________________________________
7) Agregar cantantes manualmente
En el panel derecho, sección Agregar / Aprender:
1.	Completa Nombre (obligatorio) y, si quieres, Imagen (URL).
2.	Llena campos como Género musical (pop, ranchera, rock, etc.), Época (clásico/moderno/actual), Género (hombre/mujer/mixto), Origen (estado), Tipo (solista/grupo) y booleanos (Vivo, Sombrero, Grammy).
3.	Pulsa Agregar a KB.
Si el nombre ya existe, el sistema te lo avisará para evitar duplicados accidentales.
________________________________________
8) Importar / Exportar la KB
•	Exportar KB: crea un archivo kb_akinator_mx.json con todos los artistas y atributos.
•	Importar KB: selecciona un .json válido para reemplazar la KB actual.
o	Útil para respaldos, compartir con el equipo o subir a otra máquina.
________________________________________
9) Reiniciar / Nueva partida
•	Reiniciar: restablece el conteo de preguntas y el cálculo de probabilidades, pero conserva tu KB aprendida. Úsalo cuando quieras empezar de cero otra adivinanza.
________________________________________
10) Interfaz (qué estás viendo)
•	Pregunta actual: aparece centrada en el panel principal con botones SÍ/NO/NO SÉ.
•	Historial: debajo de la pregunta ves la lista de preguntas realizadas y tus respuestas (Sí/No/No sé).
•	Ranking de candidatos: tarjetas con foto/nombre y una barra de confianza. La tarjeta superior es la hipótesis principal.
•	Indicadores superiores:
o	Candidatos: total de artistas en juego.
o	Preguntas: cuántas has respondido.
o	Confianza top: porcentaje del candidato más probable.
________________________________________
11) Consejos de uso
•	Responde NO SÉ si no tienes certeza: el motor lo entiende como “neutral” y sigue buscando.
•	Imágenes: puedes poner URL en el alta o dejar que use un avatar generado; si usas carpeta assets/, agrega la ruta en la KB (ej.: image: "assets/luismiguel.jpg").
•	Época: usa la taxonomía del juego (clásico / moderno / actual) para que las preguntas sean más claras.
•	Tipo: diferencia solista vs grupo: esto discrimina rápido el conjunto.
________________________________________
12) Solución de problemas
•	No aparecen imágenes:
o	Verifica la ruta/URL de image.
o	En local, confirma que la carpeta assets/ esté al lado de index.html.
o	Si falla la carga, se mostrará un avatar como respaldo.
•	No me adivinó y no sé qué atributo dar:
o	Usa alguno muy distintivo (por ejemplo, tipo=grupo, origen=Jalisco, genmus=ranchera, sombrero=true).
•	Importé una KB y no pasa nada:
o	Asegúrate de que el JSON sea un arreglo de objetos y los atributos tengan nombres válidos (genmus, epoca, genero, origen, tipo, vivo, usa_sombrero, grammy).
•	Ya adivinó y quiero jugar otra vez:
o	Pulsa Reiniciar.
________________________________________
13) ¿Qué hay “debajo del cofre”? 
•	Reglas/Casos: Cada artista es un caso con atributos (reglas implícitas).
•	Encadenamiento hacia adelante: el motor formula la siguiente pregunta calculando la entropía esperada (la que mejor divide candidatos).
•	Probabilístico: cada respuesta actualiza probabilidades por verosimilitud (Sí/No/No sé) y normaliza el ranking.
•	Aprendizaje: cuando falla, solicita nombre + atributo clave y actualiza la KB (persistida en localStorage).
________________________________________

Mini-guía (1 minuto)
1.	Iniciar → responde SÍ/NO/NO SÉ.
2.	Mira el ranking: la barra de confianza sube/baja.
3.	El sistema auto-adivina al llegar a ≥ 90%.
4.	Si falla: llena Aprendizaje guiado (nombre + atributo clave) y Aprender diferencia.
5.	Reiniciar para nueva partida; Exportar/Importar para respaldar la KB.
