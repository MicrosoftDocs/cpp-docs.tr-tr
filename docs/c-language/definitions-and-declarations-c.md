---
title: "Tanımları ve Declarations (C) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: export functions
ms.assetid: d150395a-89d4-4298-9ac4-08f84fe1261c
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5800c18dd9a765aa85a8af90110c8ce32dc48174
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [DLL içeri ve dışarı aktarma işlevleri](../c-language/dll-import-and-export-functions.md)