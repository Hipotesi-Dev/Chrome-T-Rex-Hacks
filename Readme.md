# Google Chrome Dino Hacks
Para entrar en el Dinosaurio sin cortar el cable del wifi: [chrome://dino/](chrome://dino/)
Scripts desarrollados por [Edu Olivares](http://www.hipotesi.org)
--
## Como instalar el hack
_Para "Instalar el hack" simplemente tienes que ir a la consola de desarrolladores (F12 o inspeccionar) y buscar la pestaña "Consola". Donde pegaremos el código que nosotros queramos._

![Consola de Dessarrolladores](https://github.com/Hipotesi-Dev/Chrome-T-Rex-Hacks/blob/main/Consola.png)

## Códigos

-  Invencibilidad (_Cualquiera de los dos funciona_)
`Runner.instance_.gameOver = function(){};`
`Runner.prototype.gameOver = function() {}`
- Para quitar invencibilidad
`var original = Runner.prototype.gameOver`
- Aumento de Velocidad
`Runner.instance_.setSpeed(50)` 

  > El 50 puedes cambialo al numero que quieras

- Super salto
`Runner.instance_.Rex.setJumpVelocity(1000)`
  > El 1000 puedes cambialo al numero que quieras
 
- Sin obstáculos
`Runner.instance_.playingIntro = true`
- Añadir nubes de fondo
`Runner.instance_.horizon.addCloud()`
- Quitar EL PRIMER obstáculo
`Runner.instance_.horizon.removeFirstObstacle()`
- Sacar la luna
`Runner.instance_.inverted = true`
- Multiplicador de puntos
`Runner.instance_.msPerFrame = 0.01`

  > Puedes cambiar el 0,01 pero recomiendo dejarlo como esta

- Añadir puntos
`Runner.instance_.distanceRan = 900`

  > Puedes cambiar el 900 por la puntuación que tu quieras
