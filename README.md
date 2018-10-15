# Page2tei, Time Us custom

## Original project
This XSL transformation is based on the work of [dariok](https://github.com/dariok) for the [Transkribus Project](https://transkribus.eu/Transkribus/). His original transformation scenario is to be found under the [page2tei project](https://github.com/dariok/page2tei) name. 

## Page2tei 
Page2tei takes a PAGE XML file and transforms it into a conform TEI XML file. 

## Customizations
Customizations by Time Us project include : 

- transforming non-default tags into TEI-conform tags
- dealing only with PAGE XML files (not METS)
- transforming additional data entered under the `temp` (temporary) namespace by our [ExportFromTranskribus](https://github.com/TimeUs-ANR/ExportFromTranskribus) script
- creating more complete teiHeader
- creating `rendition="multiline"` attributes to all semantic tags extended over more than one line

## Running Page2tei_TU 
1. Download latest version of Saxon HE parser (ex: `saxonHE9-9-0-1J`):
- https://sourceforge.net/projects/saxon/files/Saxon-HE/

2. Set following directory configuration:
```
page2tei_TimeUs/
 | - page2tei_TU.xsl
 | - stringpack.xsl
 | - saxon9he.jar
 | - input/
 | - oupput/
``` 

3. Paste all PAGE files to transform in `input` directory

4. Run following command in terminal:

`java -jar -s:input/ -o:output/ -xsl:page2tei_TU.xsl`

Transformed files will be stored in `output/` directory.
