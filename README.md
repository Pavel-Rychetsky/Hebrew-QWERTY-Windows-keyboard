# Hebrew-QWERTY-Windows-keyboard

The purpose of this project is to develop Windows keyboard which maps Hebrew letters according their phonetic or visual similarity with English (ASCII) letters.

## Letters

22 Hebrew letters are mapped to 20 keys (because of a, e, i, o, and u are reserved for vowels - see below) following way:

- according phonetic similarity
    - g, d, h, z, t, j, l, m, n, s, c, q, r
- according phonetic similarity of letter with dagesh
    - b, k, p
- according visual similarity
    - x for aleph
    - y for ayin
    - w/W for sin/shin
- specialities
    - v for waw as "w" is  pronounced close to "v" in some languages
    - T for tet (tav is used more frequently)
    - H for chet
    - AltGr (Ctrl+Alt)+s for sin *without* dot
    - f is not used
- the final forms are written with Shift
- the wide forms are written with AltGr (Ctrl+Alt) including final mem

|Key   |Normal|Shift |AltGr (Ctrl+Alt)|
|----- |------|------|------|
|x|א aleph||wide ﬡ|
|b|ב vet/bet|||
|g|ג gimmel|||
|d|ד dalet||wide ﬢ|
|h|ה he|ח chet|wide ﬣ|
|v|ו waw|||
|z*|ז zajin|||
|t|ת tav|ט tet|wide ﬨ|
|j|י yod|||
|k|כ chaf/kaf|ך final|wide ﬤ|
|l|ל lamed||wide ﬥ|
|m|מ mem|ם final|wide ﬦ final|
|n|נ nun|ן final||
|s|ס samech|ש sin/shin (without dot)||
|y*|ע (ayin)|||
|p|פ fe/pe|ף final||
|c|צ tsade|ץ final||
|q|ק qof|||
|r|ר resh||wide ﬧ|
|w|שׂ sin|שׁ shin||
|f||||

(*) Y and Z in QWERTY layout (e.g. US). See Hebrew-QWERTZ-Windows-keyboard project if you are using QWERTZ as you native keyboard.

### Letters with dagesh / mappiq

Because of many modern Hebrew fonts contain special characters for letters with dagesh or mappiq I've decided to implement dagesh as dead key mapped to "." (period)

- e.g. "." followed by b results in בּ
- if neither dagesh nor mappiq is allowed with letter (ayin, chet, final forms instead of pe and kaf) the result is same letter as without dead key; such behaviour is not implemented for wide forms
- "." followed by "." result in separate dagesh (mappiq) - useful in case the font doesn't include letter with dagesh and there is necessary to composite final character
    - such way the dagesh is typed *after* the letter
    - e.g. b followed by two "." results in בּ (looks same as above, but still constructed from two characters)

### Composite sin/shin

If font doesn't contain glyph for sin/shin with dot (very rare) or if you just want to type the sin/shin without dot, you can use

- Shift + s to type ש
- AltGr (Ctrl+Alt) + s to type "  ׂ " - sin dot
- Shift + AltGr (Ctrl+Alt) + s to type " ׁ  " - shin dot

so either

- ש (Shift + s) followed by AltGr (Ctrl+Alt) + s results in שׂ as composite
- ש (Shift + s) followed by Shift + AltGr (Ctrl+Alt) + s results in שׁ as composite

or (more simply by just one key covering both ש and proper dot)

- AltGr (Ctrl+Alt) + w to type שׂ as composite
- Shift + AltGr (Ctrl+Alt) + w to type שׁ as composite

## Vowels

To type nikkud, the vowels - typed after previous consonant - are mapped following way:

|Key   |Normal|Shift |AltGr (Ctrl+Alt)|Shift+AltGr (Ctrl+Alt)|
|-----|-------|------|------|------|
|a| ◌ַ &nbsp;patah| ◌ָ &nbsp;kamats| ◌ֲ &nbsp;hataf patah| ◌ֳ &nbsp;hataf kamats|
|e| ◌ֶ &nbsp;segol | ◌ֵ &nbsp;tsere| ◌ֱ &nbsp;hataf segol|  |
|i| ◌ִ &nbsp;hiriq | י◌ִ &nbsp;hiriq yod|  |  |
|o| ◌ֹ &nbsp;holam | וֹ◌ &nbsp;holam male| ◌ׇ &nbsp;kamats hatuf| ◌ֺ &nbsp;holam haser for waw\*|
|u| ◌ֻ &nbsp;kubuts | וּ◌ &nbsp;shuruk|  |  |

\* Compare וֹ (waw with holam) and וֺ (waw with holam haser).

### Sheva

The sheva is mapped to ";" (semicolon). The semicolon itself is mapped to AltGr+; (Ctrl+Alt+;) as dead key. The key combination followed by itself results in colon (:), followed by anything else results in semicolon (;).

- so e.g. שְׁוָא is typed as W;vAx

## Punctuation, special accents

I've tried to by compatible with SIL keyboard (https://www.sbl-site.org/Fonts/BiblicalHebrewSILManual.pdf) if possible.
Differences are marked with (*).

|Key   |Normal|Shift |AltGr (Ctrl+Alt)|Shift+AltGr (Ctrl+Alt)|
|-----|-------|------|------|------|
| \` | \` | ₪ sheqel *20aa*| $ dollar| ~ tilde|
| 1 | 1 | ! | ◌ֽ &nbsp;meteg *05bd*| ◌֗ &nbsp;revia *0597*|
| 2 | 2 | ◌֘ &nbsp;zarqa *0598*| ◌֢ &nbsp;atnah hafukh *05a2*| ◌֮ &nbsp;zinor *05ae*|
| 3 | 3 | ◌֨ &nbsp;qadma *05a8*| ◌֖ &nbsp;tipeha *0596*| ◌֙ &nbsp;pashta *0599*|
| 4 | 4 | ◌֜ &nbsp;geresh (accent) *059c*| ◌֥ &nbsp;merkha *05a5*| ◌֠ &nbsp;telisha gedola *05a0*|
| 5 | 5 | ◌֞ &nbsp;gershayim (accent) *059e*| ◌֦ &nbsp;merkha kefula *05a6*| ◌֩ &nbsp;telisha qetana *05a9*|
| 6 | 6 |  | ◌֭ &nbsp;degi *05ad*| ◌֟ &nbsp;qarnez para *059f*|
| 7 | 7 | ◌֬ &nbsp;ilum *05ac*| ◌֣ &nbsp;munah *05a3*| ◌֡ &nbsp;payer *05a1*|
| 8 | 8 | ◌֝ &nbsp;geresh muqdam *059d*| ◌֛ &nbsp;tevir *059b*| ◌֕ &nbsp;zaqef gadol *0595*|
| 9 | 9 | ( | ◌֧ &nbsp;darga *05a7*| ◌֓ &nbsp;shalshelet *0593*|
| 0 | 0 | ) | ◌֪ &nbsp;yerah ben yomo *05aa*| ◌֯ &nbsp;masora circle *05af*|
| - | ◌־◌ &nbsp;maqaf *05be*| – en dash *2013*| — em dash *2014*| ◌ֿ &nbsp;rafe *05bf*|
| = | = | + | ◌֑ &nbsp;etnahta *0591*| ◌ dotted circle *25cc*|
| q | ק |  |  |  |
| w | שׂ sin| שׁ shin| שׂ sin composite| שׁ shin composite|
| e | ◌ֶ &nbsp;segol| ◌ֵ &nbsp;tsere| ◌ֱ &nbsp;hataf segol|  |
| r | ר resh|  | ﬧ wide resh|  |
| t | ת tav| ט tet| ﬨ wide tav|  |
| y | ע ayin|  |  |  |
| u | ◌ֻ &nbsp;kubuts| וּ◌ &nbsp;shuruk|  |  |
| i | ◌ִ &nbsp;hiriq| י◌ִ &nbsp;hiriq yod|  |  |
| o | ◌ֹ &nbsp;holam| וֹ◌ &nbsp;holam male| ◌ׇ &nbsp;kamats hatuf | ◌ֺ &nbsp;holam haser for waw|
| p | פ fe/pe| ף final fe/pe|  | ͏ combine grapheme joiner *034f*|
| [ | [ | { | | ◌֔ &nbsp;zaqef qatam *0594*|
| ] | ] | } |  ◌֚ &nbsp;yetiv *059a*| ◌֒ &nbsp;segolta *0592*|
| \ | ׀ paseq *05c0*| \ backslash(\*)| ◌֤ &nbsp;mahapakh *05a4*| ◌֫ &nbsp;ole *05ab*|
| a | ◌ַ &nbsp;patah| ◌ָ &nbsp;kamats| ◌ֲ &nbsp;hataf patah| ◌ֳ &nbsp;hataf kamats|
| s | ס samekh| ש sin/shin without dot| ׂ sin dot *05c2*| ׁ shin dot *05c1*|
| d | ד dalet|  | ﬢ wide dalet|  |
| f |  |  |  | ◦ (\*)white bullet *25e6*|
| g | ג gimel|  |  | • bullet 2022|
| h | ה he| ח het| ﬣ wide he(\*) | ◌̊ &nbsp;ring above *030a*|
| j | י yod|  |  | ̶  (\*) long stroke *0336*|
| k | כ chaf/kaf| ך final chaf/kaf| ﬤ wide chaf/kaf|  |
| l | ל lamed|  | ﬥ wide lamed|  |
| ; |  sheva| ״ gershayim (punctuation) *05f4*| ; semicolon dead key| ׃ sof pasuq *05c3*|
| ' | ’ right single quotation *2019*| ” right double quotation *201d*| ̣ &nbsp;punctum *0323*| אׄ upper dot *05c4*|
| z | ז zayin|  | # number sign|  |
| x | א aleph|  | ﬡ wide aleph|  |
| c | צ tsade| ץ final tsade| & ampersand |  |
| v | ו  waw|  | @ at sign| (\*) left-to-right *200e*|
| b | ב  vet/bet|  |  | (\*) right-to-left *200f*|
| n | נ nun| ן final nun| \* asterisk|  (\*) zero width non-joiner *200c*|
| m | מ mem| ם final mem| ﬦ wide final mem| zero width joiner *200d*|
| , | , | < | « guillemets left| ◌̇ &nbsp;masora dot above *0307*|
| . | ּ &nbsp;dagesh/mappiq dead key| > | » guillemets right| ◌̈ &nbsp;thousands *0308*|
| / | / | ? | ׳ geresh (punctuation) *05f3*|  |
