---
title: Dllimport / dllexport için kurallar ve sınırlamalar | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- dllexport attribute [C++], limitations and rules
- dllimport attribute [C++], limitations and rules
- dllexport attribute [C++]
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6819ad58e3814f7c632c44db4549321e0c6969e4
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46038405"
---
# <a name="rules-and-limitations-for-dllimportdllexport"></a>dllimport/dllexport için Kurallar ve Sınırlamalar

**Microsoft'a özgü**

- Bir işlev olmadan bildirirseniz **dllimport** veya `dllexport` özniteliği, işlev olarak kabul edilmez DLL arabiriminin bir parçası. Bu nedenle, işlev tanımı bu modüldeki veya başka bir modül aynı programın içinde mevcut olması gerekir. DLL arabirimi işlevi parçası haline getirmek için bir modül olarak işlev tanımı bildirmek `dllexport`. Aksi takdirde istemci oluşturulduğunda bir bağlayıcı hatası meydana gelir.

- Programınızı tek bir modülde varsa **dllimport** ve `dllexport` aynı işlev bildirimlerini `dllexport` özniteliği önceliklidir **dllimport** özniteliği. Ancak, bir derleyici uyarısı oluşturulur. Örneğin:

    ```
    #define DllImport   __declspec( dllimport )
    #define DllExport   __declspec( dllexport )

       DllImport void func1( void );
       DllExport void func1( void );   /* Warning; dllexport */
                                       /* takes precedence. */

    ```

- Statik veri işaretçisi ile bildirilen bir veri nesnesi adresi ile başlatılamıyor **dllimport** özniteliği. Örneğin, aşağıdaki kod hatalar oluşturur:

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

- İle bildirilen bir statik işlev işaretçisi bir işlevin adresini ile başlatma **dllimport** işaretçiyi DLL alma dönüştürücü (Denetim işleve aktaran bir kod saplama) adresine yerine adresini ayarlar işlev. Bu atama bir hata iletisi oluşturmaz:

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

- Bir program içerdiğinden `dllexport` özniteliği bildiriminde bir nesnenin o nesne tanımı sağlamalısınız, adresi ile bir genel veya yerel statik işlev işaretçisi başlatabilirsiniz bir `dllexport` işlevi. Benzer şekilde, bir genel veya yerel statik veri işaretçisine adresiyle başlatabilirsiniz bir `dllexport` veri nesnesi. Örneğin:

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

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[DLL İçeri ve Dışarı Aktarma İşlevleri](../c-language/dll-import-and-export-functions.md)