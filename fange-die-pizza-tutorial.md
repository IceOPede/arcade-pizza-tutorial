# Fange die Pizza

## {Einführung @showdialog}

![Game animation](https://pxt.azureedge.net/blob/240e4e29baa921d3d9ecfda531f54d648d3319fb/static/tutorials/chase-the-pizza.gif)

In diesem Tutorial wirst du ein Spiel mit 2 Sprites erstellen: einem ``||sprites:Spieler||``-Sprite und einem ``||sprites:Essen||``-Sprite. Das Ziel des Spiels ist es, so viel Pizza wie möglich zu essen, bevor die Zeit abläuft! Jedes Mal, wenn dein Spieler die Pizza einfängt, erhältst du Punkte und der Countdown wird zurückgesetzt.

## {Schritt 1}

Setze zuerst die ``||scene:Hintergrundfarbe||`` auf eine Farbe, die dir gefällt. Um zu sehen, wie das in deinem Spiel aussieht, schaue dir das Fenster des Game-Simulators an.

```typescript
scene.setBackgroundColor(0)
```

## {Schritt 2}

Füge den Code hinzu, um ein Sprite zu ``||sprites:erstellen||`` und weise ihm den Variablennamen ``||variables(noclick):meinSprite||`` zu. Verwende für den ``||sprites:SpriteKind||`` den ``||sprites:SpriteKind.Player||``.

```typescript
scene.setBackgroundColor(7)
let meinSprite = sprites.create(img`
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

## {Schritt 3}

Zeichne deinen ``||sprites:Spieler||``-Charakter, indem du den Bildeditor für ``||variables(noclick):meinSprite||`` verwendest. Benutze die Farbpalette und Designwerkzeuge, um ein Bild auf der Leinwand zu zeichnen. Klicke auf **Fertig**, wenn du fertig bist.

![Bildeditor](https://pxt.azureedge.net/blob/425891a14de9d825142d50bef4b61e4e9ab5d5cc/static/tutorials/chase-the-pizza/image-editor-js.gif)

## {Schritt 4}

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
// @highlight
controller.moveSprite(meinSprite)
```

## {Schritt 5}

Genau wie bei ``||variables(noclick):meinSprite||``, erstelle erneut ein Sprite und setze den Variablenamen auf ``||variables(noclick):pizza||``. Dieses Mal setze die ``||sprites:SpriteKind||`` auf ``||sprites:SpriteKind.Food||``. Dies wird das **Pizza**-Sprite in unserem Spiel sein.

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
controller.moveSprite(meinSprite)
// @highlight
let pizza = sprites.create(img`
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

## {Schritt 6}

Verwende den Bildeditor für ``||variables(noclick):pizza||`` und wähle dann die Galerie Ansicht aus. Scrolle, um das Bild einer kleinen Pizza (oder ein beliebiges anderes Bild, das dir gefällt!) zu finden, und wähle es aus, um es in den Bildeditor zu laden.

![Bildeditor](https://pxt.azureedge.net/blob/88d1aa236c0840db48e0a9c9932b875ed85bf339/static/tutorials/chase-the-pizza/image-gallery-spy.gif)

## {Schritt 7 @resetDiff}

Füge deinem Code ein ``||sprites:Beim Überlappen||`` Ereignis hinzu. Setze die ``||sprites:SpriteKind||`` des zweiten Attributes auf``||sprites:SpriteKind.Food||``.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {

})
```

## {Schritt 8}

Wenn unser ``||sprites:Spieler||`` mit dem ``||variables(noclick):pizza||``-Sprite überlappt, fügen wir einen Punkt zu unserer Spielwertung hinzu. Füge den folgenden Code ein: ``||info:ändere Spielwertung um||`` 1.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	// @highlight
	info.changeScoreBy(1)
})
```

## {Schritt 9}

Nun wollen wir die Position für ``||variables(noclick):pizza||`` auf eine zufällige Positionen auf dem Bildschirm setzten. Wir verwenden otherSprite und ``||sprites:setze seine Position||``. Verwenden Sie vorerst einfach 0 sowohl für x als auch für y.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
	// @highlight
	otherSprite.setPosition(0, 0)
})
```

## {Schritt 10}

Nun fügen wir den Code hinzu, um die x- und y-Positionen des otherSprites auf einen zufälligen Wert zusetzten. Dafür verwenden wir eine ``||math:zufälligen||`` Zahl Generator. Der Arcade-Spielbildschirm ist 160 Pixel breit und 120 Pixel hoch. Im ersten ``||math:zufälligen||`` Wert in der x-Koordinate der ``||sprites:Position des otherSprite||``, ändere den maximalen Wert von **0** zu **160**. Im zweiten ``||math:zufälligen||`` Wert in der y-Koordinate ändere den maximalen Wert von **0** zu 120.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
	// @highlight
	otherSprite.setPosition(randint(0, 160), randint(0, 120))
})
```

## {Schritt 11}

Starte den Countdown jedes mal neu, wenn sich die Sprites überlappen. Fügen den Code hinzu, um den Countdown mit ``||info:Countdown starten||`` zu starten und setzte den Wert auf 10.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
	otherSprite.setPosition(randint(0, 160), randint(0, 120))
	// @highlight
	info.startCountdown(10)
})
```

## {Complete @resetDiff}

Herzlichen Glückwunsch, du hast dein Spiel abgeschlossen! Verwende den Spiel-Simulator, um zu spielen, indem du deinen ``||sprites:Spieler||`` über den Bildschirm bewegst und versuchst, so viel Pizza wie möglich zu essen, bevor die Zeit abläuft. Was ist deine höchste Punktzahl?

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
controller.moveSprite(meinSprite)
let pizza = sprites.create(img`
. . . . . . b b b b . . . . . .
. . . . . . b 4 4 4 b . . . . .
. . . . . . b b 4 4 4 b . . . .
. . . . . b 4 b b b 4 4 b . . .
. . . . b d 5 5 5 4 b 4 4 b . .
. . . . b 3 2 3 5 5 4 e 4 4 b .
. . . b d 2 2 2 5 7 5 4 e 4 4 e
. . . b 5 3 2 3 5 5 5 5 e e e e
. . b d 7 5 5 5 3 2 3 5 5 e e e
. . b 5 5 5 5 5 2 2 2 5 5 d e e
. b 3 2 3 5 7 5 3 2 3 5 d d e 4
. b 2 2 2 5 5 5 5 5 5 d d e 4 .
b d 3 2 d 5 5 5 d d d 4 4 . . .
b 5 5 5 5 d d 4 4 4 4 . . . . .
4 d d d 4 4 4 . . . . . . . . .
4 4 4 4 . . . . . . . . . . . .
`, SpriteKind.Food)

sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
	otherSprite.setPosition(randint(0, 160), randint(0, 120))
	info.startCountdown(10)
})
```
