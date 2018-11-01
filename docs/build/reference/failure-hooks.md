---
title: Hata Kancaları
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: 2bda1d34c85b1e88c7d278816e30e76537a7523b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463616"
---
# <a name="failure-hooks"></a>Hata Kancaları

Hata kanca ile aynı şekilde etkin [bildirim kanca](../../build/reference/notification-hooks.md). Kanca rutin gerekir böylece işleme uygun değeri döndürür (HINSTANCE veya FARPROC bir) devam edebilir veya bir özel durum olduğunu göstermek için 0.

Kullanıcı tanımlı işlevi için gösterir işaretçi değişkeninin şöyledir:

```
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

**DelayLoadInfo** yapısı doğru gelen değer de dahil olmak üzere, hata raporlama için gerekli tüm ilgili verileri içeren `GetLastError`.

Bildirim ise **dliFailLoadLib**, kanca işlevini döndürebilir:

- 0 hata yürütemiyorsa.

- Hata kanca sorunu düzeltildi ve kitaplığın kendisi yüklenen bir hModule'ü.

Bildirim ise **dliFailGetProc**, kanca işlevini döndürebilir:

- 0 hata yürütemiyorsa.

- Geçerli proc adresi (içeri aktarma işlevi adresi) başarılı ise hata kanca adresi alınırken.

## <a name="see-also"></a>Ayrıca Bkz.

[Hata İşleme ve Bildirme](../../build/reference/error-handling-and-notification.md)