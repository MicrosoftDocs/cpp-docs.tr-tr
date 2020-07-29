---
title: Genel Kurallar ve Sınırlamalar
ms.date: 11/04/2016
ms.assetid: 6c48902d-4259-4761-95d4-e421d69aa050
ms.openlocfilehash: 8d21f627f461dce90af93ca5c1af8c4a28098539
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213417"
---
# <a name="general-rules-and-limitations"></a>Genel Kurallar ve Sınırlamalar

**Microsoft'a Özgü**

- Or özniteliği olmadan bir işlev veya nesne bildirirseniz **`dllimport`** **`dllexport`** , işlev veya nesne DLL arabiriminin bir parçası olarak kabul edilmez. Bu nedenle, işlev veya nesne tanımı bu modülde veya aynı programın başka bir modülünde bulunmalıdır. DLL arabiriminin işlevini veya nesne parçasını oluşturmak için, diğer modüldeki işlevin veya nesnenin tanımını olarak bildirmeniz gerekir **`dllexport`** . Aksi takdirde, bir bağlayıcı hatası oluşturulur.

   Özniteliği ile bir işlev veya nesne bildirirseniz **`dllexport`** , tanımı aynı programın bazı modülünde yer almalıdır. Aksi takdirde, bir bağlayıcı hatası oluşturulur.

- Programınızdaki tek bir modül **`dllimport`** **`dllexport`** aynı işlev veya nesne için hem hem de bildirimleri içeriyorsa **`dllexport`** öznitelik, özniteliğe göre önceliklidir **`dllimport`** . Ancak, bir derleyici uyarısı oluşturulur. Örnek:

    ```cpp
    __declspec( dllimport ) int i;
    __declspec( dllexport ) int i;   // Warning; inconsistent;
                                     // dllexport takes precedence.
    ```

- C++ ' da, genel olarak tanımlanmış veya statik bir yerel veri işaretçisini başlatabilir veya özniteliği ile belirtilen bir veri nesnesinin adresiyle bir **`dllimport`** hata üretir. Ayrıca, özniteliğiyle belirtilen bir işlevin adresiyle statik bir yerel işlev işaretçisi başlatabilirsiniz **`dllimport`** . C 'de, bu tür bir atama, işlevin adresi yerine, işaretçiyi DLL içeri aktarma dönüştürücüsü adresine (denetimi işlevine aktaran bir kod Saplaması) ayarlar. C++ ' da, işaretçiyi işlevin adresine ayarlar. Örnek:

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

   Ancak, **`dllexport`** bir nesnenin bildiriminde özniteliği içeren bir program, bu nesnenin tanımını programda bir yerde sağlaması gerektiğinden, bir işlev adresiyle genel veya yerel bir statik işlev işaretçisi başlatabilirsiniz **`dllexport`** . Benzer şekilde, bir veri nesnesinin adresiyle genel veya yerel bir statik veri işaretçisi başlatabilirsiniz **`dllexport`** . Örneğin, aşağıdaki kod C veya C++ içinde hata oluşturmaz:

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

- **`dllexport`** Olarak işaretlenmemiş bir temel sınıfı olan bir normal sınıfa uygularsanız **`dllexport`** , derleyici C4275 oluşturacaktır.

   Temel sınıf, bir sınıf şablonunun özelleştirmesi ise derleyici aynı uyarıyı oluşturur. Bu sorunu çözmek için temel sınıfı ile işaretleyin **`dllexport`** . Bir sınıf şablonunun bir özelleştirmesi ile ilgili sorun, ' nin yerleştirileceği yerdir **`__declspec(dllexport)`** ; sınıf şablonunu işaretlememeye izin verilmez. Bunun yerine, sınıf şablonunu açıkça oluşturun ve bu açık örnek oluşturmayı ile işaretleyin **`dllexport`** . Örnek:

    ```cpp
    template class __declspec(dllexport) B<int>;
    class __declspec(dllexport) D : public B<int> {
    // ...
    ```

   Bu geçici çözüm, şablon bağımsız değişkeni türetilen sınıfsa başarısız olur. Örnek:

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

   Bu, şablonlarla ortak bir model olduğundan, derleyici, **`dllexport`** bir veya daha fazla taban sınıfına sahip olan ve bir ya da daha fazla temel sınıftan bir sınıf şablonu özelleştirmesi olduğunda öğesinin semantiğini değiştirdi. Bu durumda, derleyici **`dllexport`** sınıf şablonlarının özelleştirilmesi için örtülü olarak uygulanır. Aşağıdakileri yapabilir ve uyarı almaz:

    ```cpp
    class __declspec(dllexport) D : public B<D> {
    // ...
    ```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[dllexport, dllimport](../cpp/dllexport-dllimport.md)
