---
title: "Dllimport dllexport için kurallar ve sınırlamalar | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- dllexport attribute [C++], limitations and rules
- dllimport attribute [C++], limitations and rules
- dllexport attribute [C++]
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 62b012f1ce81ffa30528d027e36b299e9e38d2f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rules-and-limitations-for-dllimportdllexport"></a>dllimport/dllexport için Kurallar ve Sınırlamalar
**Microsoft özel**  
  
-   Bir işlev olmadan bildirirseniz **dllimport** veya `dllexport` özniteliği işlevi değil olarak kabul DLL arabiriminin parçası. Bu nedenle, işlev tanımının bu modül veya başka bir modül aynı programının mevcut olması gerekir. DLL arabirimi işlevi parçası haline getirmek için başka bir modül işlev tanımı bildirme `dllexport`. Aksi durumda, istemci yapılandırıldığında bağlayıcı hatası oluşur.  
  
-   Tek bir modül programınızdaki içeriyorsa **dllimport** ve `dllexport` aynı işlevi için bildirimleri `dllexport` özniteliği önceliklidir **dllimport** özniteliği. Ancak, bir derleyici uyarısı oluşturulur. Örneğin:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllExport void func1( void );   /* Warning; dllexport */  
                                       /* takes precedence. */  
  
    ```  
  
-   Statik veri işaretçi adresi ile bildirilen bir veri nesnesi ile başlatamıyor **dllimport** özniteliği. Örneğin, aşağıdaki kod hatalar oluşturur:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport int i;  
       .  
       .  
       .  
       int *pi = &i;                           /* Error */  
  
       void func2()  
       {  
          static int *pi = &i;                   /* Error */  
       }  
  
    ```  
  
-   Bildirilen bir işlev adresi olan bir statik işlev işaretçisi başlatma **dllimport** işaretçiyi DLL içeri aktarma dönüştürücü (Denetim işleve aktaran bir kod saplama) adresine yerine adresini ayarlar işlev. Bu atama bir hata iletisi oluşturmaz:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void   
       .  
       .  
       .  
       static void ( *pf )( void ) = &func1;   /* No Error */  
  
       void func2()  
       {  
          static void ( *pf )( void ) = &func1;  /* No Error */  
       }  
  
    ```  
  
-   Bir program içerdiği için `dllexport` bir nesnesinin bildirimi özniteliğinde, söz konusu nesne tanımı sağlamalıdır, genel veya yerel statik işlev işaretçisi adresiyle başlatabilir bir `dllexport` işlevi. Benzer şekilde, bir genel veya yerel statik verileri işaretçi adresiyle başlatabilir bir `dllexport` veri nesnesi. Örneğin:  
  
    ```  
    #define DllImport   __declspec( dllimport )  
    #define DllExport   __declspec( dllexport )  
  
       DllImport void func1( void );  
       DllImport int i;  
  
       DllExport void func1( void );  
       DllExport int i;  
       .  
       .  
       .  
       int *pi = &i;                            /* Okay */  
       static void ( *pf )( void ) = &func1;    /* Okay */  
  
       void func2()  
       {  
          static int *pi = i;                     /* Okay */  
          static void ( *pf )( void ) = &func1;   /* Okay */  
       }  
  
    ```  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [DLL İçeri ve Dışarı Aktarma İşlevleri](../c-language/dll-import-and-export-functions.md)