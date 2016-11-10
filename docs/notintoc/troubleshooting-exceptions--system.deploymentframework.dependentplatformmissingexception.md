---
title: "Troubleshooting Exceptions: System.DeploymentFramework.DependentPlatformMissingException"
ms.custom: na
ms.date: "10/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "DependentPlatformMissingException class, troubleshooting"
ms.assetid: fee1ca1c-0f0b-483b-b8ab-3743dfdda038
caps.latest.revision: 12
ms.author: "mblome"
manager: "douge"
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
# Troubleshooting Exceptions: System.DeploymentFramework.DependentPlatformMissingException
A `T:System.DeploymentFramework.DependentPlatformMissingException` exception is thrown when an application depends on something not installed on this client. Possible causes include the wrong operating system or version of the [!INCLUDE[dnprdnshort](../ide/includes/dnprdnshort_md.md)] on the machine to which the application is being deployed.  
  
## Associated Tips  
 **Check that all assemblies required by the application are installed on the target computer.**  
 Every installation that attempts to use the Windows Installer begins by checking whether the installer is present on the user's computer, and, if it is not present, whether the computer is ready to install Windows Installer.  
  
## See Also  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)