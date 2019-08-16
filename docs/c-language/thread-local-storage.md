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
ms.openlocfilehash: a1099228e072a772ee7d8e7e93253b674d0cd24b
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500278"
---
# <a name="thread-local-storage"></a>İş Parçacığında Yerel Depolama

**Microsoft 'a özgü**

İş parçacığı yerel depolaması (TLS), belirli bir çok iş parçacıklı işlemdeki her bir iş parçacığının iş parçacığına özgü veriler için depolama alanı ayırdığı mekanizmadır. Standart çok iş parçacıklı programlarda veriler belirli bir işlemin tüm iş parçacıkları arasında paylaşılırken, iş parçacığı yerel depolaması, her iş parçacığı verisi için ayrıma yapan mekanizmadır. İş parçacıklarının tüm konuları için bkz. Windows SDK [süreçler ve Iş parçacıkları](/windows/win32/ProcThread/processes-and-threads) .

Microsoft C dili, iş parçacığı yerel değişkeni bildirmek için __declspec anahtar sözcüğüyle birlikte kullanılan, genişletilmiş depolama sınıfı özniteliğini içerir. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bunu bir değer ile başlatır:

```
__declspec( thread ) int tls_i = 1;
```

Statik olarak bağlantılı iş parçacığı yerel değişkenleri bildirirken bu yönergelerin gözlenmeleri gerekir:

- Dinamik başlatmaya sahip iş parçacığı yerel değişkenleri yalnızca DLL 'nin yüklenmesine ve işlemde zaten çalışmakta olan iş parçacıklarıyla başlatılır. Daha fazla bilgi için bkz. [iş parçacığı](../cpp/thread.md).

- İş parçacığı özniteliğini yalnızca veri bildirimlerine ve tanımlarına uygulayabilirsiniz. İşlev bildirimlerinde veya tanımlarında kullanılamaz. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:

    ```C
    #define Thread   __declspec( thread )
    Thread void func();      /* Error */
    ```

- İş parçacığı özniteliğini yalnızca statik depolama süresine sahip veri öğelerinde belirtebilirsiniz. Bu, genel verileri (statik ve extern) ve yerel statik verileri içerir. İş parçacığı özniteliğiyle otomatik veri bildiremezsiniz. Örneğin, aşağıdaki kod derleyici hataları üretir:

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

- Bildirimin ve tanımın aynı dosyada mi yoksa ayrı dosyalarda mı gerçekleşmediğine bakılmaksızın, bildirim için iş parçacığı özniteliğini ve iş parçacığı yerel verilerinin tanımını kullanmanız gerekir. Örneğin, aşağıdaki kod bir hata oluşturur:

    ```C
    #define Thread   __declspec( thread )
    extern int tls_i;     /* This generates an error, because the   */
    int Thread tls_i;     /* declaration and the definition differ. */
    ```

- İş parçacığı özniteliğini tür değiştiricisi olarak kullanamazsınız. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:

    ```C
    char *ch __declspec( thread );      /* Error */
    ```

- İş parçacığı yerel değişkeninin adresi sabit kabul edilmez ve bu tür bir adresi içeren herhangi bir ifade sabit bir ifade olarak kabul edilmez. Bu, bir iş parçacığı yerel değişkeninin adresini bir işaretçi için Başlatıcı olarak kullanmeyeceğiniz anlamına gelir. Örneğin, derleyici aşağıdaki kodu bir hata olarak işaretler:

    ```C
    #define Thread   __declspec( thread )
    Thread int tls_i;
    int *p = &tls_i;      /* Error */
    ```

- C, yalnızca statik olmayan uzantı nesneleri için bir başvuruyu içeren bir ifade ile bir değişkenin başlatılmasına izin verir. Örneğin:

    ```C
    #define Thread   __declspec( thread )
    Thread int tls_i = tls_i;             /* Error */
    int j = j;                            /* Error */
    Thread int tls_i = sizeof( tls_i )    /* Okay  */
    ```

   Başlatılmakta olan değişkeni içeren bir sizeof ifadesinin kendine başvuru oluşturduğunu ve izin verildiğini unutmayın.

- **Declspec (thread) \_kullanımı, DLL içeri aktarımlarının gecikme yüklemesini etkileyebilir. \_** [](../build/reference/linker-support-for-delay-loaded-dlls.md)

İş parçacığı özniteliğini kullanma hakkında daha fazla bilgi için bkz. [Çoklu Iş parçacığı konuları](../parallel/multithreading-support-for-older-code-visual-cpp.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[C Genişletilmiş Depolama Sınıfı Öznitelikler](../c-language/c-extended-storage-class-attributes.md)
