---
description: 'Hakkında daha fazla bilgi edinin: tanımlar ve bildirimler (C)'
title: Bildirimler ve Tanımlar (C)
ms.date: 11/04/2016
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
ms.openlocfilehash: a88a0e56e68b052e3bb8759f9c40670379bd2628
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97186863"
---
# <a name="definitions-and-declarations-c"></a>Bildirimler ve Tanımlar (C)

**Microsoft'a Özgü**

DLL arabirimi, sistemdeki bazı programlar tarafından verilmesi bilinen tüm öğeler (işlevler ve veriler) anlamına gelir; diğer bir deyişle, veya olarak belirtilen tüm öğeler **`dllimport`** `dllexport` . DLL arabirimine dahil edilen tüm bildirimlerin **`dllimport`** ya da `dllexport` özniteliği belirtilmelidir. Ancak, tanım yalnızca `dllexport` özniteliğini belirtebilir. Örneğin, aşağıdaki işlev tanımı bir derleyici hatası oluşturur:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int func()    /* Error; dllimport prohibited in */
                        /* definition. */
{
   return 1;
}
```

Bu kod, aynı zamanda bir hata oluşturur:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllImport int i = 10;      /* Error; this is a definition. */
```

Bununla birlikte, doğru sözdizimi şöyledir:

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport int i = 10;      /* Okay: this is an export definition. */
```

' Nin kullanımı `dllexport` bir tanım gösterir, ancak **`dllimport`** bir bildirimi gösterir. **`extern`** Bir bildirimi zorlamak için ile anahtar sözcüğünü kullanmanız gerekir `dllexport` ; Aksi takdirde bir tanım kapsanır.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllImport int k;   /* These are correct and imply */
Dllimport int j;          /* a declaration. */
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[DLL Içeri ve dışarı aktarma Işlevleri](../c-language/dll-import-and-export-functions.md)
