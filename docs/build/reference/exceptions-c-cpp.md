---
description: 'Daha fazla bilgi edinin: gecikme yükleme özel durumları (C/C++)'
title: DLL gecikmesi yükleme özel durum kodları
ms.date: 01/19/2021
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
ms.openlocfilehash: 214d8514baba7b180b8d838af8a6b6c0543cc1ce
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667186"
---
# <a name="dll-delay-load-exception-codes"></a>DLL gecikmesi yükleme özel durum kodları

Hata oluştuğunda iki yapılandırılmış özel durum kodu oluşturulabilir:

- Bir `LoadLibrary` hata için

- Bir `GetProcAddress` hata için

Özel durum bilgileri makrosu aşağıda verilmiştir:

```C
//
// Exception information
//
#define FACILITY_VISUALCPP  ((LONG)0x6d)
#define VcppException(sev,err)  ((sev) | (FACILITY_VISUALCPP<<16) | err)
```

Oluşturulan özel durum kodları standart `VcppException(ERROR_SEVERITY_ERROR, ERROR_MOD_NOT_FOUND)` ve `VcppException(ERROR_SEVERITY_ERROR, ERROR_PROC_NOT_FOUND)` değerlerdir. Özel durum, `DelayLoadInfo` `LPDWORD` alanındaki yapıda tarafından alınabilecek değer içindeki bir yapıya bir işaretçi geçirir `GetExceptionInformation` [`EXCEPTION_RECORD`](/windows/win32/api/winnt/ns-winnt-exception_record) `ExceptionInformation[0]` .

Ayrıca, alanında yanlış bitler ayarlandıysa `grAttrs` , özel durum `ERROR_INVALID_PARAMETER` oluşturulur. Bu özel durum, tüm amaçlar ve amaçlar için önemli.

Daha fazla bilgi için bkz. [Yapı ve sabit tanımlar](structure-and-constant-definitions.md).

## <a name="see-also"></a>Ayrıca bkz.

[Hata işleme ve bildirme](error-handling-and-notification.md)
