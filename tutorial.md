# Combination Lock
##Introducktion @showdialog
Wenn du die richtige Tastenkombination (mit Klick auf  Taste A und Klick auf Taste B) eingibst, erfährst du die Kombination für das Zahlenschloss!
## Step 1
Erstelle eine Variable "secret", der beim Start eine vierstellige Zahl (z.B.1234) zugeordnet wird. 
## Step 2
Erstelle eine Variable "key", der beim Start eine sechsstellige Kombination aus A und B (z.B. BBABAA) zugeordnet wird.
```blocks
let key = "BBABAA"
```
```
Damit du einer Variablen Text zuordnen kannst, gehe zu Fortgeschritten / Text
```
## Step 3
Erstelle eine Variable "userkey", der beim Start ein leerer Text zugeordnet wird.

```
Den leeren Text findest du unter Fortgeschritten / Text
```
  
## Step 4
Wenn Knopf A geklickt wird, füge der Variablen "userkey" den Buchstaben A hinzu.
```blocks
input.onButtonPressed(Button.A, function () {
    userkey = "" + userkey + "A"
    
})
```
Zeige außerdem den Buchstaben A an, erzeuge eine Pause von 10 Millisekunden und lösche dann den Bildschirminhalt.
## Step 5
Wiederhole diese Anweisungen für: Wenn Knopf B geklickt wird ...
## Step 6
Erstelle eine Funktion "check-key". Diese Funktion soll überprüfen, ob die Variable "userkey" mit der Variablen "key" übereinstimmt.
## Step 7
Wenn die Variable "userkey" gleich der Variablen "key" ist, soll eine Melodie ertönen und der Wert der Variablen "secret" (unsere Zahlenkombination für das Zahlenschloss!) angezeigt werden.
```blocks
music.startMelody(music.builtInMelody(Melodies.JumpUp), MelodyOptions.Once)
```
## Step 8
Sonst wenn die Variable "userkey" bereits mehr Buchstaben als die Variable "key" enthält ... 
``` blocks
function check_key () {
    
    if (userkey == key) {
        
    } else if (userkey.length > key.length) {
        
    }
}
```
## Step 9
... dann sollen zwei Töne ausgegeben werden, mit den LEDs ein Kreuz angezeigt werden, 2 Sekunden pausiert werden, der Bildschirminhalt gelöscht werden und die Variable "userkey" wieder auf leeren Text gesetzt werden.
## Step 10
Diese Funktion "check-key" muss jetzt bei "Wenn Knopf A geklickt ..." und bei "Wenn Knopf B geklickt ..." am Ende aufgerufen werden.
``` blocks
input.onButtonPressed(Button.A, function () {
    userkey = "" + userkey + "A"
    basic.showString("A ")
    basic.pause(10)
    basic.clearScreen()
    check_key()
})
```
## Step 11
Damit man weiß, dass der micro:bit für die Eingabe bereit ist, wird in dauerhaft (wenn die Länge der Variable user-key 0 ist) eine LED angezeigt.
Diese LED soll blinken! Was muss man daher noch ergänzen?!
```blocks
basic.forever(function () {
    if (userkey.length == 0) {
        led.toggle(4, 4)
        
    }
})
```
## Step 12
Teste jetzt dein Programm! # tutorial
