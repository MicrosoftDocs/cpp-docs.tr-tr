---
title: MFC DLL sık sorulan sorular | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- troubleshooting [C++], DLLs
- DLLs [C++], frequently asked questions
- FAQs [C++], DLLs
ms.assetid: 09dd068e-fc33-414e-82f7-289c70680256
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f5740989562aea799f3a49adfa464e2c460acb3
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32372516"
---
# <a name="dll-frequently-asked-questions"></a>Sıkça Sorulan DLL Soruları  
  
Aşağıdaki DLLs hakkında bazı sık sorulan sorular (SSS) istenir.  
    
-   [MFC DLL çoklu iş parçacığı oluşturabilir miyim?](#mfc_multithreaded_1)  

-   [Çok iş parçacıklı uygulamada farklı iş parçacıklarındaki MFC DLL'ine erişebilir mi?](#mfc_multithreaded_2)  
  
-   [Herhangi bir MFC sınıfları veya bir MFC DLL'inde kullanılamayan işlevler vardır?](#mfc_prohibited_classes)  
  
-   [Yükleme yaparken istemci uygulamanın performansını artırmak için hangi iyileştirme tekniklerini kullanmalıyım?](#mfc_optimization)  
  
-   [My Normal MFC DLL bellek sızıntısı yoktur, ancak kodum doğru görünüyor. Bellek sızıntısı nasıl bulabilirim?](#memory_leak)  

## <a name="mfc_multithreaded_1"></a> MFC DLL çoklu iş parçacığı oluşturabilir miyim?  
  
Win32 iş parçacığı yerel depolaması (TLS) işlevleri gibi kullandığı sürece başlatma sırasında bir MFC DLL güvenli bir şekilde birden çok iş parçacığı oluşturabilir mi dışında **TlsAlloc** iş parçacığı yerel depolama alanı ayırmak için. Ancak, bir MFC DLL kullanıyorsa **__declspec(thread)** iş parçacığı yerel depolama alanı ayırmak için istemci uygulaması örtük olarak DLL'e bağlanması gerekir. İstemci uygulaması açıkça çağrısı DLL bağlar, **LoadLibrary** başarıyla DLL yüklemez. MFC DLL'leri içinde birden çok iş parçacığı oluşturma hakkında daha fazla bilgi için Bilgi Bankası makalesi, "Sorun: çağırma LoadLibrary() için yük bir DLL olduğunu sahip statik TLS" (Q118816) bakın. DLL'lerde iş parçacığı yerel değişkenleri hakkında daha fazla bilgi için bkz: [iş parçacığı](../cpp/thread.md).
  
 Başlatma sırasında yeni bir MFC iş parçacığı oluşturan bir MFC DLL, bir uygulama tarafından yüklendiğinde yanıt vermeyi durdurur. Her bir iş parçacığı çağırarak oluşturulduğunda bu içerir `AfxBeginThread` veya `CWinThread::CreateThread` içinde:  
  
-   `InitInstance` , Bir `CWinApp`-normal bir MFC DLL nesnesinde türetilmiş.  
  
-   Sağlanan `DllMain` veya **RawDllMain** normal bir MFC DLL işlev.  
  
-   Sağlanan `DllMain` veya **RawDllMain** MFC uzantı DLL işlevi.  
  
 Bilgi Bankası makalesi, "Sorun: olamaz oluşturma bir MFC iş parçacığı sırasında DLL başlatma" (Q142243) başlatma sırasında iş parçacığı oluşturma hakkında daha fazla bilgi için bkz.  
  
## <a name="mfc_multithreaded_2"></a> Çok iş parçacıklı uygulamada farklı iş parçacıklarındaki MFC DLL'ine erişebilir mi?
Birden çok iş parçacıklı uygulamalar farklı iş parçacığı tarafından dinamik olarak MFC'ye Normal MFC DLL'leri ve MFC uzantı DLL'leri erişebilir. Ve sürüm 4.2 Visual C++ itibariyle, uygulama statik olarak MFC'ye birden çok iş parçacığı uygulama içinde oluşturulan bağlantı Normal MFC DLL'leri erişebilir.  
  
 4.2 sürümü önce statik olarak MFC'ye bağlı normal bir MFC DLL için yalnızca bir dış iş parçacığı bağlayamıyor. Bilgi Bankası makalesi, statik olarak MFC'ye (önce Visual C++ sürümü 4.2) birden çok iş parçacığı bağlantı Normal MFC DLL'leri erişim kısıtlamaları hakkında daha fazla bilgi için bkz: "birden çok iş parçacığı ve MFC _USRDLLs" (Q122676).  
  
 Visual C++ belgelerinde USRDLL terimi artık kullanılmayan unutmayın. Statik olarak MFC'ye bağlı normal bir MFC DLL önceki USRDLL ile aynı özelliklere sahiptir.  


## <a name="mfc_prohibited_classes"></a> Herhangi bir MFC sınıfları veya bir MFC DLL'inde kullanılamayan işlevler vardır?
Uzantı DLL'leri kullanma `CWinApp`-türetilmiş sınıf istemci uygulaması. Kullanıcıların kendi sahip olmaları değil `CWinApp`-türetilmiş sınıf.  
  
Normal MFC DLL'leri olmalıdır bir `CWinApp`-türetilmiş sınıf ve o uygulama sınıfın tek bir nesne bir MFC uygulamalarında olduğu gibi. Farklı `CWinApp` nesne bir uygulamanın `CWinApp` DLL nesnesinin ana ileti göndericisi sahip değil.  
  
 Çünkü unutmayın `CWinApp::Run` mekanizması bir DLL için geçerli değildir, uygulamanın ana ileti göndericisi. DLL kalıcı olmayan iletişim kutuları açılır ya da kendi ana penceresi varsa, uygulamanın ana ileti göndericisi sırayla çağıran DLL'den dışarı aktarılmış bir yordam çağırmalıdır `CWinApp::PreTranslateMessage` üye işlevi DLL uygulama nesnesi.  

## <a name="mfc_optimization"></a> Hangi iyileştirme tekniklerini istemci uygulaması geliştirmek için kullanmalıyım&#39;yüklenirken s performans?
DLL bir sıradan değiştirme MFC statik olarak bağlı normal bir MFC DLL ise dinamik olarak MFC'ye bağlı MFC DLL dosya boyutunu azaltır.  
  
 DLL dışarı aktarılan işlevler çok sayıda varsa, .def dosyası işlevlerini dışarı aktarmak için kullanın (kullanmak yerine **__declspec(dllexport)**) ve .def dosyası kullanma [NONAME özniteliği](../build/exporting-functions-from-a-dll-by-ordinal-rather-than-by-name.md) her işlevi dışarı. NONAME özniteliği yalnızca sıra sayısı değerini ve dosya boyutunu azaltır DLL dışarı aktarım tablosunda depolanması için işlev adı neden olur.  
  
 Bir uygulamaya dolaylı olarak bağlantılı DLL'ler uygulama yüklendiğinde yüklenir. Yükleme performansını artırmak için DLL farklı DLL'lere bölmeyi deneyin. Bir DLL'e hemen sonra çağrı yapan uygulamanın gereken tüm işlevleri koyun ve dolaylı olarak bağlayın çağıran uygulama vardır. Çağrı yapan uygulamanın hemen gerekmez diğer işlevleri başka bir DLL'e koyun ve sahip uygulama açıkça bağlanmak için bu DLL. Daha fazla bilgi için bkz: [hangi bağlama yöntemini kullanacağınızı belirleme](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use).  

## <a name="memory_leak"></a> Var.&#39;s my Normal MFC DLL ancak kodumu bellek sızıntısı ince arar. Bellek sızıntısı nasıl bulabilirim?  
  
Olası bir nedeni de bellek sızıntısı MFC ileti işleyicisi işlevler içinde kullanılan geçici nesneler oluşturmasıdır. MFC uygulamalarında, bu geçici nesneleri otomatik olarak içinde temizlenmesini `CWinApp::OnIdle()` iletileri işleme Between çağrılan işlev. Ancak, MFC dinamik bağlantı kitaplıklarını (DLL'ler) içinde `OnIdle()` işlevi otomatik olarak çağrılmaz. Sonuç olarak, geçici nesneler otomatik olarak temizlenir değil. Geçici nesneleri temizlemek için DLL'i açıkça çağırmalıdır `OnIdle(1)` düzenli aralıklarla.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)