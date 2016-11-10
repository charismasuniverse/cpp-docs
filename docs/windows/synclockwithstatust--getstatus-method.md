---
title: "SyncLockWithStatusT::GetStatus Method"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus method"
ms.assetid: d448b51d-a63d-40d9-a9ee-4aad3204118d
caps.latest.revision: 5
ms.author: "mblome"
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
# SyncLockWithStatusT::GetStatus Method
Supports the WRL infrastructure and is not intended to be used directly from your code.  
  
## Syntax  
  
```  
DWORD GetStatus() const;  
```  
  
## Return Value  
 The result of a wait operation on the object that is based on the SyncLockWithStatusT class, such as a Mutex or Semaphore. Zero (0) indicates the wait operation returned the signaled state; otherwise, another state occurred, such as time-out value elapsed.  
  
## Remarks  
 Retrieves the wait status of the current SyncLockWithStatusT object.  
  
 The GetStatus() function retrieves the value of the underlying [status_](../windows/synclockwithstatust--status_-data-member.md) data member. When an object based on the SyncLockWithStatusT class performs a lock operation, the object first waits for the object to become available. The result of that wait operation is stored in the `status_` data member. The possible values of the `status_` data member are the return values of the wait operation. For more information, see the return values of the **WaitForSingleObjectEx()** function in the MSDN Library.  
  
## Requirements  
 **Header:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::Details  
  
## See Also  
 [SyncLockWithStatusT Class](../windows/synclockwithstatust-class.md)