---
title: Tanımları ve Declarations (C) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d44a98fee82e41252b27fa5a1605b04a15af9115
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="definitions-and-declarations-c"></a>Bildirimler ve Tanımlar (C)
**Microsoft özel**  
  
 DLL arabirimi sistemde bazı programlar tarafından verilecek bilinen tüm öğeleri (İşlevler ve veriler) ifade eder; diğer bir deyişle, olarak bildirilen tüm öğeleri **dllimport** veya `dllexport`. DLL arabiriminde dahil tüm bildirimleri ya da belirtmeniz gerekir **dllimport** veya `dllexport` özniteliği. Bununla birlikte, tanım yalnızca belirtebilirsiniz `dllexport` özniteliği. Örneğin, aşağıdaki işlev tanımı bir derleyici hatası oluşturur:  
  
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
  
 Kullanımını `dllexport` bir tanımı gelir sırada **dllimport** bir bildirimi anlamına gelir. Bir bildirimi zorlamak için `extern` ile `dllexport` anahtar sözcüğünü kullanmanız gerekir; aksi takdirde, bir tanım gösterilir.  
  
```  
#define DllImport   __declspec( dllimport )  
#define DllExport   __declspec( dllexport )  
  
extern DllImport int k;   /* These are correct and imply */  
Dllimport int j;          /* a declaration. */      
```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL İçeri ve Dışarı Aktarma İşlevleri](../c-language/dll-import-and-export-functions.md)