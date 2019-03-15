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
ms.openlocfilehash: f80b99943b103dcf90c05d59df3169e0e05d79f4
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811673"
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

Bkz: [yapı ve sabit tanımları](structure-and-constant-definitions.md) daha fazla bilgi için.

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme ve Bildirme](error-handling-and-notification.md)
