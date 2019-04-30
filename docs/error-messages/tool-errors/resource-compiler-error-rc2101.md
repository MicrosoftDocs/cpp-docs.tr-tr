---
title: Kaynak Derleyicisi Hatası RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: 595e87b73d79a01993e0e9b3aaa814332b21413f
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64345283"
---
# <a name="resource-compiler-error-rc2101"></a>Kaynak Derleyicisi Hatası RC2101

Önceden işlenmiş RC dosyasında geçersiz yönerge

Kaynak Derleyicisi dosyayı içeren bir **#pragma** yönergesi.

Kullanım **#ifndef** önişlemci yönergesi kaynak derleyicisi bir dahil etme dosyasından işlediğinde tanımlar rc_ınvoked sabit ile. Bir yerde **#pragma** rc_ınvoked sabiti tanımlandığında işlenmez kod bloğunun bir yönerge. Bloğu içindeki kod, yalnızca C/C++ derleyicisi tarafından ve kaynak derleyicisi tarafından işlenir. Aşağıdaki örnek kod, bu tekniği gösterir:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** önişlemci yönergesi hiçbir anlamı bir. RC dosyası. **#İnclude** önişlemci yönergesi de sık kullanılan bir. (Bir proje temelli özel üst bilgi dosyası veya ürünlerinden biri ile Microsoft tarafından sağlanan bir standart üstbilgi dosyası) bir üstbilgi dosyasını eklemek için RC dosyası. Bu dosyaların bazıları içeren **#pragma** yönergesi. Bir veya birden çok diğer üst bilgi dosyaları, sorunlu içeren dosyayı bir üstbilgi dosyası içerebildiklerinden **#pragma** yönergesi hemen belirgin olmayabilir.

**#İfndef** rc_ınvoked teknik proje tabanlı üst bilgi dosyaları, üstbilgi dosyaları dahil olmak üzere denetleyebilirsiniz.