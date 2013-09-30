gwtxslt
=======

XSL Transformation API for GWT. Forked from https://code.google.com/p/gwtxslt/

Popular browsers support XSL Transformations. This project makes available for GWT some parts of browsers' JavaScript interfaces for XSLT processing.

This project presents itself as a GWT module. To use it, you have to place it to your build/classpath, and inherit it's .gwt.xml file:
```xml
<inherits name="hu.szaboaz.gwt.xslt.XSLT" />
```
Usage:
```java
//Any number of processors can be created, they will behave
//independently. Every stylesheet have to have its own processor.
XsltProcessor processor = new XsltProcessor();

//Setting the stylesheet to transform with
processor.importStyleSheet(styleSheetText);

//Setting the document to be transformed
processor.importSource(sourceText);

//Order of setting the stylesheet and document is indifferent.

//Optional, must be called after importStyleSheet
processor.setParameter(paramNameString, paramValueString);

//Getting the result
String resultString = processor.transform();
DOM.getElementById("resultContainer").setInnerHTML(resultString);
```
The importSource-setParameter-transform cycle can be repeated multiple times.
