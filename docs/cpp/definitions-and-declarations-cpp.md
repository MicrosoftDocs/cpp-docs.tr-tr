---
description: 'Hakkında daha fazla bilgi edinin: tanımlar ve bildirimler (C++)'
title: Tanımlar ve Bildirimler (C++)
ms.date: 11/04/2016
ms.assetid: 56b809c0-e602-4f18-9ca5-cd7a8fbaaf30
ms.openlocfilehash: c22274534193011c1c5ec26aedbece339a9302b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339442"
---
# <a name="definitions-and-declarations-c"></a>Tanımlar ve Bildirimler (C++)

**Microsoft'a Özgü**

DLL arabirimi, sistemdeki bazı programlar tarafından verilmesi bilinen tüm öğeler (işlevler ve veriler) anlamına gelir; diğer bir deyişle, veya olarak belirtilen tüm öğeler **`dllimport`** **`dllexport`** . DLL arabirimine dahil edilen tüm bildirimlerin **`dllimport`** ya da **`dllexport`** özniteliği belirtilmelidir. Ancak, tanım yalnızca **`dllexport`** özniteliğini belirtmelidir. Örneğin, aşağıdaki işlev tanımı bir derleyici hatası oluşturur:

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

' Nin kullanımı **`dllexport`** bir tanım gösterir, ancak **`dllimport`** bir bildirimi gösterir. **`extern`** Bir bildirimi zorlamak için ile anahtar sözcüğünü kullanmanız gerekir **`dllexport`** ; Aksi takdirde bir tanım kapsanır. Bu nedenle, aşağıdaki örnekler doğrudur:

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
