---
title: Estilos y plantillas de controles
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AutoGeneratedOrientationPage
helpviewer_keywords:
- styles [WPF]
- ControlTemplate [WPF]
- parts [WPF]
- states [WPF]
- templates [WPF]
ms.assetid: c19049bb-5ceb-492d-afd2-751dca0ed8e3
caps.latest.revision: "36"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f5f3bb1856a83309483119ded600396218b81fb7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="control-styles-and-templates"></a>Estilos y plantillas de controles
Los controles de Windows Presentation Foundation (WPF) tienen un <xref:System.Windows.Controls.ControlTemplate> que contiene el árbol visual de ese control. Puede cambiar la estructura y la apariencia de un control modificando el <xref:System.Windows.Controls.ControlTemplate> de ese control. No hay ninguna manera de reemplazar sólo una parte del árbol visual de un control; Para cambiar el árbol visual de un control debe establecer el <xref:System.Windows.Controls.Control.Template%2A> propiedad del control a su nueva y completa <xref:System.Windows.Controls.ControlTemplate>.  
  
 Los temas de escritorio determinan qué diccionario de recursos se usa. Los temas de escritorio determinan qué diccionario de recursos se usa. Para obtener los diccionarios de recursos de los temas de escritorio, consulte [Default WPF Themes ](http://go.microsoft.com/fwlink/?LinkID=158252) (Temas de WPF predeterminados).  
  
 En la tabla siguiente se describen los nombres de archivo del diccionario de recursos y sus correspondientes temas de escritorio.  
  
|Archivo de tema|Tema de escritorio|  
|----------------|-------------------|  
|Classic.xaml|Apariencia de Windows clásica (desde Windows 95, Windows 98 y Windows 2000) en el sistema operativo Windows XP.|  
|Luna.NormalColor.xaml|Tema azul predeterminado en Windows XP.|  
|Luna.Homestead.xaml|Tema verde olivo en Windows XP.|  
|Luna.Metallic.xaml|Tema plateado en Windows XP.|  
|Royale.NormalColor.xaml|Tema predeterminado en el sistema operativo Windows XP Media Center Edition.|  
|Aero.NormalColor.xaml|Tema predeterminado en el sistema operativo Windows Vista.|  
  
## <a name="in-this-section"></a>En esta sección  
 [Button Styles and Templates](../../../../docs/framework/wpf/controls/button-styles-and-templates.md) (Estilos y plantillas de Button)  
 [Calendar Styles and Templates](../../../../docs/framework/wpf/controls/calendar-styles-and-templates.md) (Estilos y plantillas de Calendar)  
 [CheckBox Styles and Templates](../../../../docs/framework/wpf/controls/checkbox-styles-and-templates.md) (Estilos y plantillas de CheckBox)  
 [ComboBox Styles and Templates](../../../../docs/framework/wpf/controls/combobox-styles-and-templates.md) (Estilos y plantillas de ComboBox)  
 [ContextMenu Styles and Templates](../../../../docs/framework/wpf/controls/contextmenu-styles-and-templates.md) (Estilos y plantillas de ContextMenu)  
 [DataGrid Styles and Templates](../../../../docs/framework/wpf/controls/datagrid-styles-and-templates.md) (Estilos y plantillas de DataGrid)  
 [DatePicker Syles and Templates](../../../../docs/framework/wpf/controls/datepicker-styles-and-templates.md) (Estilos y plantillas de DatePicker)  
 [DocumentViewer Styles and Templates](../../../../docs/framework/wpf/controls/documentviewer-styles-and-templates.md) (Estilos y plantillas de DocumentViewer)  
 [Estilos y plantillas de Expander](../../../../docs/framework/wpf/controls/expander-styles-and-templates.md)  
 [Frame Styles and Templates](../../../../docs/framework/wpf/controls/frame-styles-and-templates.md) (Estilos y plantillas de Frame)  
 [GroupBox Styles and Templates](../../../../docs/framework/wpf/controls/groupbox-styles-and-templates.md) (Estilos y plantillas de GroupBox)  
 [Label Styles and Templates](../../../../docs/framework/wpf/controls/label-styles-and-templates.md) (Estilos y plantillas de Label)  
 [ListBox Styles and Templates](../../../../docs/framework/wpf/controls/listbox-styles-and-templates.md) (Estilos y plantillas de ListBox)  
 [ListView Styles and Templates](../../../../docs/framework/wpf/controls/listview-styles-and-templates.md) (Estilos y plantillas de ListView)  
 [Menu Styles and Templates](../../../../docs/framework/wpf/controls/menu-styles-and-templates.md) (Estilos y plantillas de Menu)  
 [NavigationWindow Styles and Templates](../../../../docs/framework/wpf/controls/navigationwindow-styles-and-templates.md) (Estilos y plantillas de NavigationWindow)  
 [PasswordBox Syles and Templates](../../../../docs/framework/wpf/controls/passwordbox-syles-and-templates.md) (Estilos y plantillas de PasswordBox)  
 [ProgressBar Styles and Templates](../../../../docs/framework/wpf/controls/progressbar-styles-and-templates.md) (Estilos y plantillas de ProgressBar)  
 [RadioButton Styles and Templates](../../../../docs/framework/wpf/controls/radiobutton-styles-and-templates.md) (Estilos y plantillas de RadioButton)  
 [RepeatButton Syles and Templates](../../../../docs/framework/wpf/controls/repeatbutton-syles-and-templates.md) (Estilos y plantillas de RepeatButton)  
 [ScrollBar Styles and Templates](../../../../docs/framework/wpf/controls/scrollbar-styles-and-templates.md) (Estilos y plantillas de ScrollBar)  
 [ScrollViewer Styles and Templates](../../../../docs/framework/wpf/controls/scrollviewer-styles-and-templates.md) (Estilos y plantillas de ScrollViewer)  
 [Slider Styles and Templates](../../../../docs/framework/wpf/controls/slider-styles-and-templates.md) (Estilos y plantillas de Slider)  
 [StatusBar Styles and Templates](../../../../docs/framework/wpf/controls/statusbar-styles-and-templates.md) (Estilos y plantillas de StatusBar)  
 [TabControl Styles and Templates](../../../../docs/framework/wpf/controls/tabcontrol-styles-and-templates.md) (Estilos y plantillas de TabControl)  
 [TextBox Styles and Templates](../../../../docs/framework/wpf/controls/textbox-styles-and-templates.md) (Estilos y plantillas de TextBox Styles)  
 [Thumb Syles and Templates](../../../../docs/framework/wpf/controls/thumb-syles-and-templates.md) (Estilos y plantillas de Thumb)  
 [ToggleButton Syles and Templates](../../../../docs/framework/wpf/controls/togglebutton-syles-and-templates.md) (Estilos y plantillas de ToggleButton)  
 [ToolBar Styles and Templates](../../../../docs/framework/wpf/controls/toolbar-styles-and-templates.md) (Estilos y plantillas de ToolBar)  
 [ToolTip Styles and Templates](../../../../docs/framework/wpf/controls/tooltip-styles-and-templates.md) (Estilos y plantillas de ToolTip)  
 [TreeView Styles and Templates](../../../../docs/framework/wpf/controls/treeview-styles-and-templates.md) (Estilos y plantillas de TreeView)  
 [Window Styles and Templates](../../../../docs/framework/wpf/controls/window-styles-and-templates.md) (Estilos y plantillas de ventana)  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Controls>  
  
 <xref:System.Windows.Controls.ControlTemplate>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Información general sobre la creación de controles](../../../../docs/framework/wpf/controls/control-authoring-overview.md)  
  
 [Aplicar estilos y plantillas](../../../../docs/framework/wpf/controls/styling-and-templating.md)
