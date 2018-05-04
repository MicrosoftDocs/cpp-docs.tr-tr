---
title: Tanımlar ve bildirimler (C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 742270c77d47c178d0254ca9b9882f73fe3b8293
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="definitions-and-declarations-c"></a>Tanımlar ve Bildirimler (C++)
## <a name="microsoft-specific"></a>Microsoft'a Özgü
 DLL arabirimi sistemde bazı programlar tarafından verilecek bilinen tüm öğeleri (İşlevler ve veriler) ifade eder; diğer bir deyişle, olarak bildirilen tüm öğeleri `dllimport` veya `dllexport`. DLL arabiriminde dahil tüm bildirimleri ya da belirtmeniz gerekir `dllimport` veya `dllexport` özniteliği. Ancak, tanım yalnızca `dllexport` özniteliğini belirtmelidir. Örneğin, aşağıdaki işlev tanımı bir derleyici hatası oluşturur:

```
__declspec( dllimport ) int func() {   // Error; dllimport
                                       // prohibited on definition.
   return 1;  
}
```

 Bu kod, aynı zamanda bir hata oluşturur:

```
__declspec( dllimport ) int i = 10;  // Error; this is a definition.
```

 Bununla birlikte, doğru sözdizimi şöyledir:

```
__declspec( dllexport ) int i = 10;  // Okay--export definition
```

 Kullanımını `dllexport` bir tanımı gelir sırada `dllimport` bir bildirimi anlamına gelir. Bir bildirimi zorlamak için `extern` ile `dllexport` anahtar sözcüğünü kullanmanız gerekir; aksi takdirde, bir tanım gösterilir. Bu nedenle, aşağıdaki örnekler doğrudur:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllExport int k; // These are both correct and imply a
DllImport int j;        // declaration.
```

 Aşağıdaki örnekler öncekini açıklar:

```
static __declspec( dllimport ) int l; // Error; not declared extern.

void func() {
    static __declspec( dllimport ) int s;  // Error; not declared
                                           // extern.
    __declspec( dllimport ) int m;         // Okay; this is a
                                           // declaration.
    __declspec( dllexport ) int n;         // Error; implies external
                                           // definition in local scope.
    extern __declspec( dllimport ) int i;  // Okay; this is a
                                           // declaration.
    extern __declspec( dllexport ) int k;  // Okay; extern implies
                                           // declaration.
    __declspec( dllexport ) int x = 5;     // Error; implies external
                                           // definition in local scope.
}
```

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca Bkz.
 [dllexport, dllimport](../cpp/dllexport-dllimport.md)
