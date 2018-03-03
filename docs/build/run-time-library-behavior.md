---
title: "DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
dev_langs:
- C++
helpviewer_keywords:
- DLLs [C++], entry point function
- process detach [C++]
- process attach [C++]
- DLLs [C++], run-time library behavior
- DllMain function
- _CRT_INIT macro
- _DllMainCRTStartup method
- run-time [C++], DLL startup sequence
- DLLs [C++], startup sequence
ms.assetid: e06f24ab-6ca5-44ef-9857-aed0c6f049f2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 75bf84eeaf9277c5cf037c4fa59c28d109d95856
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı  
  
Varsayılan olarak Visual C++ kullanarak bir dinamik bağlantı kitaplığı (DLL) yapılandırdığınızda, bağlayıcı Visual C++ çalışma zamanı kitaplığı (VCRuntime) içerir. VCRuntime başlatmak ve C/C++ yürütülebilir sonlandırmak için gerekli kod içerir. Bir DLL'e bağlandığında VCRuntime kodu olarak adlandırılan bir iç DLL giriş noktası işlevi sağlar `_DllMainCRTStartup` eklemek veya bir işlem veya iş parçacığı ayırmak için DLL Windows işletim sistemi iletileri işler. `_DllMainCRTStartup` İşlevi yığın arabellek güvenlik C çalışma zamanı kitaplığı (CRT) başlatma ve sonlandırma, ayarlama gibi temel görevleri gerçekleştirir ve statik ve genel nesneler için Kurucular ve Yıkıcılar çağırır. `_DllMainCRTStartup`Ayrıca çağrıları kanca işlevleri WinRT, MFC ve ATL kendi başlatma ve sonlandırma gerçekleştirmek için gibi diğer kitaplıkları için. Bu başlatma, CRT ve diğer kitaplıkları, yanı sıra statik değişkenler, başlatılmamış durumda bırakılır. Statik olarak bağlantılı CRT veya dinamik olarak bağlı CRT DLL DLL kullanıp kullanmadığını aynı VCRuntime iç başlatma ve sonlandırma yordamları denir.  
  
## <a name="default-dll-entry-point-dllmaincrtstartup"></a>Varsayılan DLL giriş noktası _DllMainCRTStartup  
  
Windows, genellikle adlı isteğe bağlı giriş noktası işlevi, tüm DLL'ler içerebilir `DllMain`, yani başlatma ve sonlandırma için çağrılır. Bu ayırmak veya gerektiği gibi ek kaynakları serbest bırakmak için fırsatı sunar. Windows dört durumda giriş noktası işlevi çağırır: işlem ekleme, işlem ayırma, iş parçacığı ekleme ve iş parçacığı ayırma. DLL işlem adres alanına bunu kullanan bir uygulama yüklendiğinde veya uygulama çalışma zamanında DLL istediğinde yüklendiğinde, işletim sistemi DLL verileri ayrı bir kopyasını oluşturur. Bu adlı *işlem ekleme*. *İş parçacığı ekleme* DLL yüklendiği işlem yeni bir iş parçacığı oluşturduğunda gerçekleşir. *İş parçacığı ayırma* iş parçacığı sonlandırıldığında oluşur ve *işlem ayırma* DLL artık gerekli değildir ve bir uygulama tarafından yayımlanan durumdur. İşletim sistemi DLL giriş noktası için ayrı bir çağrısı geçirme bu olayların her biri, için yapar bir *neden* her olay türü için bağımsız değişken. Örneğin, işletim sistemi gönderir `DLL_PROCESS_ATTACH` olarak *neden* işlem sinyal bağımsız değişkeni ekleyin.  
  
VCRuntime kitaplığı adı verilen bir giriş noktası işlevi sunar `_DllMainCRTStartup` varsayılan başlatma ve sonlandırma işlemleri işlemek için. Üzerinde işlem ekleme, `_DllMainCRTStartup` işlevi arabellek güvenlik denetimlerini ayarlar, CRT ve diğer kitaplıkları başlatır, çalışma zamanı türü bilgileri başlatır, başlatır ve statik ve yerel olmayan veriler için oluşturucular çağırır, iş parçacığı yerel depolama başlatır , her attach için bir iç statik sayaç artırılır ve bir kullanıcının veya kitaplık-sağladığı çağırır `DllMain`. İşlem üzerinde ayırma, şu adımları ters işlevi geçer. Çağırır `DllMain`, azaltır iç sayaç yıkıcı çağrıları, çağrıları CRT sonlandırma işlevleri ve kayıtlı `atexit` işlevler ve diğer bir sonlandırma kitaplıklarının bildirir. Ek Sayaç sıfıra gittiğinde işlevi döndürür `FALSE` DLL kaldırılamıyor Windows belirtmek için. `_DllMainCRTStartup` İşlevi olarak da adlandırılır sırasında iş parçacığı ekleme ve iş parçacığı ayırma. Bu durumda, VCRuntime kod hiçbir ek başlatma veya kendi başına sonlandırma yapar ve yalnızca çağırır `DllMain` boyunca ileti geçirmek için. Varsa `DllMain` döndürür `FALSE` hatası, sinyal işleminden attach `_DllMainCRTStartup` çağrıları `DllMain` yeniden ve geçirir `DLL_PROCESS_DETACH` olarak *neden* bağımsız değişkeni, sonra kalan geçer sonlandırma işlemi.  
  
Visual C++, varsayılan giriş noktası DLL'lerde oluştururken `_DllMainCRTStartup` tarafından sağlanan VCRuntime bağlı olarak otomatik olarak. Kullanarak, DLL için bir giriş noktası işlevi belirtmeniz gerekmez [/Entry (giriş noktası simgesi)](../build/reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.  
  
> [!NOTE]
> / Entry kullanarak bir DLL için başka bir giriş noktası işlevi belirlemek mümkün olsa: bağlayıcı seçeneği önerilmez, çünkü giriş noktası işlevinizin her şeyi yinelenen zorunda, `_DllMainCRTStartup` , aynı sırayla yapar. VCRuntime davranışını yinelenen olanak tanıyan işlevler sağlar. Örneğin, çağırabilirsiniz [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) hemen desteklemek için işlem üzerinde ekleme [/GS (arabellek güvenlik denetimi)](../build/reference/gs-buffer-security-check.md) denetleme seçeneği arabellek. Çağırabilirsiniz `_CRT_INIT` işlevi, kalan DLL başlatma veya sonlandırma işlevleri gerçekleştirmek için giriş noktası işlevi, aynı parametreleri geçirme.  
  
<a name="initializing-a-dll"></a>  
  
## <a name="initialize-a-dll"></a>DLL başlatma  
  
DLL, DLL yüklendiğinde yürütülmelidir başlatma kodu olabilir. Kendi DLL başlatma ve sonlandırma işlevleri gerçekleştirmek sırayla `_DllMainCRTStartup` adlı bir işlev çağrılarını `DllMain` sağlayan. `DllMain` İmza DLL giriş noktası için gerekli olması gerekir. Varsayılan giriş noktası işlevi `_DllMainCRTStartup` çağrıları `DllMain` aynı parametreleri kullanarak Windows tarafından geçirildi. Belirtmezseniz, varsayılan olarak, bir `DllMain` işlevi, Visual C++ sizin için bir sağlar ve bu şekilde `_DllMainCRTStartup` her zaman çağırmak için bir şey vardır. Bu DLL başlatmak gerekmiyorsa olduğunu DLL dosyanızı oluştururken yapmanız gereken özel bir şey anlamına gelir.  
  
İçin kullanılan imzayı budur `DllMain`:  
  
```cpp  
#include <windows.h>  
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```  
  
Bazı kitaplıklar kaydırma `DllMain` sizin için işlevi. Örneğin, normal bir MFC DLL'ine uygulamak `CWinApp` nesnenin `InitInstance` ve `ExitInstance` başlatma ve sonlandırma DLL tarafından gerekli gerçekleştirmek için üye işlevleri. Daha fazla ayrıntı için bkz: [Normal MFC DLL'leri başlatma](#initializing-regular-dlls) bölümü.  
  
> [!WARNING]
> Güvenli bir şekilde bir DLL giriş noktası yapabilecekleriniz hakkında önemli sınırları vardır. Bkz: [genel en iyi yöntemler](https://msdn.microsoft.com/library/windows/desktop/dn633971#general_best_practices) çağırmak için güvensiz belirli Windows API'leri için `DllMain`. Herhangi bir şey ancak gerekiyorsa sonra basit başlatma yapın, bir başlangıç işlevi DLL için. Sonra başlatma işlevi çağırmak için uygulamalar gerektirebilir `DllMain` sahip çalıştırma ve bunlar önce çağırın diğer işlevleri DLL'de.  
  
<a name="initializing-non-mfc-dlls"></a>  
  
### <a name="initialize-ordinary-non-mfc-dlls"></a>Sıradan (MFC olmayan) DLL'leri başlatma  
  
VCRuntime tarafından sağlanan kullanın (MFC olmayan) normal DLL'lerde kendi başlatılmasını gerçekleştirmek için `_DllMainCRTStartup` giriş noktası DLL kaynak kodunuz adlı bir işlev içermelidir `DllMain`. Aşağıdaki kod tanımının gösteren temel bir çatı sunar `DllMain` aşağıdaki gibi görünmelidir:  
  
```cpp  
#include <windows.h>
  
extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module 
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved)  // reserved
{
    // Perform actions based on the reason for calling.
    switch (reason) 
    { 
    case DLL_PROCESS_ATTACH:
        // Initialize once for each new process.
        // Return FALSE to fail DLL load.
        break;

    case DLL_THREAD_ATTACH:
        // Do thread-specific initialization.
        break;

    case DLL_THREAD_DETACH:
        // Do thread-specific cleanup.
        break;

    case DLL_PROCESS_DETACH:
        // Perform any necessary cleanup.
        break;
    }
    return TRUE;  // Successful DLL_PROCESS_ATTACH.
}
```  
  
> [!NOTE]
> Eski Windows SDK Belgeleri DLL giriş noktası işlevi gerçek adını Entry seçeneğiyle komut satırı bağlayıcı üzerinde belirtilmelidir söyler. Visual C++ ile giriş noktası işlevinizin adı ise/Entry seçeneğini kullanmanıza gerek yoktur `DllMain`. Aslında, adını ve/Entry seçeneğini kullanırsanız, giriş noktası işlevinizi dışında `DllMain`, giriş noktası işlevinizin aynı başlatma, çağrılar sürece CRT düzgün başlatılmamış `_DllMainCRTStartup` yapar.  
  
<a name="initializing-regular-dlls"></a>  
  
### <a name="initialize-regular-mfc-dlls"></a>Normal MFC DLL'leri başlatma  
  
Normal MFC DLL'leri olduğundan bir `CWinApp` nesnesi, gerçekleştirdikleri başlatma ve sonlandırma görevlerini MFC uygulaması ile aynı konumda: içinde `InitInstance` ve `ExitInstance` üye işlevleri DLL'nin `CWinApp`-türetilen sınıf. MFC sağladığından bir `DllMain` tarafından çağrılır işlevi `_DllMainCRTStartup` için `DLL_PROCESS_ATTACH` ve `DLL_PROCESS_DETACH`, kendi yazdığınız değil `DllMain` işlevi. MFC tarafından sağlanan `DllMain` işlev çağrıları `InitInstance` zaman, DLL yüklendiğinde ve çağırır `ExitInstance` DLL kaldırılmadan önce.  
  
Normal bir MFC DLL çoklu iş parçacığı çağırarak izlemek [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) ve [TlsGetValue](http://msdn.microsoft.com/library/windows/desktop/ms686812) içinde kendi `InitInstance` işlevi. Bu işlevler iş parçacığına özgü veri izlemek izin verme.  
  
Dinamik olarak MFC'ye, hata ayıklama MFC uzantı DLL'leri MFCO herhangi MFC OLE, MFC veritabanı (veya DAO) kullanıyorsanız veya MFC yuva desteği, sırasıyla bağlantılar normal, MFC DLL*sürüm*D.dll, MFCD*sürüm*D.dll ve MFCN*sürüm*D.dll (burada *sürüm* sürüm numarası) otomatik olarak bağlanır. Her biri, Normal MFC DLL içinde kullanıyorsanız bu DLL'ler için aşağıdaki önceden tanımlanmış başlatma işlevlerinden birini çağırmalıdır `CWinApp::InitInstance`.  
  
|MFC destek türü|Çağrılacak başlatma işlevi|  
|-------------------------|-------------------------------------|  
|MFC OLE (MFCO*sürüm*D.dll)|`AfxOleInitModule`|  
|MFC veritabanı (MFCD*sürüm*D.dll)|`AfxDbInitModule`|  
|MFC yuva (MFCN*sürüm*D.dll)|`AfxNetInitModule`|  
  
<a name="initializing-extension-dlls"></a>  
  
### <a name="initialize-mfc-extension-dlls"></a>MFC uzantı DLL'leri başlatma  
  
MFC uzantı DLL'leri olmadığı için bir `CWinApp`-türetilen (Normal MFC DLL'lerde) nesnesini, başlatma ve sonlandırma kodunuzu eklemeniz gerekir `DllMain` MFC DLL Sihirbazı'nın oluşturduğu işlevi.  
  
 Sihirbaz aşağıdaki kodu MFC uzantı DLL'leri sağlar. Kodda, `PROJNAME` projenizin adı için bir yer tutucudur.  
  
```cpp  
#include "stdafx.h"  
#include <afxdllx.h>  
  
#ifdef _DEBUG  
#define new DEBUG_NEW  
#undef THIS_FILE  
static char THIS_FILE[] = __FILE__;  
#endif  
static AFX_EXTENSION_MODULE PROJNAMEDLL = { NULL, NULL };  
  
extern "C" int APIENTRY  
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID lpReserved)  
{  
   if (dwReason == DLL_PROCESS_ATTACH)  
   {  
      TRACE0("PROJNAME.DLL Initializing!\n");  
  
      // MFC extension DLL one-time initialization  
      AfxInitExtensionModule(PROJNAMEDLL,   
                                 hInstance);  
  
      // Insert this DLL into the resource chain  
      new CDynLinkLibrary(Dll3DLL);  
   }  
   else if (dwReason == DLL_PROCESS_DETACH)  
   {  
      TRACE0("PROJNAME.DLL Terminating!\n");  
   }  
   return 1;   // ok  
}  
```  
  
Yeni bir oluşturma `CDynLinkLibrary` başlatma sırasında nesne sağlar MFC uzantı DLL dışarı aktarmak için `CRuntimeClass` nesneleri veya istemci uygulaması kaynaklarına.  
  
Bir veya daha fazla Normal MFC DLL'leri DLL'den MFC uzantısı kullanacaksanız, oluşturan bir başlatma işlevi dışarı aktarmanız gerekir bir `CDynLinkLibrary` nesnesi. Bu işlev her MFC uzantı DLL'si kullanan Normal MFC DLL'leri çağrılmalıdır. Bu başlatma işlevi çağırmak için bir uygun bir yerdir `InitInstance` Normal MFC DLL üye işlevini `CWinApp`-MFC uzantı DLL dışarı aktarılan sınıfları veya işlevleri herhangi birini kullanmadan önce nesne türetilmiş.  
  
İçinde `DllMain` MFC DLL Sihirbazı'nın ürettiği çağrısı `AfxInitExtensionModule` modülünün çalışma zamanı sınıfları yakalar (`CRuntimeClass` yapıları) yanı sıra kendi nesne oluşturucuları (`COleObjectFactory` nesneleri) için kullanmak `CDynLinkLibrary` nesnesi oluşturulur. Dönüş değerini denetlemelisiniz `AfxInitExtensionModule`; sıfır değeri döndürdüyse `AfxInitExtensionModule`, sıfırdan dönün, `DllMain` işlevi.  
  
MFC uzantı DLL'si açıkça bir yürütülebilir dosyaya bağlı (yürütülebilir çağrıları anlamına `AfxLoadLibrary` DLL'e bağlanmak için), bir çağrı ekleyin `AfxTermExtensionModule` üzerinde `DLL_PROCESS_DETACH`. Bu işlev her işlem MFC uzantı DLL'si ayrıldığında MFC uzantı DLL temizlemesini MFC verir (işlem çıktığında veya DLL sonucu olarak kaldırıldığında olur olur bir `AfxFreeLibrary` çağrısı). MFC uzantı DLL'si örtük olarak çağrısı uygulama bağlanacağı varsa `AfxTermExtensionModule` gerekli değildir.  
  
MFC uzantı DLL'leri bağlantı açıkça çağırmalısınız uygulamaları `AfxTermExtensionModule` DLL boşaltma olduğunda. Ayrıca kullanması gereken `AfxLoadLibrary` ve `AfxFreeLibrary` (Win32 işlevleri yerine `LoadLibrary` ve `FreeLibrary`) uygulama birden çok iş parçacığı kullanıyorsa. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantı DLL yüklendiğinde ve kaldırıldığında genel MFC durumunu bozuk olmayan yürütülen başlatma ve kapatma kodunun sağlar.  
  
MFCx0.dll tamamen başlatılmış olduğundan `DllMain` olduğu olarak adlandırılan, bellek ayırabilir ve MFC işlevleri içinde çağırabilirsiniz `DllMain` (aksine, MFC 16-bit sürümü).  
  
Uzantı DLL'leri ilgilenebilmek işleme çoklu iş parçacığı `DLL_THREAD_ATTACH` ve `DLL_THREAD_DETACH` içinde durumlarda `DllMain` işlevi. Bu durumların geçirilecek `DllMain` zaman iş parçacığı ekleme ve DLL'den ayırma. Çağırma [TlsAlloc](http://msdn.microsoft.com/library/windows/desktop/ms686801) DLL zaman ekleme iş parçacığı yerel depolaması (TLS) dizinler DLL'e bağlı her iş parçacığı için korumak DLL sağlar.  
  
Üstbilgi dosyası yapı tanımları tanımı gibi MFC uzantı DLL'leri içinde kullanılan yapılar için özel tanımları içerir Not `AFX_EXTENSION_MODULE` ve `CDynLinkLibrary`. MFC uzantı DLL bu üst bilgi dosyasını içermesi gerekir.  
  
> [!NOTE]
>  Tanımlamak ne herhangi birini tanımsız olduğundan önemlidir `_AFX_NO_XXX` Stdafx.h makrolarındaki. Yalnızca belirli hedef platformu veya bu özelliği destekleyen olup olmadığını denetleme amacıyla bu makroları mevcut. Bu makroları denetlemek için program yazabilirsiniz (örneğin, `#ifndef _AFX_NO_OLE_SUPPORT`), ancak programınız hiçbir zaman tanımlayın veya bu makroları tanımsız.  
  
Çoklu iş parçacığı kullanımı tanıtıcıları dahil bir örnek başlatma işlevi [kullanarak iş parçacığı yerel depolama dinamik bağlantı kitaplığı](http://msdn.microsoft.com/library/windows/desktop/ms686997) Windows SDK'sındaki. Örnek olarak adlandırılan bir giriş noktası işlevi içerdiğini unutmayın `LibMain`, ancak bu işlev ad vermemelisiniz `DllMain` böylece MFC ve C çalışma zamanı kitaplıkları ile çalışır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
  
[Visual C++'ta DLL'ler](../build/dlls-in-visual-cpp.md)  
[DllMain giriş noktası](https://msdn.microsoft.com/library/windows/desktop/ms682583.aspx)  
[Dinamik bağlantı kitaplığı en iyi uygulamalar](https://msdn.microsoft.com/library/windows/desktop/dn633971.aspx)  