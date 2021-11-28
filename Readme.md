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

# EL BOT
A ver esto ya es un bot en condiciones, salta corre y hace todo solo, tu simplemente no toques nada. La instalación es la misma que los codigos.

``
function keyDown(e) {
  Podium = {};
  var n = document.createEvent("KeyboardEvent");
  Object.defineProperty(n, "keyCode", {
    get: function () {
      return this.keyCodeVal;
    },
  }),
    n.initKeyboardEvent
      ? n.initKeyboardEvent(
          "keydown",
          !0,
          !0,
          document.defaultView,
          e,
          e,
          "",
          "",
          !1,
          ""
        )
      : n.initKeyEvent(
          "keydown",
          !0,
          !0,
          document.defaultView,
          !1,
          !1,
          !1,
          !1,
          e,
          0
        ),
    (n.keyCodeVal = e),
    document.body.dispatchEvent(n);
}
function keyUp(e) {
  Podium = {};
  var n = document.createEvent("KeyboardEvent");
  Object.defineProperty(n, "keyCode", {
    get: function () {
      return this.keyCodeVal;
    },
  }),
    n.initKeyboardEvent
      ? n.initKeyboardEvent(
          "keyup",
          !0,
          !0,
          document.defaultView,
          e,
          e,
          "",
          "",
          !1,
          ""
        )
      : n.initKeyEvent(
          "keyup",
          !0,
          !0,
          document.defaultView,
          !1,
          !1,
          !1,
          !1,
          e,
          0
        ),
    (n.keyCodeVal = e),
    document.body.dispatchEvent(n);
}
setInterval(function () {
  Runner.instance_.horizon.obstacles.length > 0 &&
    (Runner.instance_.horizon.obstacles[0].xPos <
      25 * Runner.instance_.currentSpeed -
        Runner.instance_.horizon.obstacles[0].width / 2 &&
      Runner.instance_.horizon.obstacles[0].yPos > 75 &&
      (keyUp(40), keyDown(38)),
    Runner.instance_.horizon.obstacles[0].xPos <
      30 * Runner.instance_.currentSpeed -
        Runner.instance_.horizon.obstacles[0].width / 2 &&
      Runner.instance_.horizon.obstacles[0].yPos <= 75 &&
      keyDown(40));
}, 5);
``
