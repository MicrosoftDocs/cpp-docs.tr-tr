---
title: Özel durumlar (C/C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
dev_langs:
- C++
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 40a3a9e1cf1384603d6b7d95fa5960e951f932ef
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43216889"
---
# <a name="exceptions-cc"></a>Özel Durumlar (C/C++)
Hataları karşılaştığında, iki özel durum kodları yükseltilebilir:  
  
-   İçin bir **LoadLibrary** hatası  
  
-   İçin bir **GetProcAddress** hatası  
  
 Özel durum bilgilerini şu şekildedir:  
  
```  
//  
// Exception information  
//  
#define FACILITY_VISUALCPP  ((LONG)0x6d)  
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)  
```  
  
 Oluşturulan özel durum kodları şunlardır: standart VcppException (error_severıty_error, ERROR_MOD_NOT_FOUND) ve VcppException (error_severıty_error, ERROR_PROC_NOT_FOUND) değerleri. İşaretçi özel durum geçirir bir **DelayLoadInfo** yapısı tarafından alınabilen LPDWORD değerindeki **Getexceptionınformation** içinde [exceptıon_record](/windows/desktop/api/winnt/ns-winnt-_exception_record) yapısı, ExceptionInformation [0] alan.  
  
 Ayrıca, yanlış BITS grAttrs alanında ayarlarsanız, özel durum ERROR_INVALID_PARAMETER oluşturulur. Bu, için tüm intents ve purposes, önemli istisnadır.  
  
 Bkz: [yapı ve sabit tanımları](../../build/reference/structure-and-constant-definitions.md) daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hata İşleme ve Bildirme](../../build/reference/error-handling-and-notification.md)