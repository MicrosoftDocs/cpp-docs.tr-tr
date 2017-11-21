---
title: "iş parçacığı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: thread_cpp
dev_langs: C++
helpviewer_keywords:
- thread local storage (TLS)
- thread __declspec keyword
- TLS (thread local storage), compiler implementation
- __declspec keyword [C++], thread
ms.assetid: 667f2a77-6d1f-4b41-bee8-05e67324fab8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7d81cd7e569cd2baa8ab50b1904fa3ac15b36d0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="thread"></a>thread

**Microsoft özel**  
**İş parçacığı** genişletilmiş depolama sınıfı değiştiricisi iş parçacığı yerel değişken bildirmek için kullanılır. Taşınabilir için eşdeğer C ++ 11 ve sonraki sürümleri, kullanın [thread_local](../cpp/storage-classes-cpp.md#thread_local) depolama sınıfı tanımlayıcısı.

## <a name="syntax"></a>Sözdizimi

```
__declspec( thread ) declarator
```

## <a name="remarks"></a>Açıklamalar

İş Parçacığı Yerel Depolaması (TLS), çok iş parçacıklı bir işlemdeki her iş parçacığının, iş parçacığına özgü veriler için depolama alanı ayırdığı mekanizmadır. Standart çok iş parçacıklı programlarda veriler belirli bir işlemin tüm iş parçacıkları arasında paylaşılırken, iş parçacığı yerel depolaması, her iş parçacığı verisi için ayrıma yapan mekanizmadır. İş parçacığı kapsamlı bir açıklama için bkz: [çoklu iş parçacığı kullanımı](../parallel/multithreading-support-for-older-code-visual-cpp.md).

İş parçacığı yerel değişkenleri bildirimlerini kullanmalıdır [öznitelik sözdizimi Genişletilmiş](../cpp/declspec.md) ve `__declspec` anahtar sözcüğüyle **iş parçacığı** anahtar sözcüğü. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişken bildirir ve bir değerle başlatır:

```cpp
__declspec( thread ) int tls_i = 1;  
```

İş parçacığı yerel nesneleri ve değişkenleri bildirirken bu yönergelere uymanız gerekir:

- Uygulayabileceğiniz **iş parçacığı** özniteliği yalnızca sınıfı ve veri bildirimler ve tanımlar; için **iş parçacığı** işlevi bildirimlerinde veya tanımlarında kullanılamaz.

- Kullanımını **iş parçacığı** özniteliği engelliyor olabilir [gecikme yükleme](../build/reference/linker-support-for-delay-loaded-dlls.md) DLL'SİNİN alır.

- XP sistemlerine **iş parçacığı** DLL __declspec(thread) verileri kullanır ve dinamik olarak LoadLibrary yüklenirse düzgün çalışmayabilir.

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

## <a name="see-also"></a>Ayrıca Bkz.

[__declspec](../cpp/declspec.md)  
[Anahtar sözcükler](../cpp/keywords-cpp.md)  
[İş parçacığı yerel depolaması (TLS)](../parallel/thread-local-storage-tls.md)
