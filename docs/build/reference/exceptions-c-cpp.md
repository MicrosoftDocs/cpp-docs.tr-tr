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
ms.openlocfilehash: cf38af464f08e143ed9073befe30f6aeb8b913b6
ms.sourcegitcommit: 46d24d6e70c03e05484923d9efc6ed5150e96a64
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68915473"
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

Oluşturulan özel durum kodları standart VcppException (ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND) ve VcppException (ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND) değerlerdir. Özel durum, [EXCEPTION_RECORD](/windows/desktop/api/winnt/ns-winnt-exception_record) yapısı, ExceptionInformation [0] alanındaki **GetExceptionInformation** tarafından alınabilecek lpdword değerindeki bir **DelayLoadInfo** yapısına bir işaretçi geçirir.

Ayrıca, grAttrs alanında yanlış bitler ayarlandıysa, ERROR_INVALID_PARAMETER özel durumu oluşturulur. Bu özel durum, tüm amaçlar ve amaçlar için önemli.

Daha fazla bilgi için bkz. [Yapı ve sabit tanımlar](structure-and-constant-definitions.md) .

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme ve Bildirme](error-handling-and-notification.md)
