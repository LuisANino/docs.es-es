---
title: "Cómo: Firmar documentos XML con firmas digitales"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- signatures, XML signing
- System.Security.Cryptography.SignedXml class
- digital signatures, XML signing
- System.Security.Cryptography.RSACryptoServiceProvider class
- XML digital signatures
- XML signing
- signing XML
ms.assetid: 99692ac1-d8c9-42d7-b1bf-2737b01037e4
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 95f610922126074017802ef53670b26b3596e17c
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-sign-xml-documents-with-digital-signatures"></a>Cómo: Firmar documentos XML con firmas digitales
Puede usar las clases del espacio de nombres <xref:System.Security.Cryptography.Xml> para firmar un documento XML o parte de un documento XML con una firma digital.  Las firmas XML digitales (XMLDSIG) permiten comprobar que los datos no se modificaron después de firmarlos.  Para obtener más información sobre el estándar XMLDSIG, consulte la recomendación de World Wide Web Consortium (W3C) [XML Signature Syntax and Processing](http://go.microsoft.com/fwlink/?LinkID=136777).  
  
 El ejemplo de código de este procedimiento muestra cómo firmar digitalmente un documento XML completo y adjuntar la firma al documento en un elemento <`Signature`>.  En el ejemplo se crea una clave de firma RSA, se agrega la clave a un contenedor de claves seguro y, a continuación, se usa la clave para firmar digitalmente un documento XML.  La clave se puede recuperar para comprobar la firma digital XML, o bien se puede usar para firmar otro documento XML.  
  
 Para obtener información acerca de cómo comprobar una firma digital XML creada mediante este procedimiento, consulte [Cómo: comprobar las firmas digitales de documentos XML](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md).  
  
### <a name="to-digitally-sign-an-xml-document"></a>Para firmar digitalmente un documento XML  
  
1.  Cree un objeto <xref:System.Security.Cryptography.CspParameters> y especifique el nombre del contenedor de claves.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToSignXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#2)]  
  
2.  Genere una clave asimétrica mediante la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  La clave se guarda automáticamente en el contenedor de claves al pasar el objeto <xref:System.Security.Cryptography.CspParameters> al constructor de la clase <xref:System.Security.Cryptography.RSACryptoServiceProvider>.  Esta clave se usará para firmar el documento XML.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToSignXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#3)]  
  
3.  Cree un objeto <xref:System.Xml.XmlDocument> cargando un archivo XML del disco.  El objeto <xref:System.Xml.XmlDocument> contiene el elemento XML que se va a cifrar.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToSignXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#4)]  
  
4.  Cree un nuevo objeto <xref:System.Security.Cryptography.Xml.SignedXml> y pásele el objeto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToSignXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#5)]  
  
5.  Agregue la clave RSA de firma al objeto <xref:System.Security.Cryptography.Xml.SignedXml>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToSignXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#6)]  
  
6.  Cree un objeto <xref:System.Security.Cryptography.Xml.Reference> que describa qué se va a firmar.  Para firmar el documento completo, establezca la propiedad <xref:System.Security.Cryptography.Xml.Reference.Uri%2A> en `""`.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToSignXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#7)]  
  
7.  Agregue un objeto <xref:System.Security.Cryptography.Xml.XmlDsigEnvelopedSignatureTransform> al objeto <xref:System.Security.Cryptography.Xml.Reference>.  Una transformación permite al comprobador representar los datos XML de un modo idéntico al que usó el firmante.  Los datos XML se pueden representar de maneras diferentes, por lo que este paso es vital para la comprobación.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToSignXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#8)]  
  
8.  Agregue el objeto <xref:System.Security.Cryptography.Xml.Reference> al objeto <xref:System.Security.Cryptography.Xml.SignedXml>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#9](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#9)]
     [!code-vb[HowToSignXMLDocumentRSA#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#9)]  
  
9. Calcule la firma llamando al método <xref:System.Security.Cryptography.Xml.SignedXml.ComputeSignature%2A>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#10](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#10)]
     [!code-vb[HowToSignXMLDocumentRSA#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#10)]  
  
10. Recupere la representación XML de la firma (un elemento <`Signature`>) y guárdela en un nuevo objeto <xref:System.Xml.XmlElement>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#11](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#11)]
     [!code-vb[HowToSignXMLDocumentRSA#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#11)]  
  
11. Anexe el elemento al objeto <xref:System.Xml.XmlDocument>.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#12](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#12)]
     [!code-vb[HowToSignXMLDocumentRSA#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#12)]  
  
12. Guarde el documento.  
  
     [!code-csharp[HowToSignXMLDocumentRSA#13](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#13)]
     [!code-vb[HowToSignXMLDocumentRSA#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#13)]  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se supone que un archivo llamado `test.xml` se encuentra en el mismo directorio que el programa compilado.  Puede colocar el siguiente código XML en un archivo llamado `test.xml` y usarlo con este ejemplo.  
  
```xml  
<root>  
    <creditcard>  
        <number>19834209</number>  
        <expiry>02/02/2002</expiry>  
    </creditcard>  
</root>  
```  
  
 [!code-csharp[HowToSignXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToSignXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToSignXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToSignXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Para compilar este ejemplo, debe incluir una referencia a `System.Security.dll`.  
  
-   Incluya los siguientes espacios de nombres: <xref:System.Xml>, <xref:System.Security.Cryptography> y <xref:System.Security.Cryptography.Xml>.  
  
## <a name="net-framework-security"></a>Seguridad de .NET Framework  
 Nunca almacene ni transfiera la clave privada de un par de claves asimétricas en texto sin formato.  Para obtener más información acerca de las claves criptográficas simétricas y asimétricas, vea [generar claves para cifrado y descifrado](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).  
  
 No inserte nunca una clave privada directamente en el código fuente.  Las claves insertadas se pueden leer fácilmente desde un ensamblado con el [Ildasm.exe (Desensamblador de IL)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) o abriendo el ensamblado en un editor de texto como Bloc de notas.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Security.Cryptography.Xml>  
 [Comprobar las firmas digitales de documentos XML](../../../docs/standard/security/how-to-verify-the-digital-signatures-of-xml-documents.md)
