---
description: 'Daha fazla bilgi edinin: yük hata kancalarını geciktir'
title: Hata kancaları
ms.date: 01/19/2021
helpviewer_keywords:
- delayed loading of DLLs, failure hooks
ms.openlocfilehash: 46cec6c66169ebe589bb5f0c912b2d8239e69da1
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667171"
---
# <a name="failure-hooks"></a>Hata Kancaları

Hata kancası, [bildirim kancası](notification-hooks.md)ile aynı şekilde etkindir. `HINSTANCE`Bir özel durumun oluşturulması gerektiğini belirtmek için, kanca yordamının uygun bir değer döndürmesi gerekir, böylece işlem devam edebilir (bir veya `FARPROC` ) ya da 0.

Kullanıcı tanımlı işleve başvuran işaretçi değişkeni:

```C
// This is the failure hook, dliNotify = {dliFailLoadLib|dliFailGetProc}
ExternC
PfnDliHook   __pfnDliFailureHook2;
```

**`DelayLoadInfo`** Yapı, değerin değeri de dahil olmak üzere hatanın doğru raporlaması için gereken tüm ilgili verileri içerir `GetLastError` .

Bildirim ise **`dliFailLoadLib`** , kanca işlevi şu şekilde dönebilir:

- 0, hatayı işleyemeyebilir.

- `HMODULE`, Hata kancasını sorunu düzeltti ve kitaplığın kendisini yükleirse.

Bildirim ise **`dliFailGetProc`** , kanca işlevi şu şekilde dönebilir:

- 0, hatayı işleyemeyebilir.

- Başarısız olan bir proc adresi (alma işlevi adresi), adresin kendisini alma işleminde başarılı oldu.

## <a name="see-also"></a>Ayrıca bkz.

[Hata işleme ve bildirme](error-handling-and-notification.md)
