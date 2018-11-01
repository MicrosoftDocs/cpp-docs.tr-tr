---
title: Bildirimler ve Tanımlar (C)
ms.date: 11/04/2016
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
ms.openlocfilehash: 1ec42f17d22b24aac3d19a3b129babe723930ae7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50620239"
---
# <a name="definitions-and-declarations-c"></a>Bildirimler ve Tanımlar (C)

**Microsoft'a özgü**

DLL arabirimi, sistemdeki bazı programlar tarafından dışa aktarılacak bilinen tüm öğelere (İşlevler ve veriler) gösterir. olarak bildirilen diğer bir deyişle, tüm öğeleri **dllimport** veya `dllexport`. DLL arabirimine dahil olan tüm bildirimler belirtmeli **dllimport** veya `dllexport` özniteliği. Ancak, tanım yalnızca belirtebilirsiniz `dllexport` özniteliği. Örneğin, aşağıdaki işlev tanımı bir derleyici hatası oluşturur:

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

Kullanımını `dllexport` bir tanımı gelir ancak **dllimport** bir bildirimi gösterir. Bir bildirimi zorlamak için `extern` ile `dllexport` anahtar sözcüğünü kullanmanız gerekir; aksi takdirde, bir tanım gösterilir.

```
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

extern DllImport int k;   /* These are correct and imply */
Dllimport int j;          /* a declaration. */
```

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[DLL İçeri ve Dışarı Aktarma İşlevleri](../c-language/dll-import-and-export-functions.md)