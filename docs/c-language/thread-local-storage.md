---
title: İş Parçacığında Yerel Depolama
ms.date: 11/04/2016
helpviewer_keywords:
- thread-local variables
- TLS (thread local storage)
- thread storage-class attribute
- thread-local storage
- storage, thread local storage
ms.assetid: a0f1b109-c953-4079-aa10-e47f5483173d
ms.openlocfilehash: 4b1aa32b384f3a5db5203883c1cc03bd61de7b19
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152137"
---
# <a name="thread-local-storage"></a>İş Parçacığında Yerel Depolama

**Microsoft'a özgü**

İş parçacığı yerel depolaması (TLS) verilen ve çok iş parçacıklı bir işlemdeki her iş parçacığı için iş parçacığına özgü veri depolama alanı ayırdığı mekanizmadır. Standart çok iş parçacıklı programlarda veriler belirli bir işlemin tüm iş parçacıkları arasında paylaşılırken, iş parçacığı yerel depolaması, her iş parçacığı verisi için ayrıma yapan mekanizmadır. İş parçacıklarını tam bir açıklaması için bkz: [işlemleri ve iş parçacıklarını](/windows/desktop/ProcThread/processes-and-threads) Windows SDK.

Microsoft C dili, genişletilmiş depolama sınıfı özniteliği, __declspec anahtar sözcüğü ile bir iş parçacığı yerel değişkenini bildirmek için kullanılan iş parçacığı içerir. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bir değer ile başlatır:

```
__declspec( thread ) int tls_i = 1;
```

Bu yönergeleri, yerel değişkenleri statik olarak bağlı bir iş parçacığı bildirme uyulması gerekir:

- Dinamik olarak başlatılması sahip iş parçacığı yerel değişkenleri yalnızca DLL'yi yüklemek iş parçacığı ve işlemin çalışmakta olan iş parçacığı başlatılır. Daha fazla bilgi için [iş parçacığı](../cpp/thread.md).

- İş parçacığı özniteliği, sadece veri bildirimlerine ve tanımlarına uygulayabilirsiniz. İşlev bildirimlerinde veya tanımlarında kullanılamaz. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:

    ```C
    #define Thread   __declspec( thread )
    Thread void func();      /* Error */
    ```

- İş parçacığı özniteliği yalnızca statik depolama süresine sahip veri öğelerini belirtebilirsiniz. Bu, genel verileri (statik ve extern) ve yerel statik veriler içerir. İş parçacığı özniteliği ile otomatik veri bildiremezsiniz. Örneğin, aşağıdaki kod derleyici hataları oluşturur:

    ```C
    #define Thread   __declspec( thread )
    void func1()
    {
        Thread int tls_i;            /* Error */
    }

    int func2( Thread int tls_i )    /* Error */
    {
       return tls_i;
    }
    ```

- İş parçacığı özniteliği bildirimi ve tanımı olup aynı dosya veya ayrı dosyalarda bildirimi ve tanımı ortaya bağımsız olarak iş parçacığı yerel veri için kullanmanız gerekir. Örneğin, aşağıdaki kod bir hata oluşturur:

    ```C
    #define Thread   __declspec( thread )
    extern int tls_i;     /* This generates an error, because the   */
    int Thread tls_i;     /* declaration and the definition differ. */
    ```

- İş parçacığı özniteliğini tür değiştiricisi olarak kullanamazsınız. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:

    ```C
    char *ch __declspec( thread );      /* Error */
    ```

- İş parçacığı yerel değişkenin adresi sabit olarak kabul edilmez ve böyle bir adres içeren herhangi bir ifade sabit bir ifade olarak kabul edilmez. Bu, iş parçacığı yerel değişkenin adresi için bir işaretçi bir başlatıcı olarak kullanamayacağınız anlamına gelir. Örneğin, derleyici aşağıdaki kodu hata olarak işaretler:

    ```C
    #define Thread   __declspec( thread )
    Thread int tls_i;
    int *p = &tls_i;      /* Error */
    ```

- C kendisi, ancak yalnızca statik olmayan uzantı nesneleri için bir başvuru içeren bir ifadeyle bir değişkenin başlatılması izin verir. Örneğin:

    ```C
    #define Thread   __declspec( thread )
    Thread int tls_i = tls_i;             /* Error */
    int j = j;                            /* Error */
    Thread int tls_i = sizeof( tls_i )    /* Okay  */
    ```

   Başlatılmakta değişkeni içeren bir sizeof ifadesi kendisine bir başvuru oluşturmadığına ve izin unutmayın.

- Kullanımını  **\_ \_declspec(thread)** ile etkileyebilir [gecikme yükleme](../build/reference/linker-support-for-delay-loaded-dlls.md) DLL içe aktarma.

İş parçacığı özniteliği kullanma hakkında daha fazla bilgi için bkz. [çoklu iş parçacığı kullanımı konuları](../parallel/multithreading-support-for-older-code-visual-cpp.md).

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Genişletilmiş Depolama Sınıfı Öznitelikler](../c-language/c-extended-storage-class-attributes.md)
