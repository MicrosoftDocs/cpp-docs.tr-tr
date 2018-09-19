---
title: Kaynak Derleyicisi hatası RW2001 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW2001
dev_langs:
- C++
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f401ce7c9a96cfeecf195b8872a704b8b1291939
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114988"
---
# <a name="resource-compiler-error-rw2001"></a>Kaynak Derleyicisi Hatası RW2001

Önceden işlenmiş RC dosyasında geçersiz yönerge

RC dosyası içeren bir **#pragma** yönergesi.

Kullanım **#ifndef** önişlemci yönergesi ile **rc_ınvoked** sabit kaynak derleyicisi bir dahil etme dosyasından işlediğinde tanımlar. Bir yerde **#pragma** yönerge olmayan kod bloğu içinde ne zaman işlenen **rc_ınvoked** sabiti tanımlanır. Bloğu içindeki kod, yalnızca C/C++ derleyicisi tarafından ve kaynak derleyicisi tarafından işlenir. Aşağıdaki örnek kod, bu tekniği gösterir:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** önişlemci yönergesi hiçbir anlamı bir. RC dosyası. **#İnclude** önişlemci yönergesi de sık kullanılan bir. (Bir proje temelli özel üst bilgi dosyası veya ürünlerinden biri ile Microsoft tarafından sağlanan bir standart üstbilgi dosyası) bir üstbilgi dosyasını eklemek için RC dosyası. Bu dosyaların bazıları içeren **#pragma** yönergesi. Bir veya birden çok diğer üst bilgi dosyaları, sorunlu içeren dosyayı bir üstbilgi dosyası içerebildiklerinden **#pragma** yönergesi hemen belirgin olmayabilir.

**#İfndef rc_ınvoked** teknik proje tabanlı üst bilgi dosyaları, üstbilgi dosyaları dahil olmak üzere denetleyebilirsiniz.