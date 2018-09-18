---
title: Kaynak Derleyicisi hatası RC2101 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 196806e6d2767c889ae96d239af69113c542ba6c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034765"
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