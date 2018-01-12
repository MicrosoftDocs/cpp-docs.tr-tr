---
title: "İş parçacığı yerel depolaması (TLS) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- multithreading [C++], Thread Local Storage
- TLS [C++]
- threading [C++], Thread Local Storage
- storing thread-specific data
- thread attribute
- Thread Local Storage [C++]
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 47e6be3645e03892d17e45256a5a003d982d973f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="thread-local-storage-tls"></a>İş Parçacığında Yerel Depolama (TLS)
İş parçacığı yerel depolaması (TLS) verilen birden çok iş parçacıklı işlemdeki her bir iş parçacığı iş parçacığına özgü veri depolanacağı konumları ayırabilirsiniz yöntemidir. Dinamik olarak bağlama (çalışma zamanı) iş parçacığına özgü veri TLS API yoluyla desteklenir ([TlsAlloc](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686801), [TlsGetValue](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686812), [TlsSetValue](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686818), ve [TlsFree](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686804)). İş parçacığı yerel depolama Windows nasıl uygulandığı hakkında daha fazla bilgi için bkz: [iş parçacığı yerel depolaması (Windows)](https://msdn.microsoft.com/en-us/library/windows/desktop/ms686749\(v=vs.85\).aspx).  Win32 ve Visual C++ Derleyici artık varolan API uygulamasına ek olarak statik olarak bağlı (yük-time) iş parçacığı başına veri destekler.  
  
##  <a name="_core_compiler_implementation_for_tls"></a>TLS için derleyici uygulaması  
 **C ++ 11:** `thread_local` depolama sınıfı tanımlayıcısı olan nesneleri için iş parçacığı yerel depolama belirtin ve sınıf üyeleri için önerilen yöntem. Daha fazla bilgi için bkz: [depolama sınıfları (C++)](../cpp/storage-classes-cpp.md).  
  
 Visual C++ Ayrıca, bir Microsoft özel öznitelik sağlar [iş parçacığı](../cpp/thread.md), genişletilmiş depolama sınıfı değiştirici olarak. Kullanım `__declspec` bildirmek için anahtar sözcüğü bir **iş parçacığı** değişkeni. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişken bildirir ve bir değerle başlatır:  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
## <a name="rules-and-limitations"></a>Kurallar ve sınırlamalar  
 Aşağıdaki yönergeler statik olarak bildirme iş parçacığı yerel nesneleri ve değişkenleri zaman bağlı uyulması gerekir. Bu yönergeleri her ikisini de uygulamak [iş parçacığı](../cpp/thread.md)ve çoğunlukla aynı zamanda [thread_local](../cpp/storage-classes-cpp.md):  
  
-   `thread` Özniteliği uygulanabilir, yalnızca sınıf ve veri bildirimler ve tanımlar. İşlev bildirimleri veya tanımlarında kullanılamaz. Örneğin, aşağıdaki kod derleyici hatası oluşturur:  
  
    ```  
  
    __declspec( thread )void func();     // This will generate an error.  
    ```  
  
-   `thread` Değiştiricisi, yalnızca üzerinde veri öğeleri ile belirtilebilir `static` uzantı. Bu genel veri nesnelerini içerir (her ikisi de `static` ve `extern`), yerel statik nesneleri ve C++ sınıfları statik veri üyeleri. Otomatik veri nesneleri ile bildirilemez `thread` özniteliği. Aşağıdaki kod derleyici hataları üretir:  
  
    ```  
  
    void func1()  
    {  
        __declspec( thread )int tls_i;            // This will generate an error.  
    }  
  
    int func2(__declspec( thread )int tls_i )    // This will generate an error.  
    {  
        return tls_i;  
    }  
    ```  
  
-   Bildirimler ve bir iş parçacığı yerel nesne tüm belirtmelisiniz tanımını `thread` özniteliği. Örneğin, aşağıdaki kodu bir hata oluşturur:  
  
    ```  
    #define Thread  __declspec( thread )  
    extern int tls_i;        // This will generate an error, since the  
    int __declspec( thread )tls_i;        // declaration and definition differ.  
    ```  
  
-   `thread` Öznitelik bir tür değiştiricisi olarak kullanılamaz. Örneğin, aşağıdaki kod derleyici hatası oluşturur:  
  
    ```  
    char __declspec( thread ) *ch;        // Error  
    ```  
  
-   C++ bildirimi kullanan nesneleri çünkü `thread` özniteliği izin verilir, aşağıdaki iki örnek anlam olarak eşdeğerdir:  
  
    ```  
  
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
  
-   İş parçacığı yerel nesne adresi sabit kabul edilmez ve böyle bir adres içeren herhangi bir ifade sabit bir ifade olarak kabul edilmez. Standart C, bu iş parçacığı yerel değişken adresini bir başlatıcı olarak için kullanımını nesne veya işaretçi yasaklamaz için etkisidir. Örneğin, aşağıdaki kod C derleyicisi tarafından hata olarak işaretlenmiştir:  
  
    ```  
  
    __declspec( thread )int tls_i;  
    int *p = &tls_i;       //This will generate an error in C.  
    ```  
  
     C++'da bu kısıtlama geçerli değildir. Tüm nesnelerin dinamik başlatılması için C++ izin verdiğinden, bir nesne, bir iş parçacığı yerel değişken adresini kullanan bir ifade kullanarak başlatabilirsiniz. Bu, yalnızca iş parçacığı yerel nesneleri oluşturma gibi gerçekleştirilir. Örneğin, daha önce gösterilen koddan C++ kaynak dosyası olarak derlendiğinde bir hata oluşturmaz. Yalnızca, adresi alınan iş parçacığı hala mevcut olduğu sürece bir iş parçacığı yerel değişken adresini geçerli olduğunu unutmayın.  
  
-   Standart C nesne veya kendisine bir başvuru içeren bir ifade değişkenle başlatma, ancak yalnızca statik olmayan uzantı nesnelerin sağlar. C++ tür nesnelerin dinamik başlatılması için genellikle kendisine bir başvuru içeren bir ifade ile olanak sağlasa da, bu tür bir başlatma iş parçacığı yerel nesneleriyle izin verilmez. Örneğin:  
  
    ```  
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++   
    int j = j;                               // OK in C++, error in C  
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++  
    ```  
  
     Unutmayın bir `sizeof` başlatılmakta nesnesi içerir ifadesi kendisine bir başvuru göstermiyor ve C ve C++ içinde etkinleştirilir.  
  
     C++ tür dinamik başlatma iş parçacığı verilerin iş parçacığı yerel depolama tesisi gelecekteki olası geliştirmeler nedeniyle izin vermiyor.  
  
-   Önceki Windows işletim sistemlerinde [!INCLUDE[wiprlhext](../c-runtime-library/reference/includes/wiprlhext_md.md)], `__declspec`(iş parçacığı) bazı sınırlamalar vardır. DLL herhangi bir veri veya nesne olarak bildirirse `__declspec`(iş parçacığı) sebep olabilir koruma hatası dinamik olarak yüklenmişse. DLL ile yüklendikten sonra [LoadLibrary](http://msdn.microsoft.com/library/windows/desktop/ms684175), kod başvurursa sistem hatasına neden olur `__declspec`(iş parçacığı) veri. Bir iş parçacığı genel değişkeni alanını çalışma zamanında ayrılmış olduğundan, bu alanı boyutunu uygulamanın gereksinimlerini gereksinimlerinin ve statik olarak bağlı olan tüm DLL'ler hesaplaması temel alır. Kullandığınızda `LoadLibrary`, ile bildirilen iş parçacığı yerel değişkenleri izin vermek için bu alanı genişletemezsiniz `__declspec`(iş parçacığı). TLS API ' larını kullanın [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801), DLL ile yüklenmesi gereken, TLS ayırmak için dll `LoadLibrary`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C ve Win32 ile Çoklu İş Parçacığı Kullanımı](../parallel/multithreading-with-c-and-win32.md)   
