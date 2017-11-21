---
title: "Özel durumlar (C/C++) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
dev_langs: C++
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 40d78e9246d0bb682d63ae094f96123dd4b883e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="exceptions-cc"></a>Özel Durumlar (C/C++)
Hataları karşılaştığında iki özel durum kodları yükseltilebilir:  
  
-   İçin bir **LoadLibrary** hatası  
  
-   İçin bir **GetProcAddress** hatası  
  
 Özel durum bilgilerini şöyledir:  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 Oluşturulan özel durum kodları standart VcppException (error_severıty_error, ERROR_MOD_NOT_FOUND) ve VcppException (error_severıty_error, ERROR_PROC_NOT_FOUND) değerleri olur. Bir işaretçi özel durum geçirir bir **DelayLoadInfo** tarafından alınan LPDWORD değeri yapısında **GetExceptionInformation** içinde [EXCEPTION_RECORD](http://msdn.microsoft.com/library/windows/desktop/aa363082) yapısı, ExceptionInformation [0] alan.  
  
 Ayrıca, yanlış BITS grAttrs alanında ayarlarsanız, özel durum ERROR_INVALID_PARAMETER atılır. Bu, için tüm intents ve purposes, önemli istisnadır.  
  
 Bkz: [yapı ve sabit tanımları](../../build/reference/structure-and-constant-definitions.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata işleme ve bildirme](../../build/reference/error-handling-and-notification.md)