---
title: Kaynak Derleyicisi Hatası RC2101
ms.date: 11/04/2016
f1_keywords:
- RC2101
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
ms.openlocfilehash: 3fb576758e447c54e4ddfe7ddb024a1fd35a65f2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80191658"
---
# <a name="resource-compiler-error-rc2101"></a>Kaynak Derleyicisi Hatası RC2101

Önceden işlenmiş RC dosyasında geçersiz yönerge

Kaynak derleyicisi dosyası bir **#pragma** yönergesi içerir.

**#İfndef** Önişlemci yönergesini, kaynak derleyicisinin bir içerme dosyasını işlediğinde tanımladığı RC_INVOKED sabiti ile kullanın. **#Pragma** yönergesini RC_INVOKED sabiti tanımlandığında işlenmemiş bir kod bloğunun içine yerleştirin. Bloktaki kod, kaynak derleyicisi tarafından değil yalnızca C/C++ derleyici tarafından işlenir. Aşağıdaki örnek kod bu tekniği göstermektedir:

```
#ifndef RC_INVOKED
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler
#endif
```

**#Pragma** Önişlemci yönergesinin bir anlamı yoktur. RC dosyası. **#İnclude** Önişlemci yönergesi sıklıkla bir içinde kullanılır. RC dosyası bir üst bilgi dosyası (proje tabanlı özel üstbilgi dosyası ya da Microsoft tarafından ürünlerden biriyle sunulan standart bir üstbilgi dosyası) dahil edilecek. Bu dosya içerme dosyalarından bazıları **#pragma** yönergesini içerir. Bir üst bilgi dosyası bir veya daha fazla üstbilgi dosyası içerebildiğinden, sorunlu **#pragma** yönergesini içeren dosya hemen açık olmayabilir.

**#İfndef** RC_INVOKED tekniği, proje tabanlı üstbilgi dosyalarındaki üst bilgi dosyalarını kontrol edebilir.
