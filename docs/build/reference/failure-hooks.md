---
description: 'Daha fazla bilgi edinin: hata kancaları'
title: Hata Kancaları
ms.date: 11/04/2016
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.assetid: 12bb303b-ffe6-4471-bffe-9ef4f8bb2d30
ms.openlocfilehash: a0e74e3413fc81505941dd6f4545988a0d39436f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200734"
---
# <a name="failure-hooks"></a>Hata Kancaları

Hata kancası, [bildirim kancası](notification-hooks.md)ile aynı şekilde etkindir. Bir özel durumun oluşturulması gerektiğini göstermek için, kanca yordamının uygun bir değer döndürmesi gerekir (bir HıNSTANCE veya FARPROC) veya 0.

Kullanıcı tanımlı işleve başvuran işaretçi değişkeni:

```
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

**DelayLoadInfo** yapısı, hatanın doğru raporlaması için gereken tüm ilgili verileri içerir, örneğin değeri `GetLastError` .

Bildirim **dliFailLoadLib** ise, kanca işlevi şu şekilde dönebilir:

- 0, hatayı işleyemeyebilir.

- Hata kancasını sorunu düzeltti ve kitaplığın kendisini yükleirse bir HMODULE.

Bildirim **dliFailGetProc** ise, kanca işlevi şu şekilde dönebilir:

- 0, hatayı işleyemeyebilir.

- Başarısız olan bir proc adresi (alma işlevi adresi), adresin kendisini alma işleminde başarılı oldu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Işleme ve bildirim](error-handling-and-notification.md)
