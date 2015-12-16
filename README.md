# TXSTEP

For the software see http://www.txstep.de/.

## Pattern-matching
https://tustep.wikispaces.com/Neue+Konventionen.

## Concatenation of tags with _
    <char-group name="ok">?{-}{{}}%</char-group>

ok für ohne Klammern, das sind alle Zeichen ("?") außer ("{-}") den Spitzklammern ("{{" und "}}") und außer %

Das % ist in die char-group als Ausnahme mit aufgenommen, damit nicht auch in der Zeichenfolge "T%<est i%>st" (wo die Spitzklammern Bestandteil der TUSTEP-Codierung 
            für e mit Zirkumflex und s mit Hacek sind) das Blank ausgetauscht wird. 

