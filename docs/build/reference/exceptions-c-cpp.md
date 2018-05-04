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
ms.openlocfilehash: 819f9424b2439cc49517afe54d62a8ed4f06d22d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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
 [Hata İşleme ve Bildirme](../../build/reference/error-handling-and-notification.md)