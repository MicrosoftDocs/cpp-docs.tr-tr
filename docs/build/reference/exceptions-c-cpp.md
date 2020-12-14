---
description: 'Daha fazla bilgi edinin: özel durumlar (C/C++)'
title: DLL yükleme özel durum kodları (C/C++)
ms.date: 11/19/2019
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
ms.openlocfilehash: 53ae6ab9a21309159b29a96e58d077f45fe30e12
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200851"
---
# <a name="exceptions-cc"></a>Özel Durumlar (C/C++)

Hatalarla karşılaşıldığında iki özel durum kodu ortaya çıkar:

- Bir **LoadLibrary** hatası için

- **GetProcAddress** hatası için

Özel durum bilgileri aşağıda verilmiştir:

```
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Oluşturulan özel durum kodları standart VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) ve VcppException (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND) değerlerdir. Özel durum, [EXCEPTION_RECORD](/windows/win32/api/winnt/ns-winnt-exception_record) yapısı, ExceptionInformation [0] alanındaki **GetExceptionInformation** tarafından alınabilecek lpdword değerindeki bir **DelayLoadInfo** yapısına bir işaretçi geçirir.

Ayrıca, grAttrs alanında yanlış bitler ayarlandıysa, özel durum ERROR_INVALID_PARAMETER oluşturulur. Bu özel durum, tüm amaçlar ve amaçlar için önemli.

Daha fazla bilgi için bkz. [Yapı ve sabit tanımlar](structure-and-constant-definitions.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Hata Işleme ve bildirim](error-handling-and-notification.md)
