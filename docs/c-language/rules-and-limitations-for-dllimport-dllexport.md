---
title: Dllimport-dllexport için kurallar ve sınırlamalar
ms.date: 11/04/2016
helpviewer_keywords:
- dllexport attribute [C++], limitations and rules
- dllimport attribute [C++], limitations and rules
- dllexport attribute [C++]
ms.assetid: 274b735f-ab9c-4b07-8d0e-fdb65d664634
ms.openlocfilehash: c2f121d978962fe7fc03aa453fb0a16650aa2727
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220879"
---
# <a name="rules-and-limitations-for-dllimportdllexport"></a>dllimport/dllexport için Kurallar ve Sınırlamalar

**Microsoft'a Özgü**

- Or özniteliği olmadan bir işlev bildirirseniz **`dllimport`** `dllexport` , işlev dll arabiriminin bir parçası olarak kabul edilmez. Bu nedenle, işlevin tanımı bu modülde veya aynı programın başka bir modülünde mevcut olmalıdır. İşlevi DLL arabiriminin bir parçası yapmak için, diğer modüldeki işlevin tanımını olarak bildirmeniz gerekir `dllexport` . Aksi halde, istemci oluşturulduğunda bir bağlayıcı hatası oluşturulur.

- Programınızdaki tek bir modül **`dllimport`** `dllexport` aynı işlev için ve bildirim içeriyorsa, özniteliği `dllexport` özniteliği üzerinde önceliklidir **`dllimport`** . Ancak, bir derleyici uyarısı oluşturulur. Örnek:

    ```
    #define DllImport   __declspec( dllimport )
    #define DllExport   __declspec( dllexport )

       DllImport void func1( void );
       DllExport void func1( void );   /* Warning; dllexport */
                                       /* takes precedence. */

    ```

- Özniteliği ile belirtilen bir veri nesnesinin adresiyle bir statik veri işaretçisi başlatamıyor **`dllimport`** . Örneğin, aşağıdaki kod hatalar oluşturur:

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

- İle belirtilen bir işlevin adresiyle bir statik işlev işaretçisi başlatmak, **`dllimport`** işlevin adresi yerine, DLL içeri aktarma dönüştürücüsü (denetimi işleve aktaran bir kod Saplaması) adresine işaretçiyi ayarlar. Bu atama bir hata iletisi oluşturmaz:

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

- `dllexport`Bir nesnenin bildiriminde özniteliği içeren bir program, bu nesnenin tanımını sağlaması gerektiğinden, bir işlev adresiyle genel veya yerel bir statik işlev işaretçisi başlatabilirsiniz `dllexport` . Benzer şekilde, bir veri nesnesinin adresiyle genel veya yerel bir statik veri işaretçisi başlatabilirsiniz `dllexport` . Örnek:

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

[DLL Içeri ve dışarı aktarma Işlevleri](../c-language/dll-import-and-export-functions.md)
