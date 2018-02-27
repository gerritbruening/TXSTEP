# TXSTEP

For the software see
* http://www.txstep.de/
* https://tustep.wikispaces.com/TXSTEP

For the underlying technology see
* http://www.tustep.uni-tuebingen.de/
* http://wiki.tei-c.org/index.php/Publishing_printed_critical_editions_from_TEI#using_TUSTEP

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
Compare more than 9 (xml-)sources, output = diff-files with TEI inspired tags; from these files, after cumulating and sorting, a synopsis of the variant readings is generated.

## fff2xml.xml
Provisional conversion from FFF to XML. For the general needs, see https://github.com/gerritbruening/muo#plan-of-action.

Current structure of the script:

1. insert basic markup
2. remove redundant `<Erstausgabe>` page breaks following after each `<Kapiteltitel>`
3. remove redundant `<Absatzanfang/>` following after each `<Erstausgabe>` page break
4. insert `<Absatzanfang/>` where `<Erstausgabe>` page breaks coincide with the start of a new paragraph ([generated](https://github.com/gerritbruening/TXSTEP/blob/master/xxsbab.xml) from a handcrafted list)
5. insert `<Versal>` ([generated](https://github.com/gerritbruening/TXSTEP/blob/master/xxversal.xml) from a handcrafted list)
6. handling of hyphenation
7. `<Absatzanfang/>` → `<Absatz>...</Absatz>`
8. page breaks at the end of paragraphs: move them from inside of a paragraph to outside of it
9. trim whitespace at the end of paragraphs
10. put apparatus entries in separate records
11. handle the bulk of variants
12. comment out hitherto unhandled FFF markup
13. integrate apparatus into preceding and following records, trim whitespace between app entry and following punctuation characters
14. BYPASS for the generation of a clear reading text close to GA
15. add root element