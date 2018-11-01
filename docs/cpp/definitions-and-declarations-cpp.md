---
title: Tanımlar ve Bildirimler (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: 987e27bdf35eba7d9380fc546c15b93b3179333b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628949"
---
# <a name="definitions-and-declarations-c"></a>Tanımlar ve Bildirimler (C++)

**Microsoft'a özgü**

DLL arabirimi, sistemdeki bazı programlar tarafından dışa aktarılacak bilinen tüm öğelere (İşlevler ve veriler) gösterir. olarak bildirilen diğer bir deyişle, tüm öğeleri **dllimport** veya **dllexport**. DLL arabirimine dahil olan tüm bildirimler belirtmeli **dllimport** veya **dllexport** özniteliği. Ancak, tanım yalnızca belirtmelisiniz **dllexport** özniteliği. Örneğin, aşağıdaki işlev tanımı bir derleyici hatası oluşturur:

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

Kullanımını **dllexport** bir tanımı gelir ancak **dllimport** bir bildirimi gösterir. Kullanmalısınız **extern** anahtar sözcüğü ile **dllexport** bir bildirimi zorlamak için Aksi takdirde, bir tanım gösterilir. Bu nedenle, aşağıdaki örnekler doğrudur:

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)