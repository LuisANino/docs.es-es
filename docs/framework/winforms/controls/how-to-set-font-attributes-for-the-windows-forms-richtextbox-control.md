---
title: "Cómo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- .rtf files [Windows Forms], formatting in RichTextBox control
- fonts [Windows Forms], changing attributes in RichTextBox control
- RTF files [Windows Forms], formatting in RichTextBox control
- RichTextBox control [Windows Forms], setting font attributes
- text [Windows Forms]
- text boxes [Windows Forms], formatting text
- formatting [Windows Forms]
ms.assetid: 2bc23ddb-0529-4489-a1a2-ad253cb43f9a
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e892ce1ecea450e9c3bf300283492913cdb80e07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-font-attributes-for-the-windows-forms-richtextbox-control"></a>Cómo: Establecer atributos de fuente para el control RichTextBox de formularios Windows Forms
Los formularios Windows Forms <xref:System.Windows.Forms.RichTextBox> control tiene numerosas opciones para dar formato al texto que muestra. Hacer que los caracteres seleccionados negrita, subrayado o cursiva, usando la <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> propiedad. También puede usar esta propiedad para cambiar el tamaño y el tipo de letra de los caracteres seleccionados. El <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> propiedad le permite cambiar el color de los caracteres seleccionados.  
  
### <a name="to-change-the-appearance-of-characters"></a>Para cambiar la apariencia de los caracteres  
  
1.  Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionFont%2A> propiedad a una fuente adecuada.  
  
     Para permitir que los usuarios establezcan la familia de fuentes, el tamaño y el tipo de letra en una aplicación, utilizaría normalmente la <xref:System.Windows.Forms.FontDialog> componente. Para obtener información general al respecto, consulte [Información general sobre el componente FontDialog](../../../../docs/framework/winforms/controls/fontdialog-component-overview-windows-forms.md).  
  
2.  Establecer el <xref:System.Windows.Forms.RichTextBox.SelectionColor%2A> propiedad a un color adecuado.  
  
     Para permitir a los usuarios establecer el color en una aplicación, utilizaría normalmente la <xref:System.Windows.Forms.ColorDialog> componente. Para obtener información general al respecto, consulte [Información general sobre el componente ColorDialog](../../../../docs/framework/winforms/controls/colordialog-component-overview-windows-forms.md).  
  
    ```vb  
    RichTextBox1.SelectionFont = New Font("Tahoma", 12, FontStyle.Bold)  
    RichTextBox1.SelectionColor = System.Drawing.Color.Red  
    ```  
  
    ```csharp  
    richTextBox1.SelectionFont = new Font("Tahoma", 12, FontStyle.Bold);  
    richTextBox1.SelectionColor = System.Drawing.Color.Red;  
    ```  
  
    ```cpp  
    richTextBox1->SelectionFont =  
       gcnew System::Drawing::Font("Tahoma", 12, FontStyle::Bold);  
    richTextBox1->SelectionColor = System::Drawing::Color::Red;  
    ```  
  
    > [!NOTE]
    >  Estas propiedades solo afectan al texto seleccionado o, si no hay texto seleccionado, al texto que se escriba en la posición actual del punto de inserción. Para obtener información sobre cómo seleccionar texto mediante programación, vea <xref:System.Windows.Forms.TextBoxBase.Select%2A>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.RichTextBox>  
 [RichTextBox (control)](../../../../docs/framework/winforms/controls/richtextbox-control-windows-forms.md)  
 [Controles que se utilizan en formularios Windows Forms](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
