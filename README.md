# TXSTEP

For the software see http://www.txstep.de/.

## Pattern-matching
https://tustep.wikispaces.com/Neue+Konventionen.

## Concatenation of tags with _
    <char-group name="ok">?{-}{{}}%</char-group>

ok f�r ohne Klammern, das sind alle Zeichen ("?") au�er ("{-}") den Spitzklammern ("{{" und "}}") und au�er %

Das % ist in die char-group als Ausnahme mit aufgenommen, damit nicht auch in der Zeichenfolge "T%<est i%>st" (wo die Spitzklammern Bestandteil der TUSTEP-Codierung 
            f�r e mit Zirkumflex und s mit Hacek sind) das Blank ausgetauscht wird. 

