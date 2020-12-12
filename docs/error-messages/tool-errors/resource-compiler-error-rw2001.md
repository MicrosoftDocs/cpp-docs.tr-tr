---
description: 'Hakkında daha fazla bilgi edinin: kaynak derleyicisi hatası RW2001'
title: Kaynak Derleyicisi Hatası RW2001
ms.date: 11/04/2016
f1_keywords:
- RW2001
helpviewer_keywords:
- RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
ms.openlocfilehash: e550854af4d504e484b722050f0274887956f2c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337249"
---
# <a name="resource-compiler-error-rw2001"></a>Kaynak Derleyicisi Hatası RW2001

Önceden işlenmiş RC dosyasında geçersiz yönerge

RC dosyası bir **#pragma** yönergesi içerir.

**#İfndef** Önişlemci yönergesini, kaynak derleyicisinin bir içerme dosyasını işlediğinde tanımladığı **RC_INVOKED** sabiti ile kullanın. **#Pragma** yönergesini **RC_INVOKED** sabiti tanımlandığında işlenmemiş bir kod bloğunun içine yerleştirin. Bloktaki kod, kaynak derleyicisi tarafından değil yalnızca C/C++ derleyicisi tarafından işlenir. Aşağıdaki örnek kod bu tekniği göstermektedir:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** Önişlemci yönergesinin bir anlamı yoktur. RC dosyası. **#İnclude** Önişlemci yönergesi sıklıkla bir içinde kullanılır. RC dosyası bir üst bilgi dosyası (proje tabanlı özel üstbilgi dosyası ya da Microsoft tarafından ürünlerden biriyle sunulan standart bir üstbilgi dosyası) dahil edilecek. Bu dosya içerme dosyalarından bazıları **#pragma** yönergesini içerir. Bir üst bilgi dosyası bir veya daha fazla üstbilgi dosyası içerebildiğinden, sorunlu **#pragma** yönergesini içeren dosya hemen açık olmayabilir.

**#İfndef RC_INVOKED** tekniği, proje tabanlı üstbilgi dosyalarındaki üst bilgi dosyalarını kontrol edebilir.
