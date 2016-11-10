---
title: "Property Sheets and Property Pages in MFC"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "property pages, MFC"
  - "controls [MFC], property sheets"
  - "property sheets, MFC"
  - "tab dialog boxes"
ms.assetid: e1bede2b-0285-4b88-a052-0f8a372807a2
caps.latest.revision: 11
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
# Property Sheets and Property Pages in MFC
A property sheet, also known as a tab dialog box, is a dialog box that contains property pages. Each property page is based on a dialog template resource and contains controls. It is enclosed on a page with a tab on top. The tab names the page and indicates its purpose. Users click a tab in the property sheet to select a set of controls.  
  
 Use pages to group the controls in the property sheet into meaningful sets. The contained property sheet typically has several controls of its own. These apply to all pages.  
  
 Property sheets are based on class [CPropertySheet](../mfcref/cpropertysheet-class.md). Property pages are based on class [CPropertyPage](../mfcref/cpropertypage-class.md).  
  
 A property sheet is a special kind of dialog box that is generally used to modify the attributes of some external object, such as the current selection in a view. The property sheet has three main parts: the containing dialog box, one or more property pages shown one at a time, and a tab at the top of each page that the user clicks to select that page. Property sheets are useful for situations where you have several similar groups of settings or options to change. A property sheet groups information in an easily understood manner.  
  
> [!NOTE]
>  When you are trying to show a property sheet by using `CPropertySheet::DoModal`, the system might generate a first-chance exception. This exception occurs because the system is trying to change the [Window Styles](../mfcref/window-styles.md) of the object before the object has been created. For more information about this exception, and also how to avoid it or handle it, see [CPropertySheet::DoModal](../Topic/CPropertySheet::DoModal.md).  
  
## See Also  
 [Property Sheets](../mfc/property-sheets--mfc-.md)