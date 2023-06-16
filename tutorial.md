# Spielprogrammierung

### @explicitHints true

## Einführung @showdialog

![Spielanimation](/static/tutorials/chase-the-pizza.gif)

In diesem Tutorial wirst du ein Spiel mit 2 Sprites erstellen: einem ``||sprites:Spieler||``-Sprite und einem ``||sprites:Essen||``-Sprite. Das Ziel des Spiels ist es, so viel Pizza wie möglich zu essen, bevor die Zeit abläuft! Jedes Mal, wenn dein Spieler die Pizza einfängt, erhältst du Punkte und der Countdown wird zurückgesetzt.

## Schritt 1

Setze zuerst die ``||scene:Hintergrundfarbe||`` auf eine Farbe, die dir gefällt. Um zu sehen, wie das in deinem Spiel aussieht, schaue dir das Fenster des Game-Simulators an.

```typescript
scene.setBackgroundColor(0)
```

## Schritt 2

Füge den Code hinzu, um ein Sprite zu ``||sprites:erstellen||`` und weise ihm den Variablennamen ``||variables(noclick):meinSprite||`` zu. Verwende für den ``||sprites:Sprite-Typ||`` den ``||sprites:Spieler||``.

```typescript
let meinSprite: Sprite = null
scene.setBackgroundColor(7)
meinSprite = sprites.create(img`
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
`, SpriteKind.Player)
```

## Schritt 3

Zeichne deinen ``||sprites:Spieler||``-Charakter, indem du den Bildeditor für ``||variables(sprites):meinSprite||`` verwendest. Benutze die Farbpalette und Designwerkzeuge, um ein Bild auf der Leinwand zu zeichnen. Klicke auf **Fertig**, wenn du fertig bist.

![Bildeditor](/static/tutorials/chase-the-pizza/image-editor-js.gif)

## Schritt 4

Füge den Code hinzu, um ``||controller:meinSprite zu bewegen||`` mit dem ``||controller:Controller||``.

```typescript
scene.setBackgroundColor(7)
let meinSprite = sprites.create(img`
. . . . . 5 5 5 5 5 5 . . . . .
. . . 5 5 5 5 5 5 5 5 5 5 . . .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. 5 5 5 5 5 5 5 5 5 5 5 5 5 5 .
. 5 5 5 f f 5 5 5 5 f f 5 5 5 .
5 5 5 5 f f 5 5 5 5 f f 5 5 5 5
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
5 5 5 5 5 5 5 5 5 5 5 5 5 5 5 5
5 5 f 5 5 5 5 5 5 5 5 5 5 f 5 5
5 5 5 f 5 5 5 5 5 5 5 5 f 5 5 5
. 5 5 5 f 5 5 5 5 5 5 f 5 5 5 .
. 5 5 5 5 f f f f f f 5 5 5 5 .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. . . 5 5 5 5 5 5 5 5 5 5 . . .
. . . . . 5 5 5 5 5 5 . . . . .
`, SpriteKind.Player)
```

## Schritt 5

Nun fügen wir das Pizza-Sprite hinzu. Füge den Code hinzu, um ein neues Sprite ``||sprites:erstellen||`` und ihm den Namen ``||variables(noclick):pizza||`` zuzuweisen. Verwende das ``||sprites:Food||`` für die ``||sprites:Sprite-Art||``.

```typescript
let pizza: Sprite = null
pizza = sprites.create(img`
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
`, SpriteKind.Food)
```

## Schritt 6

Ähnlich wie beim Spieler-Sprite kannst du auch das Pizza-Sprite im Bildeditor zeichnen. Verwende die Farbpalette und Designwerkzeuge, um ein Bild für das Pizza-Sprite zu erstellen. Klicke auf **Fertig**, wenn du fertig bist.

![Bildeditor](/static/tutorials/chase-the-pizza/image-editor-js.gif)

## Schritt 7

Wir wollen das Pizza-Sprite an einer zufäll

igen Position auf dem Bildschirm anzeigen lassen. Füge den folgenden Code hinzu, um das zu erreichen:

```typescript
pizza.setPosition(Math.randomRange(0, scene.screenWidth()), Math.randomRange(0, scene.screenHeight()))
```

## Schritt 8

Jetzt müssen wir dem Spieler ermöglichen, die Pizza zu fangen. Füge den folgenden Code hinzu, um das zu erreichen:

```typescript
controller.moveSprite(meinSprite)
```

## Schritt 9

Jedes Mal, wenn der Spieler die Pizza berührt, möchten wir die Punktzahl erhöhen und das Pizza-Sprite an eine neue zufällige Position bewegen. Füge den folgenden Code hinzu, um das zu erreichen:

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (spieler: Sprite, pizza: Sprite) {
    info.changeScoreBy(1)
    pizza.setPosition(Math.randomRange(0, scene.screenWidth()), Math.randomRange(0, scene.screenHeight()))
})
```

## Schritt 10

Schließlich wollen wir einen Countdown hinzufügen, um das Spiel zu begrenzen. Füge den folgenden Code hinzu, um einen Countdown von 10 Sekunden zu erstellen:

```typescript
let countdown = 10
game.onUpdate(function () {
    countdown += -1
    if (countdown <= 0) {
        game.over(true)
    }
})
```

## Schritt 11

Du hast es geschafft! Du hast dein eigenes Spiel erstellt. Klicke auf **Ausführen**, um dein Spiel zu testen. Versuche so viele Pizza-Stücke wie möglich zu fangen, bevor die Zeit abläuft.

```typescript
scene.setBackgroundColor(0)
let meinSprite = sprites.create(img`
. . . . . 5 5 5 5 5 5 . . . . .
. . . 5 5 5 5 5 5 5 5 5 5 . . .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. . 5 5 5 5 5 5 5 5 5 5 5 5 . .
. . . 5 5 5 5 5 5 5 5 5 5 . . .
. . . . 5 5 5 5 5 5 5 5 . . . .
. . . . . 5 5 5 5 5 5 . . . . .
. . . . . . 5 5 5 5 . . . . . .
. . . . . . . 5 5 . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
`, SpriteKind.Player)
let pizza = sprites.create(img`
. . . . . . . .

 . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
. . . . . . . . . . . . . . . .
`, SpriteKind.Food)
pizza.setPosition(Math.randomRange(0, scene.screenWidth()), Math.randomRange(0, scene.screenHeight()))
controller.moveSprite(meinSprite)
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (spieler: Sprite, pizza: Sprite) {
    info.changeScoreBy(1)
    pizza.setPosition(Math.randomRange(0, scene.screenWidth()), Math.randomRange(0, scene.screenHeight()))
})
let countdown = 10
game.onUpdate(function () {
    countdown += -1
    if (countdown <= 0) {
        game.over(true)
    }
})
```