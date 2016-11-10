---
title: "Resource Symbols Dialog Box"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.editors.resourcesymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "New Symbol dialog box"
  - "Resource Symbols dialog box"
  - "Change Symbol dialog box"
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
caps.latest.revision: 7
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Resource Symbols Dialog Box
The **Resource Symbols** dialog box allows you to add new resource symbols, change the symbols that are displayed, or skip to the location in the source code where a symbol is in use.  
  
 **Name**  
 Displays the name of the symbol. For more information, see [Symbol Name Restrictions](../windows/symbol-name-restrictions.md).  
  
 **Value**  
 Displays the numeric value of the symbol. For more information, see [Symbol Value Restrictions](../windows/symbol-value-restrictions.md).  
  
 **In Use**  
 When selected, specifies that the symbol is being used by one or more resources. The resource or resources are listed in the Used by box.  
  
 **Show read-only symbols**  
 When selected, displays read-only resources. By default, the Resource Symbol dialog box displays only the modifiable resources in your resource script file, but with this option selected, modifiable resources appear in bold text and read-only resources appear in plain text.  
  
 **Used by**  
 Displays the resource or resources using the symbol selected in the symbols list. To move to the editor for a given resource, select the resource in the **Used By** box and click **View Use**. For more information, see [Opening the Resource Editor for a Given Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  
 **New**  
 Opens the New Symbol dialog box, which enables you to define the name and, if necessary, a value for a new symbolic resource identifier. For more information, see [Creating New Symbols](../windows/creating-new-symbols.md).  
  
 **Change**  
 Opens the Change Symbol dialog box, which allows you to change the name or value of a symbol. If the symbol is for a control or resource in use, the symbol can be changed only from the corresponding resource editor. For more information, see [Changing Unassigned Symbols](../windows/changing-unassigned-symbols.md).  
  
 **View Use**  
 Opens the resource that contains the symbol in the corresponding resource editor. For more information, see [Opening the Resource Editor for a Given Symbol](../windows/opening-the-resource-editor-for-a-given-symbol.md).  
  
 For information on adding resources to managed projects, please see [Resources in Applications](../Topic/Resources%20in%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resources strings to properties, see [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
## Requirements  
 Win32  
  
## See Also  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)