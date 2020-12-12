---
description: 'Daha fazla bilgi edinin: iş parçacığı'
title: thread
ms.date: 05/07/2019
f1_keywords:
- thread_cpp
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
ms.openlocfilehash: 7b83686b6641585e7e7af334a6127c71a9171610
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164711"
---
# <a name="thread"></a>thread

**Microsoft'a Özgü**

**`thread`** Genişletilmiş depolama sınıfı değiştiricisi, bir iş parçacığı yerel değişkeni bildirmek için kullanılır. C++ 11 ve üzeri sürümlerde taşınabilir eşdeğer için, taşınabilir kod için [thread_local](../cpp/storage-classes-cpp.md#thread_local) depolama sınıfı belirticisini kullanın. Windows üzerinde **`thread_local`** ile uygulanır **`__declspec(thread)`** .

## <a name="syntax"></a>Syntax

**`__declspec(thread)`***bildirimci*

## <a name="remarks"></a>Açıklamalar

İş Parçacığı Yerel Depolaması (TLS), çok iş parçacıklı bir işlemdeki her iş parçacığının, iş parçacığına özgü veriler için depolama alanı ayırdığı mekanizmadır. Standart çok iş parçacıklı programlarda veriler belirli bir işlemin tüm iş parçacıkları arasında paylaşılırken, iş parçacığı yerel depolaması, her iş parçacığı verisi için ayrıma yapan mekanizmadır. İş parçacıklarının tüm konuları için bkz. [Çoklu Iş parçacığı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

İş parçacığı yerel değişkenlerinin bildirimleri [genişletilmiş öznitelik söz dizimini](../cpp/declspec.md) ve anahtar sözcüğünü kullanmalıdır **`__declspec`** **`thread`** . Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bunu bir değer ile başlatır:

```cpp
__declspec( thread ) int tls_i = 1;
```

Dinamik olarak yüklenen kitaplıklarda iş parçacığı yerel değişkenleri kullanırken, iş parçacığı yerel değişkeninin düzgün şekilde başlatılmasına neden olabilecek faktörlerin farkında olmanız gerekir:

1. Değişken, bir işlev çağrısıyla (oluşturucular dahil) başlatıldıysa, bu işlev yalnızca ikili/DLL 'nin işleme yüklenmesine neden olan iş parçacığı için ve ikili/DLL yüklendikten sonra başlatılan iş parçacıkları için çağrılacaktır. Başlatma işlevleri, DLL yüklendiğinde zaten çalışmakta olan herhangi bir iş parçacığı için çağrılmaz. DLL_THREAD_ATTACH için DllMain çağrısında dinamik başlatma gerçekleşir, ancak dll iş parçacığı başladığında işlemde değilse, DLL bu iletiyi hiçbir zaman alır.

1. Sabit değerlerle statik olarak başlatılan iş parçacığı yerel değişkenleri, genellikle tüm iş parçacıkları üzerinde düzgün şekilde başlatılır. Ancak, 2017 Aralık itibariyle, Microsoft C++ derleyicisinde **`constexpr`** değişkenlerin statik başlatma yerine dinamik olarak aldığı bilinen bir uyumluluk sorunu vardır.

   Note: Bu sorunların her Ikisinin de derleyicinin Gelecekteki güncelleştirmelerinde düzeltilmesi beklenmektedir.

Ayrıca, iş parçacığı yerel nesne ve değişkenlerini bildirirken bu yönergeleri gözlemleyebilirsiniz:

- **`thread`** Özniteliğini yalnızca sınıfına ve veri bildirimlerine ve tanımlarına uygulayabilirsiniz; **`thread`** işlev bildirimlerinde veya tanımlarında kullanılamaz.

- **`thread`** Özniteliğini yalnızca statik depolama süresine sahip veri öğelerinde belirtebilirsiniz. Buna genel veri nesneleri (hem hem **`static`** de **`extern`** ), yerel statik nesneler ve sınıfların statik veri üyeleri dahildir. Özniteliği ile otomatik veri nesneleri bildiremezsiniz **`thread`** .

- Bildirim **`thread`** ve tanımın aynı dosyada veya ayrı dosyalarda oluşmasına bakılmaksızın, bildirim için özniteliğini ve iş parçacığı yerel nesnesinin tanımını kullanmanız gerekir.

- **`thread`** Özniteliği tür değiştiricisi olarak kullanamazsınız.

- Özniteliği kullanan nesnelerin bildirimine **`thread`** izin verilmediğinden, bu iki örnek anlamsal olarak eşdeğerdir:

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

- Standart C, yalnızca statik olmayan nesneler için bir başvuruyu içeren bir ifade ile bir nesne veya değişkenin başlatılmasına izin verir. C++ normalde bir başvuruyu içeren bir ifade içeren bir nesnenin bu tür dinamik başlatılmasına izin veriyorsa, iş parçacığı yerel nesneleriyle bu tür başlatmaya izin verilmez. Örneğin:

   ```cpp
   // declspec_thread_3.cpp
   // compile with: /LD
   #define Thread __declspec( thread )
   int j = j;   // Okay in C++; C error
   Thread int tls_i = sizeof( tls_i );   // Okay in C and C++
   ```

   **`sizeof`** Başlatılmakta olan nesneyi içeren bir ifade kendine başvuru oluşturmaz ve C ve C++ ' da kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)<br/>
[Anahtar sözcükler](../cpp/keywords-cpp.md)<br/>
[İş parçacığı yerel depolaması (TLS)](../parallel/thread-local-storage-tls.md)
