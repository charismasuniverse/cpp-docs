---
title: "__writecr0"
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
  - "_writecr0"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_writecr0 intrinsic"
ms.assetid: a143d08d-0333-4e1b-91b4-4acb2ae91b5a
caps.latest.revision: 11
ms.author: "corob"
manager: "ghogen"
translation.priority.ht: 
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "ru-ru"
  - "zh-cn"
  - "zh-tw"
translation.priority.mt: 
  - "cs-cz"
  - "pl-pl"
  - "pt-br"
  - "tr-tr"
---
# __writecr0
**Microsoft Specific**  
  
 Writes the value `Data` to the CR0 register.  
  
## Syntax  
  
```  
void writecr0(   
   unsigned __int64 Data   
);  
```  
  
#### Parameters  
 [in] `Data`  
 The value to write to the CR0 register.  
  
## Requirements  
  
|Intrinsic|Architecture|  
|---------------|------------------|  
|`__writecr0`|x86, [!INCLUDE[vcprx64](../build/includes/vcprx64_md.md)]|  
  
 **Header file** \<intrin.h>  
  
## Remarks  
 This intrinsic is only available in kernel mode, and the routine is only available as an intrinsic.  
  
## END Microsoft Specific  
  
## See Also  
 [Compiler Intrinsics](../intrinsics/compiler-intrinsics.md)