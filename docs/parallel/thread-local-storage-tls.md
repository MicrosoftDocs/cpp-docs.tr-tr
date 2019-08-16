---
title: İş Parçacığı Yerel Depolaması (TLS)
ms.date: 08/09/2019
helpviewer_keywords:
- multithreading [C++], Thread Local Storage
- TLS [C++]
- threading [C++], Thread Local Storage
- storing thread-specific data
- thread attribute
- Thread Local Storage [C++]
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
ms.openlocfilehash: 7e308f7ba23503879f8ebbcacde481cf72055229
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69510397"
---
# <a name="thread-local-storage-tls"></a>İş Parçacığı Yerel Depolaması (TLS)

İş parçacığı yerel depolaması (TLS), belirli bir çok iş parçacıklı işlemdeki her iş parçacığının iş parçacığına özgü verilerin depolandığı konumları ayırabileceği yöntemdir. Dinamik olarak bağlı (çalışma zamanı) iş parçacığına özgü veriler TLS API 'SI ([TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)) yoluyla desteklenir. Win32 ve Microsoft C++ derleyicisi artık mevcut API uygulamasına ek olarak, iş parçacığı başına verileri statik olarak (yükleme zamanı) destekler.

## <a name="_core_compiler_implementation_for_tls"></a>TLS için derleyici uygulama

**C++ 11:**  `thread_local` Depolama sınıfı Belirleyicisi, nesneler ve sınıf üyeleri için iş parçacığı yerel depolama belirtmek için önerilen yoldur. Daha fazla bilgi için bkz. [Depolama sınıflarıC++()](../cpp/storage-classes-cpp.md).

Ayrıca, genişletilmiş depolama sınıfı değiştiricisi olarak Microsoft 'a özgü bir öznitelik, [iş parçacığı](../cpp/thread.md)de sağlar. Bir **iş parçacığı** değişkeni bildirmek için **__declspec** anahtar sözcüğünü kullanın. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bunu bir değer ile başlatır:

```C
__declspec( thread ) int tls_i = 1;
```

## <a name="rules-and-limitations"></a>Kurallar ve sınırlamalar

Statik olarak bağlantılı iş parçacığı yerel nesneleri ve değişkenleri bildirirken aşağıdaki yönergeler gözlenmelidir. Bu yönergeler hem [iş parçacığı](../cpp/thread.md) hem de [thread_local](../cpp/storage-classes-cpp.md)için geçerlidir:

- **Thread** özniteliği yalnızca sınıf ve veri bildirimlerine ve tanımlarına uygulanabilir. İşlev bildirimlerinde veya tanımlarında kullanılamaz. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:

    ```C
    __declspec( thread )void func();     // This will generate an error.
    ```

- **İş parçacığı** değiştiricisi yalnızca **statik** uzantılı veri öğelerinde belirtilebilir. Bu, genel veri nesneleri ( **statik** ve **extern**), yerel statik nesneler ve C++ sınıfların statik veri üyeleri içerir. Otomatik veri nesneleri **iş parçacığı** özniteliğiyle bildirilemez. Aşağıdaki kod derleyici hataları üretir:

    ```C
    void func1()
    {
        __declspec( thread )int tls_i;            // This will generate an error.
    }

    int func2(__declspec( thread )int tls_i )     // This will generate an error.
    {
        return tls_i;
    }
    ```

- İş parçacığı yerel nesnesinin bildirimleri ve tanımı, **thread** özniteliğini belirtmelidir. Örneğin, aşağıdaki kod bir hata oluşturur:

    ```C
    #define Thread  __declspec( thread )
    extern int tls_i;        // This will generate an error, since the
    int __declspec( thread )tls_i;        // declaration and definition differ.
    ```

- **İş parçacığı** özniteliği tür değiştiricisi olarak kullanılamaz. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:

    ```C
    char __declspec( thread ) *ch;        // Error
    ```

- **İş parçacığı** özniteliğini kullanan C++ nesnelerin bildirimine izin verilmediğinden, aşağıdaki iki örnek anlamsal olarak eşdeğerdir:

    ```cpp
    __declspec( thread ) class B
    {
    // Code
    } BObject;  // OK--BObject is declared thread local.

    class B
    {
    // Code
    };
    __declspec( thread ) B BObject;  // OK--BObject is declared thread local.
    ```

- İş parçacığı yerel nesnesinin adresi sabit kabul edilmez ve bu tür bir adresi içeren herhangi bir ifade sabit bir ifade olarak değerlendirilmez. Standart C 'de, etki iş parçacığı yerel değişkeninin adresinin bir nesne veya işaretçi için Başlatıcı olarak kullanılmasına izin verilmeyecektir. Örneğin, aşağıdaki kod C derleyicisi tarafından hata olarak işaretlendi:

    ```C
    __declspec( thread ) int tls_i;
    int *p = &tls_i;       //This will generate an error in C.
    ```

   Bu kısıtlama içinde C++uygulanmaz. Tüm C++ nesnelerin dinamik başlatılmasına izin verdiğinden, bir nesneyi bir iş parçacığı yerel değişkeninin adresini kullanan bir ifade kullanarak başlatabilirsiniz. İş parçacığı yerel nesnelerinin oluşturulması gibi yapılır. Örneğin, daha önce gösterilen kod, C++ kaynak dosya olarak derlendiğinde bir hata oluşturmaz. İş parçacığı yerel değişkeninin adresi yalnızca adresin alındığı iş parçacığı olduğu sürece geçerlidir.

- Standart C, yalnızca statik olmayan uzantı nesneleri için bir başvuruyu içeren bir ifade ile bir nesne veya değişkenin başlatılmasına izin verir. Genellikle C++ bir başvuruyu içeren bir ifadeyle nesnelerin bu tür dinamik başlatılmasına izin verse de, iş parçacığı yerel nesneleriyle bu tür bir başlatmaya izin verilmez. Örneğin:

    ```C
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++
    int j = j;                               // OK in C++, error in C
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++
    ```

   Başlatılmakta olan nesneyi içeren bir `sizeof` ifade kendine bir başvuruyu temsil etmez ve hem C 'de hem de ' de etkinleştirilir. C++

   C++iş parçacığı yerel depolama tesisinde gelecekte yapılacak geliştirmeler nedeniyle iş parçacığı verilerinin böyle dinamik başlatılmasına izin vermez.

- Windows Vista 'dan `__declspec( thread )` önceki Windows işletim sistemlerinde bazı sınırlamalar vardır. DLL herhangi bir veri veya nesne `__declspec( thread )`bildirirse, dinamik olarak yüklenmişse koruma hatasına neden olabilir. DLL, [LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw)ile yüklendikten sonra, kod `__declspec( thread )` verilere her başvurduğunda sistem hatasına neden olur. Bir iş parçacığının genel değişken alanı çalışma zamanında ayrıldığından, bu alanın boyutu uygulamanın gereksinimlerinin bir hesaplamasına ve statik olarak bağlanan tüm dll 'Lerin gereksinimlerine göre belirlenir. Kullandığınızda `LoadLibrary`, ile `__declspec( thread )`belirtilen iş parçacığı yerel değişkenlerine izin vermek için bu alanı genişletemezsiniz. DLL ile `LoadLibrary`yüklenmişse, TLS ayırmak Için [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc)gibi TLS API 'lerini kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)
