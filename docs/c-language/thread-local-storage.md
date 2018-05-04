---
title: İş parçacığı yerel depolaması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- thread-local variables
- TLS (thread local storage)
- thread storage-class attribute
- thread-local storage
- storage, thread local storage
ms.assetid: a0f1b109-c953-4079-aa10-e47f5483173d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c98cca6afb096cc9b5e88fe31aa949621d326c98
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="thread-local-storage"></a>İş Parçacığında Yerel Depolama
**Microsoft özel**  
  
 İş parçacığı yerel depolaması (TLS) verilen birden çok iş parçacıklı işlemdeki her bir iş parçacığı için iş parçacığına özgü veri depolama ayırır mekanizmadır. Standart çok iş parçacıklı programlarda veriler belirli bir işlemin tüm iş parçacıkları arasında paylaşılırken, iş parçacığı yerel depolaması, her iş parçacığı verisi için ayrıma yapan mekanizmadır. İş parçacığı kapsamlı bir açıklama için bkz: [işlemleri ve iş parçacıklarını](http://msdn.microsoft.com/library/windows/desktop/ms684841) içinde [!INCLUDE[winsdkshort](../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 Microsoft C Dili Genişletilmiş depolama sınıfı öznitelik __declspec anahtar sözcüğü ile bir iş parçacığı yerel değişken bildirmek için kullanılan iş parçacığı içerir. Örneğin, aşağıdaki kod bir tamsayı iş parçacığı yerel değişken bildirir ve bir değerle başlatır:  
  
```  
__declspec( thread ) int tls_i = 1;  
```  
  
 Bu yönergeler, yerel değişkenleri statik olarak bağlı iş parçacığı bildirme uyulması gerekir:  
  
-   Dinamik başlatma sahip iş parçacığı yerel değişkenleri yalnızca DLL'yi yükleme iş parçacığı ve zaten işlemde çalışan iş parçacıklarının başlatılır. Daha fazla bilgi için bkz: [iş parçacığı](../cpp/thread.md).  
  
-   İş parçacığı özniteliği yalnızca veri bildirimler ve tanımlar uygulayabilirsiniz. İşlev bildirimleri veya tanımlarında kullanılamaz. Örneğin, aşağıdaki kod derleyici hatası oluşturur:  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread void func();      /* Error */  
    ```  
  
-   İş parçacığı özniteliği yalnızca veri öğeleri statik depolama süresi ile belirtebilirsiniz. Bu, genel verileri (statik ve extern) ve yerel statik verileri içerir. İş parçacığı özniteliği olan otomatik veri bildiremezsiniz. Örneğin, aşağıdaki kod derleyici hataları üretir:  
  
    ```  
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
  
-   Bildirim ve aynı dosya veya ayrı dosyalar olup bildirim ve tanımı meydana bağımsız olarak iş parçacığı yerel veriler tanımı için iş parçacığı özniteliği kullanmanız gerekir. Örneğin, aşağıdaki kodu bir hata oluşturur:  
  
    ```  
    #define Thread   __declspec( thread )  
    extern int tls_i;     /* This generates an error, because the   */  
    int Thread tls_i;     /* declaration and the definition differ. */  
    ```  
  
-   İş parçacığı özniteliği bir tür değiştiricisi olarak kullanamazsınız. Örneğin, aşağıdaki kod derleyici hatası oluşturur:  
  
    ```  
    char *ch __declspec( thread );      /* Error */  
    ```  
  
-   İş parçacığı yerel değişken adresini sürekli olarak kabul edilmez ve böyle bir adres içeren herhangi bir ifade sabit bir ifade olarak kabul edilmez. Başka bir deyişle, bir iş parçacığı yerel değişken adresi için bir işaretçi bir başlatıcı olarak kullanamazsınız. Örneğin, derleyici aşağıdaki kod hata olarak işaretler:  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread int tls_i;  
    int *p = &tls_i;      /* Error */  
    ```  
  
-   C başlatma bir değişkenin kendisine, ancak yalnızca statik olmayan uzantı nesneleri için bir başvuru içeren bir ifade ile verir. Örneğin:  
  
    ```  
    #define Thread   __declspec( thread )  
    Thread int tls_i = tls_i;             /* Error */  
    int j = j;                            /* Error */  
    Thread int tls_i = sizeof( tls_i )    /* Okay  */  
    ```  
  
     Başlatılmakta değişkeni içeren bir sizeof ifadesi kendisine bir başvuru niteliğinde değildir ve izin unutmayın.  
  
-   Kullanımını **__declspec(thread)** ile etkileyebilir [gecikme yükleme](../build/reference/linker-support-for-delay-loaded-dlls.md) DLL'SİNİN alır **.**  
  
 İş parçacığı özniteliğini kullanma hakkında daha fazla bilgi için bkz: [çoklu iş parçacığı kullanımı konuları](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
 **SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C Genişletilmiş Depolama Sınıfı Öznitelikler](../c-language/c-extended-storage-class-attributes.md)