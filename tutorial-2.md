# Chase the Pizza

### @explicitHints true

## {Introduction @showdialog}

![Game animation](https://pxt.azureedge.net/blob/240e4e29baa921d3d9ecfda531f54d648d3319fb/static/tutorials/chase-the-pizza.gif)

In diesem Tutorial wirst du ein Spiel mit 2 Sprites erstellen: einem ``||sprites:Spieler||``-Sprite und einem ``||sprites:Essen||``-Sprite. Das Ziel des Spiels ist es, so viel Pizza wie möglich zu essen, bevor die Zeit abläuft! Jedes Mal, wenn dein Spieler die Pizza einfängt, erhältst du Punkte und der Countdown wird zurückgesetzt.

## {Step 1}

Setze zuerst die ``||scene:Hintergrundfarbe||`` auf eine Farbe, die dir gefällt. Um zu sehen, wie das in deinem Spiel aussieht, schaue dir das Fenster des Game-Simulators an.

```typescript
scene.setBackgroundColor(0)
```

## {Step 2}

Füge den Code hinzu, um ein Sprite zu ``||sprites:erstellen||`` und weise ihm den Variablennamen ``||variables(noclick):meinSprite||`` zu. Verwende für den ``||sprites:Sprite-Typ||`` den ``||sprites:Spieler||``.

```typescript
let mySprite: Sprite = null
scene.setBackgroundColor(7)
mySprite = sprites.create(img`
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

## {Step 3}

Zeichne deinen ``||sprites:Spieler||``-Charakter, indem du den Bildeditor für ``||variables(sprites):meinSprite||`` verwendest. Benutze die Farbpalette und Designwerkzeuge, um ein Bild auf der Leinwand zu zeichnen. Klicke auf **Fertig**, wenn du fertig bist.

![Bildeditor](https://pxt.azureedge.net/blob/425891a14de9d825142d50bef4b61e4e9ab5d5cc/static/tutorials/chase-the-pizza/image-editor-js.gif)

## {Step 4}

Füge den Code hinzu, um ``||controller:meinSprite zu bewegen||`` mit dem ``||controller:Controller||``.

```typescript
scene.setBackgroundColor(7)
let mySprite = sprites.create(img`
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
controller.moveSprite(mySprite)
```

## {Step 5}

Just like with ``||variables(noclick):mySprite||``, ``||create a sprite||`` again and set it to the a variable named
``||variables(noclick):pizza||``. This time, set the ``||sprites:sprite kind||`` to ``||sprites:food||``. This will
be the **pizza** sprite in our game.

```typescript
scene.setBackgroundColor(7)
let mySprite = sprites.create(img`
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
controller.moveSprite(mySprite)
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

## {Step 6}

Use the image editor for ``||variables(noclick):pizza||`` and then select the **Gallery** view. Scroll to find the image of a small pizza (or any other image you like!) and select it to load into the image editor.

![Bildeditor](https://pxt.azureedge.net/blob/88d1aa236c0840db48e0a9c9932b875ed85bf339/static/tutorials/chase-the-pizza/image-gallery-spy.gif)

## {Step 7 @resetDiff}

Add a ``||sprites:on overlap||`` event to your code. Set the ``||sprites:sprite kind||`` that cooresponds to
``otherSprite`` as ``||sprites:Food||``.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {

})
```

## {Step 8}

When our ``||sprites:Player||`` overlaps with the ``||variables(noclick):pizza||`` sprite, let's add a point to our game score. Pun in the code to ``||info:change score by||`` 1`.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
})
```

## {Step 9}

Let's set the position for ``||variables(noclick):pizza||`` to random locations around the screen. We use
``otherSprite`` and ``||sprites:set its position||``. Righy now, just use `0` for both `x` and `y`.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
    otherSprite.setPosition(0, 0)
})
```

## {Step 10}

Put in code for the `x` and `y` positions of ``otherSprite`` to use a ``||math:pick a random||`` number.
The Arcade game screen is `160` pixels wide, and `120` pixels high. In the first ``||math:pick random||``
in the `x` coordinate of the ``||sprites:otherSprite position||``, change the maximum value from **0** to
**160**. In the second ``||math:pick random||`` in the ``y`` coordinate, change the maximum value from
**0** to **120**.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
    otherSprite.setPosition(randint(0, 160), randint(0, 120))
})
```

## {Step 11}

Let's restart our countdown each time. Add the code to ``||info:start countdown||`` and make the countdown
count be `10`.

```typescript
sprites.onOverlap(SpriteKind.Player, SpriteKind.Food, function (sprite, otherSprite) {
	info.changeScoreBy(1)
    otherSprite.setPosition(randint(0, 160), randint(0, 120))
    info.startCountdown(10)
})
```

## {Complete @resetDiff}

Congratulations, you have completed your game! Use the Game Simulator to play by moving your ``||sprites:Player||`` around the screen to try and eat as much pizza as possible before the time runs out. What's your high score?

```typescript
scene.setBackgroundColor(7)
let mySprite = sprites.create(img`
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
controller.moveSprite(mySprite)
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
