Esta aplicación ha sido realizado con Android Studio Koala Feature Drop | 2024.1.2, por un equipo de estudiantes de FP.
Esta aplicación usa 6 clases de java, de las cuales 4 de ellas forman varias Activities.
Activities:
1) MainActivity
   Es el menu principal, con 2 botones, uno para pasar a la WelcomeActivity y el otro para salir.
    Esta activity usa un metodo OnClick(), el cual contiene un switch con dos opciones, cada opción se activara según el boton q se pulse, para pasar a la       siguiente actividad se usa un intent, y un startActivity(intent), y para salir de la aplicación un System.exit(0).
3) WelcomeActivity
   Se encarga de gestionar la interacción del usuario con la pantalla, mostrando las preguntas, recibiendo las respuestas y actualizando la puntuación.
   Es un textView explicando el funcionamiento de la aplicación, con un spinner para elegir la dificultad el cual usa un adapter para pasarle los items y       luego usamos un metodo llamado onItemSelected() pasa saber q item estas seleccionando.
5) PlayActivity
   Aqui es donde se realiza el juego, utilizando distintas clases ya creadas como Question.java y QuestionDB.java, las preguntas y sus respuestas
   son mostradas en un orden de manera aleatoria.
   Usamos un constructor, el cual recibe un nivel de dificultad como parámetro y crea un arreglo de objetos Question correspondiente a esa dificultad, los 
   métodos easyquestions(), mediumquestions(), hardquestions(): Contienen listas de preguntas predefinidas, cada una con su enunciado, opciones de     
   respuesta y respuesta correcta y el método answer_splitter() divide las respuestas de cada pregunta, que están concatenadas en una sola cadena, en una 
   lista de opciones individuales.
   
7) ResultActivity
   Es donde se felicita al jugador en caso de ganar o se indica q ha perdido a traves de una imagen y un sonido según el caso q se de.
   Para saber si el jugador ha ganado o ha perdido, necesitamos q el intent reciva un int, si es = 10, se ejecuta el metodo sonidoVictoria(), q ejecuta un
   sonido, para esto hemos usado una clase MediaPlayer, tambien cambiamos la imagen y el texto del TextView. Pero si el intent es menor de 10, se ejecuta 
   el metodo sonidoDerrota() q funciona igual q el metodo sonidoVictoria(), tambien se cambia la imagen y el TextView.
