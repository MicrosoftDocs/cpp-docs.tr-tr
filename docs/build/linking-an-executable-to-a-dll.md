---
title: "Bir DLL'e yürütülebilir bir dosya Bağla | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- run time [C++], linking
- dynamic load linking [C++]
- linking [C++], DLLs
- DLLs [C++], linking
- implicit linking [C++]
- explicit linking [C++]
- executable files [C++], linking to DLLs
- loading DLLs [C++]
ms.assetid: 7592e276-dd6e-4a74-90c8-e1ee35598ea3
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ffbb46c562daa213d91892b09e0938d7fd629132
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="link-an-executable-to-a-dll"></a>Bir DLL'e yürütülebilir bir dosya Bağla  
  
Yürütülebilir bir dosyanın bağlar (veya yükler) iki yoldan biriyle DLL:  
  
-   *Örtük bağlantılandırma*, bunu kullanarak yürütülebilir yüklendiğinde burada işletim sistemi DLL'yi yükler. Yalnızca işlevleri statik olarak bağlantılı ve yürütülebilir dosya içinde yer alacağı istemci yürütülebilir dışarı aktarılan DLL işlevlerini çağırır. Örtük bağlantılandırma bazen olarak adlandırılır *statik yük* veya *yükleme zamanı dinamik bağlantılandırma*.  
  
-   *Açıkça bağlantılandırma*, burada çalışma zamanında isteğe bağlı DLL işletim sistemi yükler. Açıkça bağlama tarafından DLL kullanan yürütülebilir işlev çağrılarını açıkça yükleyip DLL kaldırabileceğini ve DLL tarafından dışarı aktarılan işlevlerin erişmek için yapmanız gerekir. Statik olarak bağlantılı kitaplığında işlevlere çağrıları farklı olarak, istemci yürütülebilir, bir işlev işaretçisi aracılığıyla DLL'de dışarı aktarılan işlevler çağırması gerekir. Açıkça bağlantılandırma bazen olarak adlandırılır *dinamik yük* veya *çalışma zamanı dinamik bağlantılandırma*.  
  
Yürütülebilir bir dosya ya da bağlama yöntemini aynı DLL bağlamak için kullanabilirsiniz. Ayrıca, bu yöntemleri birbirini dışlamaz; bir yürütülebilir dosya örtük olarak bir DLL'e bağlayabilirsiniz ve başka açıkça iliştirebilirsiniz.  
  
<a name="determining-which-linking-method-to-use"></a>  
  
## <a name="determine-which-linking-method-to-use"></a>Hangi bağlama yöntemini kullanacağınızı belirleme  
  
Örtük bağlantılandırma veya açıkça bağlama kullanmak için uygulamanız için yapmanız gereken mimari bir karardır. Avantajları ve her yöntemin dezavantajları vardır.  
  
### <a name="implicit-linking"></a>Örtük bağlantılandırma  
  
Bir uygulamanın kodu bir dışa aktarılan DLL işlev çağırdığında örtük bağlantılandırma oluşur. Arama yürütülebilir dosyası için kaynak kodu derlendiğinde veya olduğunda DLL işlev çağrısı nesne kodunda dış işlev başvurusu oluşturur. Bu dış başvuruyu çözümlemek için uygulama DLL maker tarafından sağlanan içeri aktarma kitaplığı (.lib dosyası) ile bağlamanız gerekir.  
  
İçeri aktarma kitaplığını yalnızca DLL'yi ve DLL işlevleri çağrıları uygulamak için kodu içerir. İçeri aktarma kitaplığındaki bir dış işlevi bulma bu işlevin kodunun DLL'de olduğunu bildirir. DLL'ler için dış başvuruları çözümlemek için bağlayıcı yalnızca bilgi sistem işlemi başladığında DLL kodu nerede bulacağını söyleyen yürütülebilir dosyasına ekler.  
  
Sistem dinamik olarak bağlı başvuruları içeren bir program başladığında, gerekli DLL'leri bulmak için programın yürütülebilir dosyada bilgileri kullanır. DLL bulamazsanız, sistem işlemi sonlandırır ve hata raporları bir iletişim kutusu görüntüler. Aksi takdirde, sistem DLL modülleri işlemin adres alanına eşler.  
  
DLL'lerden herhangi birinde varsa, başlatma ve sonlandırma kodu için bir giriş noktası işlevi gibi `DllMain`, işletim sistemi işlevi çağırır. Giriş noktası işlevine geçirilen parametrelerden biri DLL gösteren bir kod işlemine iliştirme belirtir. Giriş noktası işlevi TRUE döndürmezse, sistem işlemi sonlandırır ve hata bildirir.  
  
Son olarak, sistem DLL işlevleri için başlangıç adresi sağlamak için işlemin yürütülebilir kodunu değiştirir.  
  
Bir programın kodunu rest gibi DLL kodu işlemi başlatıldığında ve yalnızca gerekli olduğunda belleğe yüklenen işlem adres alanına eşlenir. Sonuç olarak, `PRELOAD` ve `LOADONCALL` önceki Windows sürümlerinde artık yüklenirken denetlemek için .def dosyaları tarafından kullanılan kod özniteliklerinin anlamı yoktur.  
  
### <a name="explicit-linking"></a>Açıkça bağlantılandırma  
  
Çoğu uygulama kolay bağlama yöntemini kullanmak üzere olduğundan örtük bağlantılandırma kullanır. Ancak, ne zaman açıkça bağlama gerekli olduğu durumlar vardır. Açıkça bağlama kullanmak için bazı yaygın nedenler şunlardır:  
  
-   Uygulama çalışma zamanına kadar yükleyen DLL adını bilmez. Örneğin, uygulama başlatma sırasında bir yapılandırma dosyasından adını DLL ve dışarı aktarılan işlevleri elde edebilirsiniz.  
  
-   DLL işlem başlangıçta bulunmazsa örtük bağlantılandırma kullanan bir işleme işletim sistemi tarafından sonlandırıldı. Açıkça bağlama kullanan bir işleme, bu durumda sonlandırılmadığından ve hatadan kurtarmayı dener. Örneğin, işlem hata kullanıcıya bildirmek ve kullanıcınız dll dosyasının başka bir yol belirtin.  
  
-   Örtük bağlantılandırma kullanan bir işleme bağlı olmasını DLL'ler varsa da sonlandırılır bir `DllMain` başarısız işlev. Açıkça bağlama kullanan bir işlem, bu durumda sonlandırılmadı.  
  
-   Örtük olarak birçok dll dosyasına bağlanan bir uygulama uygulamanın yüklediği tüm DLL'ler Windows yükler yavaş olabilir. Başlangıç performansı artırmak için uygulamanın yalnızca diğer DLL'lerin bunları açıkça bağlanmak için gerekli kadar hemen yüklenirken bekleyin sonra gerekli ve bu DLL'ler örtük olarak bağlayabilirsiniz.  
  
-   Açıkça bağlantılandırma bir içeri aktarma kitaplığını kullanarak uygulama bağlama gereğini ortadan kaldırır. DLL değişiklikleri değiştirmek dışarı aktarma sıra numaraları neden oluyorsa açıkça bağlama kullanan uygulamalar bunlar çağırırsanız yeniden bağlamak zorunda değilsiniz `GetProcAddress` örtük bağlantılandırma kullanan uygulamalar için Yeniden Bağla gerekir ancak bir işlev ve sıralı bir değer değil, adını kullanarak yeni içeri aktarma kitaplığı.  
  
Dikkat edilmesi gereken açık bağlama iki tehlikesi şunlardır:  
  
-   DLL varsa bir `DllMain` giriş noktası işlevi, işletim sistemi işlevi çağırır çağıran iş parçacığının bağlamında `LoadLibrary`. DLL, önceki çağrısı nedeniyle işleme zaten bağlıysa, giriş noktası işlevi çağrılmaz `LoadLibrary` karşılık gelen hiçbir çağrısına sahip `FreeLibrary` işlevi. Açıkça bağlama sorunlara neden olabilir DLL kullanıyorsa, bir `DllMain` iş parçacığı zaten mevcut olduğundan bir işlem için her iş parçacığı başlatılmasını gerçekleştirmek için işlevi zaman `LoadLibrary` (veya `AfxLoadLibrary`) olarak adlandırılır başlatılmaz.  
  
-   DLL statik uzantılı verileri olarak bildirirse `__declspec(thread)`, açıkça bağlanmışsa koruma hatasına neden. DLL için yapılan bir çağrı tarafından yüklendikten sonra `LoadLibrary`, kod bu verileri başvurursa koruma hatasına neden oluyor. (Statik uzantılı veriler hem genel hem de yerel statik öğeler içerir.) Bu nedenle, DLL oluşturduğunuzda, iş parçacığı yerel depolama kullanmaktan kaçının veya dinamik olarak, DLL yükleme olası Tuzaklar hakkında DLL varsayılandır. Daha fazla bilgi için bkz: [iş parçacığı yerel depolaması bir dinamik bağlantı kitaplığı (Windows SDK) kullanarak](http://msdn.microsoft.com/library/windows/desktop/ms686997).  
  
<a name="linking-implicitly"></a>  
  
## <a name="how-to-link-implicitly-to-a-dll"></a>Bir DLL'e örtük olarak bağlanma  
  
Örtük bağlantılandırma DLL kullanmak için İstemci yürütülebilir dosyalar, DLL sağlayıcıdan bu dosyaları edinmeniz gerekir:  
  
-   Dışarı aktarılan verileri, İşlevler ve/veya C++ sınıfları dll bildirimleri içeren bir veya daha fazla üst bilgi dosyaları (.h dosyaları). Sınıfları, işlevleri ve DLL tarafından dışarı aktarılan verileri tüm işaretlenmelidir `__declspec(dllimport)` üstbilgi dosyasında. Daha fazla bilgi için bkz: [dllexport, dllimport](../cpp/dllexport-dllimport.md).  
  
-   Yürütülebilir dosyanın içine bağlamak için içeri aktarma kitaplığı. DLL oluşturulduğunda bağlayıcı içeri aktarma kitaplığı oluşturur. Daha fazla bilgi için bkz: [. LIB dosyaları](../build/reference/dot-lib-files-as-linker-input.md).  
  
-   Gerçek DLL dosyası.  
  
Örtük bağlantılandırma DLL kullanmak için yürütülebilir bir dosya verileri, işlevleri veya dışarı aktarılan verileri, işlevleri ve sınıfları çağrıları içeren her bir kaynak dosyadaki DLL tarafından dışarı aktarılan C++ sınıfları bildirme üstbilgi dosyaları eklemeniz gerekir. Kodlama açısından, dışarı aktarılan işlevler çağrıları herhangi bir diğer işlev çağrısıyla aynıdır.  
  
Çağıran yürütülebilir dosyayı oluşturmak için içeri aktarma kitaplığı ile bağlamanız gerekir. Bir dış derleme görevleri dosyası veya oluşturma sistemi kullanıyorsanız, diğer nesne (.obj) dosyaları listelediğiniz yerde içeri aktarma kitaplığını ya da, bağlantı kitaplıkları dosya adını belirtin.  
  
İşletim sistemi çağıran çalıştırılabiliri yüklediğinde DLL dosyasını bulun kurabilmesi gerekir. Bu uygulamanız gerekir veya dağıtma, uygulama yüklendiğinde DLL varlığını doğrula anlamına gelir.   
  
<a name="linking-explicitly"></a>  
  
## <a name="how-to-link-explicitly-to-a-dll"></a>Bir DLL'e açıkça bağlanma  
  
Açıkça bağlama tarafından DLL kullanmak için uygulamalar çalışma zamanında DLL'i açıkça yüklemek için işlev çağrısı yapmanız gerekir. Bir DLL'e açıkça bağlanmak için bir uygulama gerekir:  
  
-   Çağrı [LoadLibrary](loadlibrary-and-afxloadlibrary.md), `LoadLibraryEx`, veya DLL'i ve modül işleyiciyi yüklemek için benzer bir işlev.  
  
-   Çağrı [GetProcAddress](getprocaddress.md) bir işlev işaretçisi her uygulama çağıran işlev dışarı. DLL işlevlerini işaretçi üzerinden uygulamaları çağırmak için bu yüzden bir içeri aktarma kitaplığı ile bağlantı gerek yoktur derleyici dış başvuru oluşturmaz. Bununla birlikte, olmalıdır bir `typedef` veya `using` çağırın dışarı aktarılan işlevlerin çağrısı imza tanımlayan ifade.   
  
-   Çağrı [FreeLibrary](freelibrary-and-afxfreelibrary.md) DLL ile işiniz bittiğinde.  
  
Örneğin, bu örnek işlevi çağırır `LoadLibrary` "MyDLL" adlı bir DLL'yi çağrılar `GetProcAddress` "DLLFunc1" adlı bir işlev işaretçisi almak için işlevi çağırır ve sonucu kaydeder ve sonra çağırır `FreeLibrary` DLL kaldırmak için. 
  
```C  
#include "windows.h"

typedef HRESULT (CALLBACK* LPFNDLLFUNC1)(DWORD,UINT*);  

HRESULT LoadAndCallSomeFunction(DWORD dwParam1, UINT * puParam2)  
{
    HINSTANCE hDLL;               // Handle to DLL  
    LPFNDLLFUNC1 lpfnDllFunc1;    // Function pointer  
    HRESULT hrReturnVal;  
      
    hDLL = LoadLibrary("MyDLL");  
    if (NULL != hDLL)  
    {  
        lpfnDllFunc1 = (LPFNDLLFUNC1)GetProcAddress(hDLL, "DLLFunc1");  
        if (NULL != lpfnDllFunc1)  
        {  
            // call the function  
            hrReturnVal = lpfnDllFunc1(dwParam1, puParam2);  
        }  
        else  
        {  
            // report the error  
            hrReturnVal = ERROR_DELAY_LOAD_FAILED;  
        }
        FreeLibrary(hDLL);
    }
    else
    {
        hrReturnVal = ERROR_DELAY_LOAD_FAILED;
    }  
    return hrReturnVal;
}
```  
  
Farklı olarak bu örnekte, çoğu durumda, çağırmalıdır `LoadLibrary` ve `FreeLibrary` uygulamanızda özellikle birden çok işlevi DLL çağrı veya DLL arama için kullanacaksanız belirli bir DLL için yalnızca bir kez işlevleri sürekli olarak.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?  
  
-   [İçeri aktarma kitaplıkları ve dışarı aktarma dosyalarıyla çalışma](../build/reference/working-with-import-libraries-and-export-files.md)  
  
-   [DLL bulmak için Windows tarafından kullanılan arama yolu](../build/search-path-used-by-windows-to-locate-a-dll.md)  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'leri](../build/dlls-in-visual-cpp.md)