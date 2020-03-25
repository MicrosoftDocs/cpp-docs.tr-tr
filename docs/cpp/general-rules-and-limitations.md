---
title: Genel Kurallar ve Sınırlamalar
ms.date: 11/04/2016
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
ms.openlocfilehash: 1adbaf9d9be3a0fc0724603e01b81700554839bc
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188615"
---
# <a name="general-rules-and-limitations"></a>Genel Kurallar ve Sınırlamalar

**Microsoft 'a özgü**

- **Dllimport** veya **dllexport** özniteliği olmadan bir işlev veya nesne bildirirseniz, işlev veya nesne DLL arabiriminin bir parçası olarak kabul edilmez. Bu nedenle, işlev veya nesne tanımı bu modülde veya aynı programın başka bir modülünde bulunmalıdır. DLL arabiriminin işlevini veya nesne parçasını oluşturmak için, diğer modüldeki işlevin veya nesnenin tanımını **dllexport**olarak bildirmeniz gerekir. Aksi takdirde, bir bağlayıcı hatası oluşturulur.

   **Dllexport** özniteliğiyle bir işlev veya nesne bildirirseniz, tanımı aynı programın bazı modülünde yer almalıdır. Aksi takdirde, bir bağlayıcı hatası oluşturulur.

- Programınızdaki tek bir modül aynı işlev veya nesne için hem **dllimport** hem de **dllexport** bildirimleri içeriyorsa, **dllexport** özniteliği **dllimport** özniteliğiyle önceliklidir. Ancak, bir derleyici uyarısı oluşturulur. Örneğin:

    ```cpp
    __declspec( dllimport ) int i;
    __declspec( dllexport ) int i;   // Warning; inconsistent;
                                     // dllexport takes precedence.
    ```

- ' C++De, genel olarak tanımlanmış veya statik bir yerel veri işaretçisi başlatabilir veya **dllimport** özniteliğiyle belirtilen bir veri nesnesinin adresiyle bir hata üretir. Ayrıca, **dllimport** özniteliğiyle belirtilen bir işlevin adresiyle statik bir yerel işlev işaretçisi başlatabilirsiniz. C 'de, bu tür bir atama, işlevin adresi yerine, işaretçiyi DLL içeri aktarma dönüştürücüsü adresine (denetimi işlevine aktaran bir kod Saplaması) ayarlar. İçinde C++, işaretçiyi işlevin adresine ayarlar. Örneğin:

    ```cpp
    __declspec( dllimport ) void func1( void );
    __declspec( dllimport ) int i;

    int *pi = &i;                             // Error in C
    static void ( *pf )( void ) = &func1;     // Address of thunk in C,
                                              // function in C++

    void func2()
    {
       static int *pi = &i;                  // Error in C
       static void ( *pf )( void ) = &func1; // Address of thunk in C,
                                             // function in C++
    }
    ```

   Ancak, bir nesnenin bildiriminde **dllexport** özniteliğini içeren bir program, bu nesnenin tanımını programda bir yerde sağlaması gerektiğinden, bir **dllexport** işlevinin adresiyle genel veya yerel bir statik işlev işaretçisi başlatabilirsiniz. Benzer şekilde, bir **dllexport** veri nesnesinin adresiyle genel veya yerel bir statik veri işaretçisi başlatabilirsiniz. Örneğin, aşağıdaki kod C veya C++içinde hata oluşturmaz:

    ```cpp
    __declspec( dllexport ) void func1( void );
    __declspec( dllexport ) int i;

    int *pi = &i;                              // Okay
    static void ( *pf )( void ) = &func1;      // Okay

    void func2()
    {
        static int *pi = &i;                   // Okay
        static void ( *pf )( void ) = &func1;  // Okay
    }
    ```

- Dllexport öğesini, **dllexport**olarak işaretlenmemiş bir temel sınıfa sahip bir normal **sınıfa uygularsanız,** derleyici C4275 oluşturacaktır.

   Temel sınıf, bir sınıf şablonunun özelleştirmesi ise derleyici aynı uyarıyı oluşturur. Bu sorunu çözmek için, temel sınıfı **dllexport**ile işaretleyin. Bir sınıf şablonunun bir özelleştirmesi ile ilgili sorun, **__declspec (dllexport)** nereye yerleştireceğinizi. sınıf şablonunu işaretlemenize izin verilmiyor. Bunun yerine, sınıf şablonunu açıkça oluşturun ve bu açık örneği **dllexport**ile işaretleyin. Örneğin:

    ```cpp
    template class __declspec(dllexport) B<int>;
    class __declspec(dllexport) D : public B<int> {
    // ...
    ```

   Bu geçici çözüm, şablon bağımsız değişkeni türetilen sınıfsa başarısız olur. Örneğin:

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

   Bu, şablonlarla ortak bir model olduğundan, derleyici bir veya daha fazla taban sınıfına sahip olan bir sınıfa uygulandığında ve bir veya daha fazla temel sınıftan bir sınıf şablonu özelleştirmesi olduğunda, bu, **dllexport** 'ın semantiğini değiştirdi. Bu durumda, derleyici, sınıf şablonlarının uzmanlıklarına dolaylı olarak **dllexport** uygular. Aşağıdakileri yapabilir ve uyarı almaz:

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
