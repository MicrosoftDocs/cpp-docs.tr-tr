---
title: dllimport/dllexport için Kurallar ve Sınırlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- dllexport attribute [C++], limitations and rules
- dllimport attribute [C++], limitations and rules
- dllexport attribute [C++]
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
ms.openlocfilehash: cc83a43fd09299710585fa104dbd4dc847036c68
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62158433"
---
# <a name="rules-and-limitations-for-dllimportdllexport"></a>dllimport/dllexport için Kurallar ve Sınırlamalar

**Microsoft'a Özgü**

- Bir işlevi **dllimport** veya `dllexport` Attribute olmadan bildirirseniz, işlev dll arabiriminin bir parçası olarak kabul edilmez. Bu nedenle, işlevin tanımı bu modülde veya aynı programın başka bir modülünde mevcut olmalıdır. İşlevi DLL arabiriminin bir parçası yapmak için, diğer modüldeki işlevin tanımını olarak `dllexport`bildirmeniz gerekir. Aksi halde, istemci oluşturulduğunda bir bağlayıcı hatası oluşturulur.

- Programınızdaki tek bir modül aynı işlev için **dllimport** ve `dllexport` bildirimler içeriyorsa, `dllexport` öznitelik **dllimport** özniteliğiyle önceliklidir. Ancak, bir derleyici uyarısı oluşturulur. Örneğin:

    ```
    #define DllImport   __declspec( dllimport )
    #define DllExport   __declspec( dllexport )

       DllImport void func1( void );
       DllExport void func1( void );   /* Warning; dllexport */
                                       /* takes precedence. */

    ```

- **Dllimport** özniteliğiyle belirtilen bir veri nesnesinin adresiyle bir statik veri işaretçisi başlatamıyor. Örneğin, aşağıdaki kod hatalar oluşturur:

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

- Bir statik işlev işaretçisini **dllimport** ile belirtilen adresle birlikte başlatmak, işlevin adresı yerine DLL içeri aktarma dönüştürücüsü (denetimi işleve aktaran bir kod Saplaması) için işaretçiyi ayarlar. Bu atama bir hata iletisi oluşturmaz:

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

- Bir nesnenin bildiriminde `dllexport` özniteliği içeren bir program, bu nesnenin tanımını sağlaması gerektiğinden, bir `dllexport` işlev adresiyle genel veya yerel bir statik işlev işaretçisi başlatabilirsiniz. Benzer şekilde, bir `dllexport` veri nesnesinin adresiyle genel veya yerel bir statik veri işaretçisi başlatabilirsiniz. Örneğin:

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

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[DLL İçeri ve Dışarı Aktarma İşlevleri](../c-language/dll-import-and-export-functions.md)
