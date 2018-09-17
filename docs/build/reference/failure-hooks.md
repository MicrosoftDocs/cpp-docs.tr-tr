---
title: Hata kancaları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e4c69759034dbb7233970bd89616a062a369cc13
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45721285"
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