---
title: Tanımlar ve Bildirimler (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: 20683f3d2e12f7ffead573cbac46fdd4e106c383
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189383"
---
# <a name="definitions-and-declarations-c"></a>Tanımlar ve Bildirimler (C++)

**Microsoft 'a özgü**

DLL arabirimi, sistemdeki bazı programlar tarafından verilmesi bilinen tüm öğeler (işlevler ve veriler) anlamına gelir; diğer bir deyişle, **dllimport** veya **dllexport**olarak belirtilen tüm öğeler. DLL arabirimine dahil edilen tüm bildirimlerin **dllimport** veya **dllexport** özniteliği belirtilmelidir. Ancak, tanım yalnızca **dllexport** özniteliğini belirtmelidir. Örneğin, aşağıdaki işlev tanımı bir derleyici hatası oluşturur:

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

**Dllexport** kullanılması bir tanım gösterir, ancak **dllimport** bir bildirimi gösterir. Bir bildirimi zorlamak için, **dllexport** ile **extern** anahtar sözcüğünü kullanmanız gerekir; Aksi takdirde, bir tanım kapsanır. Bu nedenle, aşağıdaki örnekler doğrudur:

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
