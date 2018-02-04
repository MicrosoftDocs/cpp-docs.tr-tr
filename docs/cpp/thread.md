---
title: "iş parçacığı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- thread_cpp
dev_langs:
- C++
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8c514879368b8ea3d676635f2b922a2e1c07224
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/03/2018
---
# <a name="thread"></a>thread

**Microsoft Specific**

**İş parçacığı** genişletilmiş depolama sınıfı değiştiricisi iş parçacığı yerel değişken bildirmek için kullanılır. Taşınabilir için eşdeğer C ++ 11 ve sonraki sürümleri, kullanın [thread_local](../cpp/storage-classes-cpp.md#thread_local) taşınabilir kodu için depolama sınıfı tanımlayıcısı. Windows **thread_local** ile uygulanan **__declspec(thread)**.

## <a name="syntax"></a>Sözdizimi

> **__declspec (iş parçacığı)** *bildirimcisi*  

## <a name="remarks"></a>Açıklamalar

İş Parçacığı Yerel Depolaması (TLS), çok iş parçacıklı bir işlemdeki her iş parçacığının, iş parçacığına özgü veriler için depolama alanı ayırdığı mekanizmadır. Standart çok iş parçacıklı programlarda veriler belirli bir işlemin tüm iş parçacıkları arasında paylaşılırken, iş parçacığı yerel depolaması, her iş parçacığı verisi için ayrıma yapan mekanizmadır. İş parçacığı kapsamlı bir açıklama için bkz: [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

İş parçacığı yerel değişkenleri bildirimlerini kullanmalıdır [öznitelik sözdizimi Genişletilmiş](../cpp/declspec.md) ve `__declspec` anahtar sözcüğüyle **iş parçacığı** anahtar sözcüğü. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişken bildirir ve bir değerle başlatır:

```cpp
__declspec( thread ) int tls_i = 1;
```

İş parçacığı yerel değişkenleri dinamik olarak yüklenen kitaplıklarında kullanırken, bir iş parçacığı yerel değişken düzgün başlatılmamış neden olan faktörleri bilmeniz gerekir:

1. Değişkeni (oluşturucular dahil) bir işlev çağrısı ile başlatılırsa, bu işlevi yalnızca ikili/DLL yüklendikten sonra başlatılan bu iş parçacıkları ve ikili / işlemine yüklemek için DLL neden iş parçacığı için çağrılır. DLL yüklendiğinde, zaten çalışıyordu herhangi başka bir iş parçacığı için başlatma işlevleri adı değil. Dinamik başlatma DllMain DllMain çağrısı ancak DLL hiçbir iş parçacığı başladığında DLL işleminde değilse, ileti alır oluşur.

1. Statik olarak sabit değerlerle başlatılan iş parçacığı yerel değişkenler genellikle tüm iş parçacıklarında düzgün başlatılır. Ancak, aralık 2017 itibariyle yoktur bilinen uyumluluk sorunu Microsoft Visual C++ derleyicinin yapabildiği constexpr değişkenleri almak yerine statik başlatma dinamik.

   Not: Bu sorunların hem de gelecekte derleyici güncelleştirmeleri düzeltilmesi beklenir.

Ayrıca, bu yönergeleri iş parçacığı yerel nesneleri ve değişkenleri bildirirken uymanız gerekir:

- Uygulayabileceğiniz **iş parçacığı** özniteliği yalnızca sınıfı ve veri bildirimler ve tanımlar; için **iş parçacığı** işlevi bildirimlerinde veya tanımlarında kullanılamaz.

- Belirleyebileceğiniz **iş parçacığı** yalnızca veri öğeleri statik depolama süresi ile özniteliği. Bu genel veri nesnelerini içerir (her ikisi de **statik** ve **extern**), yerel statik nesneler ve sınıflar statik veri üyeleri. Otomatik veri nesneleri ile bildiremezsiniz **iş parçacığı** özniteliği.

- Kullanmalısınız **iş parçacığı** öznitelik bildirimi ve bir iş parçacığı yerel nesnesinin tanımı için bildirim ve tanımı aynı dosya veya ayrı dosyaları gerçekleştirileceğini.

- Kullanamazsınız **iş parçacığı** öznitelik bir tür değiştiricisi olarak.

- Nesnelerin bildirimi kullandığından **iş parçacığı** özniteliği izin verilir, bu iki örnek anlam olarak eşdeğerdir:

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

   Unutmayın bir **sizeof** başlatılmakta nesnesi içerir ifadesi kendisine bir başvuru niteliğinde değildir ve C ve C++ izin verilir.

**SON Microsoft özel**

## <a name="see-also"></a>Ayrıca bkz.

[__declspec](../cpp/declspec.md)  
[Anahtar Sözcükler](../cpp/keywords-cpp.md)  
[İş Parçacığında Yerel Depolama (TLS)](../parallel/thread-local-storage-tls.md)  
