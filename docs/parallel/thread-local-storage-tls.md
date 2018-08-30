---
title: İş parçacığı yerel depolaması (TLS) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- multithreading [C++], Thread Local Storage
- TLS [C++]
- threading [C++], Thread Local Storage
- storing thread-specific data
- thread attribute
- Thread Local Storage [C++]
ms.assetid: 80801907-d792-45ca-b776-df0cf2e9f197
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e5720fcbc5c52936a0e29c2ccf0847309636b5f2
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211863"
---
# <a name="thread-local-storage-tls"></a>İş Parçacığında Yerel Depolama (TLS)
İş parçacığı yerel depolaması (TLS) tarafından verilen ve çok iş parçacıklı bir işlemdeki her iş parçacığının iş parçacığına özgü verileri depolamak konumlar ayırabilirsiniz yöntemidir. Dinamik olarak bağlama (çalışma zamanı) iş parçacığına özgü verileri TLS API yoluyla desteklenir ([TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc).  Win32 ve Visual C++ derleyicisi artık statik olarak bağlı (yükleme zamanı) iş parçacığı başına veri mevcut API uygulamasına ek olarak destekler.  
  
##  <a name="_core_compiler_implementation_for_tls"></a> TLS derleyici uygulaması  
 
**C ++ 11:** `thread_local` depolama sınıfı tanımlayıcısı olan nesneler için iş parçacığı-yerel depolamayı belirtin ve sınıf üyeleri için önerilen yol. Daha fazla bilgi için [depolama sınıfları (C++)](../cpp/storage-classes-cpp.md).  
  
Visual C++, ayrıca bir Microsoft'a özel öznitelik sağlar [iş parçacığı](../cpp/thread.md), genişletilmiş depolama sınıfı değiştiricisi olarak. Kullanım **__declspec** bildirmek için anahtar sözcüğü bir **iş parçacığı** değişkeni. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişkeni bildirir ve bir değer ile başlatır:  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
## <a name="rules-and-limitations"></a>Kurallar ve sınırlamalar  
 
Aşağıdaki yönergeler, statik olarak bildirme iş parçacığı yerel nesneleri ve değişkenleri, ilişkili gözlenmelidir. Bu yönergeler her ikisi için de geçerlidir [iş parçacığı](../cpp/thread.md)ve çoğunlukla ayrıca [thread_local](../cpp/storage-classes-cpp.md):  
  
- **İş parçacığı** özniteliği, yalnızca sınıf ve veri bildirimlerine ve tanımlarına uygulanabilir. İşlev bildirimlerinde veya tanımlarında kullanılamaz. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:  
  
    ```  
    __declspec( thread )void func();     // This will generate an error.  
    ```  
  
- **İş parçacığı** değiştirici, yalnızca üzerinde veri öğeleri ile belirtilebilir **statik** uzantı. Bu, genel veri nesneleri içerir (her ikisi de **statik** ve **extern**), yerel statik nesneler ve C++ sınıfların statik veri üyeleri. Otomatik veri nesnelerini ile bildirilemez **iş parçacığı** özniteliği. Aşağıdaki kod derleyici hataları oluşturur:  
  
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
  
- Bildirimler ve bir iş parçacığı yerel nesnesinin tüm belirtmelisiniz tanımını **iş parçacığı** özniteliği. Örneğin, aşağıdaki kod bir hata oluşturur:  
  
    ```  
    #define Thread  __declspec( thread )  
    extern int tls_i;        // This will generate an error, since the  
    int __declspec( thread )tls_i;        // declaration and definition differ.  
    ```  
  
- **İş parçacığı** özniteliğini tür değiştiricisi olarak kullanılamaz. Örneğin, aşağıdaki kod bir derleyici hatası oluşturur:  
  
    ```  
    char __declspec( thread ) *ch;        // Error  
    ```  
  
- C++ bildirimi kullanan nesneler için **iş parçacığı** özniteliği izin verilir, aşağıdaki iki örnek anlam olarak eşdeğerdir:  
  
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
  
- Bir iş parçacığı yerel nesnesinin adresi sabit olarak kabul edilmez ve böyle bir adres içeren herhangi bir ifade sabit bir ifade olarak kabul edilmez. Standart C, bu parametrenin etkisi kullanımını iş parçacığı yerel değişkenin adresi bir Başlatıcısı olarak bir nesne veya işaretçiden yasaklayabilme sağlamaktır. Örneğin, aşağıdaki kod C derleyicisi tarafından hata olarak işaretlenir:  
  
    ```  
    __declspec( thread )int tls_i;  
    int *p = &tls_i;       //This will generate an error in C.  
    ```  
  
     C++'da bu kısıtlama geçerli değildir. C++ için tüm nesneleri dinamik olarak başlatılmasına izin verdiğinden, bir nesne iş parçacığı yerel değişkenin adresi kullanan bir ifade kullanarak başlatabilirsiniz. Bu, yalnızca iş parçacığı yerel nesneleri oluşturma gibi gerçekleştirilir. Örneğin, bir C++ kaynak dosyası olarak derlendiğinde daha önce gösterilen kod bir hata oluşturmaz. İş parçacığı yerel değişkenin adresi yalnızca, adres alınan iş parçacığı hala mevcut olduğu sürece geçerli olduğunu unutmayın.  
  
- Standart C, bir nesne veya değişkenin kendisine bir başvuru içeren bir ifade ile başlatma, ancak yalnızca statik olmayan uzantı nesneleri için sağlar. C++ için dinamik şekilde başlatılmasına nesnelerinin kendisine bir başvuru içeren bir ifadeyle genellikle olanak tanısa da tento typ inicializace iş parçacığı yerel nesneleriyle izin verilmez. Örneğin:  
  
    ```  
    __declspec( thread )int tls_i = tls_i;                // Error in C and C++   
    int j = j;                               // OK in C++, error in C  
    __declspec( thread )int tls_i = sizeof( tls_i )       // Legal in C and C++  
    ```  
  
     Unutmayın bir `sizeof` başlatılan nesneyi içeren ifade kendisine bir başvuru temsil etmez ve C ve C++ içinde etkinleştirilir.  
  
     C++ iş parçacığı veri dinamik şekilde başlatılmasına iş parçacığı yerel depolama tesisi olası gelecekteki geliştirmeler nedeniyle izin vermez.  
  
- Önce Windows Vista, Windows işletim sistemlerinde `__declspec`(iş parçacığı), bazı sınırlamalar vardır. Bir DLL herhangi bir veri veya nesne olarak bildirirse `__declspec`(iş parçacığı) sebep olabilir koruma hatası dinamik olarak yüklü. DLL ile yüklendikten sonra [LoadLibrary](https://msdn.microsoft.com/library/windows/desktop/ms684175), her kod başvurduğunda sistem hatasına neden olur `__declspec`(iş parçacığı) veri. Çalışma zamanında genel değişken alan bir iş parçacığı için ayrıldığından, bu alanı boyutu hesaplanması uygulama gereksinimlerini gereksinimlerinin ve statik olarak bağlı DLL'lerin temel alır. Kullanırken `LoadLibrary`, iş parçacığı yerel değişkenleri izin vermek için bu alanı genişletilemez `__declspec`(iş parçacığı). TLS API'leri gibi kullanın [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc), DLL'nin yüklenmesine, TLS ayırmak için bir DLL dosyanız içinde `LoadLibrary`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 
[C ve Win32 ile Çoklu İş Parçacığı Kullanımı](multithreading-with-c-and-win32.md)   