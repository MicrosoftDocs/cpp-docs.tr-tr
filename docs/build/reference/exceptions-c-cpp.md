---
title: Özel Durumlar (C/C++)
ms.date: 11/04/2016
f1_keywords:
- ERROR_MOD_NOT_FOUND
- vcppException
- ERROR_SEVERITY_ERROR
helpviewer_keywords:
- vcppException
- C++ exception handling, delayed loading of DLLs
- delayed loading of DLLs, exceptions
- ERROR_SEVERITY_ERROR exception
- ERROR_MOD_NOT_FOUND exception
ms.assetid: c03be05d-1c39-4f35-84cf-00c9af3bae9a
ms.openlocfilehash: 14440e625ffdb28b4b8daf6a78563ba839834213
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50647765"
---
# <a name="exceptions-cc"></a>Özel Durumlar (C/C++)

Hataları karşılaştığında, iki özel durum kodları yükseltilebilir:

- İçin bir **LoadLibrary** hatası

- İçin bir **GetProcAddress** hatası

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