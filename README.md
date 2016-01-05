# TXSTEP

For the software see http://www.txstep.de/

## Pattern-matching
https://tustep.wikispaces.com/Neue+Konventionen.

### Concatenation of tags with _
    <char-group name="ok">?{-}{{}}%</char-group>

ok für ohne Klammern, das sind alle Zeichen ("?") außer ("{-}") den Spitzklammern ("{{" und "}}") und außer %

Das % ist in die char-group als Ausnahme mit aufgenommen, damit nicht auch in der Zeichenfolge

    T%<est i%>st

(wo die Spitzklammern Bestandteil der TUSTEP-Codierung für e mit Zirkumflex und s mit Hacek sind) das Blank ausgetauscht wird. 

### Delete certain tags
                        <string-pair>
                            <search-string>{{{0}/orig*}}</search-string>
                            <replacement-string/>
                        </string-pair>


## &lt;transform> (#KOPIERE)

### Text units
        <define-text-units>
            <text-unit-start>
                <comparison-table>
                    <exclusion-string>{{/</exclusion-string>
                    <comparison-string>{{</comparison-string>
                </comparison-table>
            </text-unit-start>
        </define-text-units>
 
Appends lines to the previous line if they do not begin with start-tags.

## faustii9+.xml
Compare more than 9 (xml-)sources, output = diff-files with TEI inspired tags; from these files, after cumulating and sorting, a synopsis of the variant readings is generated