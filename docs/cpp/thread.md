---
title: thread
ms.date: 11/04/2016
f1_keywords:
- thread_cpp
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
ms.openlocfilehash: 089f339e5d203fe44789a7df1607f73ab13b8a24
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50440085"
---
# <a name="thread"></a>thread

**Microsoft'a özgü**

**İş parçacığı** genişletilmiş depolama sınıfı değiştiricisi, bir iş parçacığı yerel değişkenini bildirmek için kullanılır. Kullanmak için taşınabilir C ++ 11'de eşdeğer ve üzeri, [thread_local](../cpp/storage-classes-cpp.md#thread_local) taşınabilir kod için depolama sınıfı tanımlayıcısı. Windows üzerinde `thread_local` ile uygulanan **gt;__declspec(thread)**.

## <a name="syntax"></a>Sözdizimi

> **__declspec (iş parçacığı)** *bildirimcisi*

## <a name="remarks"></a>Açıklamalar

İş Parçacığı Yerel Depolaması (TLS), çok iş parçacıklı bir işlemdeki her iş parçacığının, iş parçacığına özgü veriler için depolama alanı ayırdığı mekanizmadır. Standart çok iş parçacıklı programlarda veriler belirli bir işlemin tüm iş parçacıkları arasında paylaşılırken, iş parçacığı yerel depolaması, her iş parçacığı verisi için ayrıma yapan mekanizmadır. İş parçacıklarını tam bir açıklaması için bkz: [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

İş parçacığı yerel değişkenleri bildirimlerinin kullanmalıdır [genişletilmiş öznitelik sözdizimi](../cpp/declspec.md) ve **__declspec** anahtar sözcüğü ile **iş parçacığı** anahtar sözcüğü. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bir değer ile başlatır:

```cpp
__declspec( thread ) int tls_i = 1;
```

Thread-local değişkenleri dinamik olarak yüklenen kitaplıkları kullanırken bir iş parçacığı yerel değişkeni doğru şekilde başlatılmamış neden olabilecek faktörünü bilmeniz gerekir:

1. (Oluşturucular dahil) bir işlev çağrısıyla değişkeni başlatılır, bu işlevi yalnızca ikili/DLL yüklendikten sonra başlatılan bu iş parçacıkları ve işleme yüklemek ikili/DLL neden iş parçacığı için çağrılır. Başlatma işlevleri DLL yüklendiğinde, çalışmakta herhangi başka bir iş parçacığı için oluşumlarından çağrılmaz. Dinamik olarak başlatılması DllMain DllMain çağrısı ancak DLL hiçbir zaman iş parçacığı başlatıldığında DLL işlemde değilse, ileti alır oluşur.

1. Sabit değerler ile statik olarak başlatılır, thread-local değişkenleri genellikle tüm iş parçacıkları üzerinde düzgün bir şekilde başlatılır. Ancak, aralık 2017'den itibaren var. bilinen uyumluluk sorunu Microsoft Visual C++ derleyicinin yapabildiği constexpr değişkenlerini almak dinamik yerine statik başlatma

   Not: Bu sorunların hem de gelecekte güncelleştirmeleri derleyicinin düzeltilmesi beklenir.

Ayrıca, iş parçacığı yerel nesneleri ve değişkenleri bildirirken bu yönergelere uymanız gerekir:

- Uygulayabileceğiniz **iş parçacığı** özniteliği yalnızca sınıf ve veri bildirimlerine ve tanımlarına; **iş parçacığı** İşlev bildirimlerinde veya tanımlarında kullanılamaz.

- Belirtebileceğiniz **iş parçacığı** özniteliğini yalnızca statik depolama süresine sahip veri öğeleri. Bu, genel veri nesneleri içerir (her ikisi de **statik** ve **extern**), yerel statik nesneler ve sınıfların statik veri üyeleri. Otomatik veri nesneleriyle bildiremezsiniz **iş parçacığı** özniteliği.

- Kullanmalısınız **iş parçacığı** özniteliği bildirimi ve bir iş parçacığı yerel nesnesinin tanımı için bildirim ve tanım aynı dosyada veya ayrı dosyalarda olsun.

- Kullanamazsınız **iş parçacığı** özniteliğini tür değiştiricisi olarak.

- Kullanan nesnelerin bildirimine **iş parçacığı** özniteliği izin verilir, bu iki örnek anlam olarak eşdeğerdir:

    ```cpp
    // declspec_thread_2.cpp
    // compile with: /LD
    __declspec( thread ) class B {
    public:
       int data;
    } BObject;   // BObject declared thread local.

    class B2 {
    public:
       int data;
    };
    __declspec( thread ) B2 BObject2;   // BObject2 declared thread local.
    ```

- Standart C, kendilerine başvuru içeren ifadelerle nesnelerin veya değişkenlerin başlatılmasına izin verir (ancak yalnızca statik olmayan uzantı nesneleri için). C++ normalde kendisine başvuru içeren bir ifadeyle bir nesnenin dinamik şekilde başlatılmasına izin verse de, iş parçacığı yerel nesneleriyle bu tür bir başlatmaya izin verilmez. Örneğin:

   ```cpp
   // declspec_thread_3.cpp
   // compile with: /LD
   #define Thread __declspec( thread )
   int j = j;   // Okay in C++; C error
   Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
   ```

   Unutmayın bir **sizeof** başlatılan nesneyi içeren ifadesi kendisine bir başvuru oluşturmadığına ve C ve C++ içinde izin verilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)<br/>
[İş Parçacığında Yerel Depolama (TLS)](../parallel/thread-local-storage-tls.md)