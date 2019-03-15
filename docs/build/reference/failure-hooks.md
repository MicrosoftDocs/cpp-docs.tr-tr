---
title: Hata Kancaları
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: 2fc22ae77d729868adbf8c37d40e450e35a8e866
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811998"
---
# <a name="failure-hooks"></a>Hata Kancaları

Hata kanca ile aynı şekilde etkin [bildirim kanca](notification-hooks.md). Kanca rutin gerekir böylece işleme uygun değeri döndürür (HINSTANCE veya FARPROC bir) devam edebilir veya bir özel durum olduğunu göstermek için 0.

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

## <a name="see-also"></a>Ayrıca bkz.

[Hata İşleme ve Bildirme](error-handling-and-notification.md)
