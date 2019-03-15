---
title: DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı
ms.date: 11/04/2016
f1_keywords:
- _DllMainCRTStartup
- CRT_INIT
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
ms.openlocfilehash: ea970f010e86d655963485339c48b8f7d36d6270
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57811445"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLL'ler ve Visual C++ çalışma zamanı kitaplığı davranışı

Bağlayıcı, varsayılan olarak Visual C++'ı kullanarak bir dinamik bağlantı kitaplığı (DLL) oluşturduğunuzda, Visual C++ çalışma zamanı kitaplığı (VCRuntime) içerir. VCRuntime başlatmak ve C/C++ yürütülebilir sonlandırmak için gereken kodu içerir. Bir DLL içine bağlandığında VCRuntime kod olarak adlandırılan bir iç DLL giriş noktası işlevi sağlar `_DllMainCRTStartup` eklemek veya bir işlem veya iş parçacığı ayırma dll Windows işletim sistemi iletileri işler. `_DllMainCRTStartup` İşlevi C çalışma zamanı kitaplığı (CRT) başlatma ve sonlandırma ayarlama, yığın arabelleği güvenlik gibi temel görevleri gerçekleştirir ve statik ve genel nesneler için oluşturucular ve Yıkıcılar için çağırır. `_DllMainCRTStartup` Ayrıca aramaları kanca işlevleri WinRT, MFC ve ATL gerçekleştirmek için kendi başlatma ve sonlandırma gibi diğer kitaplıkları. Bu başlatma, CRT ve diğer kitaplıkları, hem de, statik değişkenler, başlatılmamış bir durumda bırakılır. DLL'nizi MFC'ye statik olarak bağlı bir CRT veya dinamik olarak bağlı bir CRT DLL kullanıp kullanmayacağını aynı VCRuntime iç başlatma ve sonlandırma rutinleri çağrılır.

## <a name="default-dll-entry-point-dllmaincrtstartup"></a>Varsayılan DLL giriş noktası _DllMainCRTStartup

Windows tüm DLL'leri genellikle adlı bir isteğe bağlı bir giriş noktası işlevi içerebilir `DllMain`, yani başlatma ve sonlandırma için çağrılır. Bu, tahsis edin ya da gerektiği gibi ek kaynakları serbest bırakmak için bir fırsat sağlar. Windows, dört durumda giriş noktası işlevini çağırır: işleme, işlemden ayrılma, iş parçacığı ekleme ve iş parçacığı ayırma. Bir DLL bir işlemin adres alanına onu kullanan bir uygulama yüklendiğinde veya uygulama çalışma zamanında DLL istediğinde yüklendiğinde işletim sistemi DLL'si verileri ayrı bir kopyasını oluşturur. Bu adlandırılır *bir sürece iliştirilip*. *İş parçacığı ekleme* DLL yüklendiği işlem yeni bir iş parçacığı oluşturduğunda gerçekleşir. *İş parçacığı ayırma* iş parçacığı sonlandığında gerçekleşir ve *işlemden ayrılma* DLL artık gerekli değildir ve bir uygulama tarafından yayımlanır. İşletim sistemi ayrı DLL giriş noktası her geçirme, bu olaylar için çağrıda bir *neden* her bir olay türü için bağımsız değişken. Örneğin, işletim Sisteminin gönderdiği `DLL_PROCESS_ATTACH` olarak *neden* işlemini göstermek için bağımsız değişken ekleyin.

VCRuntime kitaplığı adlı bir giriş noktası işlevi sağlar `_DllMainCRTStartup` varsayılan başlatma ve sonlandırma işlemleri işlemek için. İşlemi eklemek, `_DllMainCRTStartup` işlevi arabellek güvenlik denetimi ayarlar, CRT ve diğer kitaplıkları başlatır, çalışma zamanı türü bilgileri başlatır, başlatır ve statik ve yerel olmayan veriler için oluşturucuları çağırır, iş parçacığı-yerel depolamayı başlatır , her ek için bir iç statik sayacını artırır ve daha sonra bir kullanıcı tarafından veya kitaplığı-sağlanan çağırır `DllMain`. Ayırma işlemi, işlev bu adımları tersten geçer. Çağrı `DllMain`, azaltır, iç sayaç yok ediciler çağırır, çağrıları CRT sonlandırma işlevleri ve kayıtlı `atexit` işlevleri ve diğer tüm kitaplıkları sonlandırma bildirir. Ek Sayaç sıfıra gittiğinde işlevi döndürür `FALSE` Windows için DLL kaldırılabilip kaldırılamayacağını belirtmek için. `_DllMainCRTStartup` İşlevi olarak da adlandırılır sırasında iş parçacığı ekleme ve iş parçacığı ayırma. Bu gibi durumlarda, VCRuntime kod hiçbir ek başlatma veya sonlandırma kendi yapar ve yalnızca çağıran `DllMain` boyunca iletinin geçirilecek. Varsa `DllMain` döndürür `FALSE` işlemden ekleme, hata, sinyal `_DllMainCRTStartup` çağrıları `DllMain` yeniden ve geçirir `DLL_PROCESS_DETACH` olarak *neden* bağımsız değişken, daha sonra rest üzerinden gider sonlandırma işlemi.

Varsayılan giriş noktası olan Visual C++ ' ta DLL'ler oluştururken `_DllMainCRTStartup` tarafından sağlanan VCRuntime bağlı olarak otomatik olarak. Kullanarak DLL dosyanız için bir giriş noktası işlevi belirtmek gerekmez [/Entry (giriş noktası simgesi)](reference/entry-entry-point-symbol.md) bağlayıcı seçeneği.

> [!NOTE]
> / Entry kullanarak DLL için başka bir giriş noktası işlevi belirlemek mümkün olmakla birlikte: bağlayıcı seçeneği değil öneririz, giriş noktası işlevinizi her şeyi çoğaltmak yeterli olacağından, `_DllMainCRTStartup` , aynı sırada yapar. VCRuntime davranışını yinelenen olanak tanıyan işlevler sağlar. Örneğin, çağırabilirsiniz [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) hemen desteklemek için üzerinde bir sürece iliştirilip [/GS (arabellek güvenlik denetimi)](reference/gs-buffer-security-check.md) denetleme seçeneği arabellek. Çağırabilirsiniz `_CRT_INIT` işlevi, kalan DLL başlatma veya sonlandırma işlevleri gerçekleştirmek için giriş noktası işlevi aynı parametre geçirme.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL'yi Başlat

DLL'niz DLL dosyanız yüklendiğinde yürütülmesi gereken başlatma kodu olabilir. Kendi DLL başlatma ve sonlandırma işlevleri gerçekleştirmek, sırayla `_DllMainCRTStartup` çağrılan işlev çağıran `DllMain` sağlayan. `DllMain` DLL giriş noktası için gerekli imzaya sahip olmalıdır. Varsayılan giriş noktası işlevini `_DllMainCRTStartup` çağrıları `DllMain` Windows tarafından geçirilen aynı parametreleri kullanarak. Siz belirtmezseniz varsayılan olarak bir `DllMain` işlevi, Visual C++ sizin için bir tane sağlar ve içinde bağlar böylece `_DllMainCRTStartup` çağırmak için bir şey her zaman vardır. Bu DLL dosyanızı başlatmanız gerekmiyorsa, DLL dosyanızı oluştururken yapmanız gereken özel bir şey anlamına gelir.

İçin kullanılan imzayı budur `DllMain`:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Bazı kitaplıklar kaydırma `DllMain` işlevi sizin için. Örneğin, normal bir MFC DLL uygulamak `CWinApp` nesnenin `InitInstance` ve `ExitInstance` başlatma ve sonlandırma, DLL tarafından gerekli gerçekleştirmek için üye işlevleri. Daha fazla ayrıntı için [Normal MFC DLL'leri Başlat](#initializing-regular-dlls) bölümü.

> [!WARNING]
> Güvenli bir şekilde bir DLL giriş noktası yapabilecekleriniz hakkında önemli sınırlamaları vardır. Bkz: [genel en iyi yöntemler](/windows/desktop/Dlls/dynamic-link-library-best-practices) çağırmak güvenli olmayan belirli Windows API'leri için `DllMain`. Ardından basit başlatma dışında hiçbir şeyde bir başlangıç işlevinde DLL için bunu varsa. Uygulamaları başlatma işlevinden sonra çağrılacak gerektirebilir `DllMain` sahip çalıştırma ve bunlar önce tüm diğer işlevleri çağırma DLL'de.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>(MFC olmayan) Normal DLL'leri Başlat

VCRuntime tarafından sağlanan kullanma (MFC olmayan) normal DLL'lerde kendi başlatma gerçekleştirmek için `_DllMainCRTStartup` giriş noktası, DLL kaynak kodunuzu çağrılan bir işlev içermelidir `DllMain`. Aşağıdaki kod tanımının gösteren temel bir çatı sunar `DllMain` aşağıdaki gibi görünmelidir:

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
> Eski Windows SDK Belgeleri DLL giriş noktası işlevini gerçek adını üzerinde bağlayıcı/Entry seçeneği ile komut satırı belirtilmelidir diyor. Visual C++ ile giriş noktası işlevinizin adı ise/Entry seçeneği kullanmanız gerekmez `DllMain`. Aslında, adı ve/Entry seçeneği kullanırsanız, giriş noktası işlevini bir şey dışında `DllMain`, aynı başlatma çağrıları, giriş noktası işlevi yapmadığı sürece CRT düzgün başlatılmadı `_DllMainCRTStartup` yapar.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Normal MFC DLL'leri Başlat

Normal MFC DLL'leri olduğundan bir `CWinApp` nesnesinde gerçekleştirdikleri başlatma ve sonlandırma görevlerinin bir MFC uygulaması ile aynı konumda: içinde `InitInstance` ve `ExitInstance` üye işlevleri DLL'nin `CWinApp`-türetilmiş sınıf. MFC sağladığından bir `DllMain` tarafından çağrılan işlevi `_DllMainCRTStartup` için `DLL_PROCESS_ATTACH` ve `DLL_PROCESS_DETACH`, kendi yazdığınız değil `DllMain` işlevi. MFC tarafından sağlanan `DllMain` işlev çağrılarında `InitInstance` ne zaman DLL'niz yüklenir ve çağrı yaptığı `ExitInstance` DLL kaldırılmadan önce.

Normal MFC DLL'SİNİN birden çok iş parçacığı çağırarak takip edebilirsiniz [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc) ve [TlsGetValue](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) içinde kendi `InitInstance` işlevi. Bu işlevler, iş parçacığına özgü verileri izlemek DLL'ye izin verme.

İçinde bir MFC OLE, MFC veritabanı (veya DAO) kullandığınız ya da MFC yuva desteği, sırasıyla, hata ayıklama MFC uzantısı DLL'leri MFCO MFC'ye, Normal MFC DLL'SİNİN*sürüm*D.dll, MFCD*sürüm*D.dll ve MFCN*sürüm*D.dll (burada *sürüm* sürüm numarasıdır) otomatik olarak bağlanır. Her biri, Normal MFC DLL içinde kullanıyorsanız bu DLL'ler için aşağıdaki önceden tanımlanmış başlatma işlevlerden birini çağırmalıdır `CWinApp::InitInstance`.

|MFC desteği türü|Çağrılacak başlatma işlevi|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*sürüm*D.dll)|`AfxOleInitModule`|
|MFC veritabanı (MFCD*sürüm*D.dll)|`AfxDbInitModule`|
|MFC yuva (MFCN*sürüm*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC uzantı DLL'leri başlatma

MFC uzantısı DLL'leri olmadığı için bir `CWinApp`-türetilmiş nesnesi (Normal MFC DLL'leri olduğu gibi), başlatma ve sonlandırma kodu buraya eklemelisiniz `DllMain` MFC DLL Sihirbazı oluşturan işlevi.

Sihirbaz aşağıdaki kodu, MFC uzantı DLL'leri sağlar. Kodda, `PROJNAME` projenizin adı için bir yer tutucudur.

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

Yeni bir oluşturma `CDynLinkLibrary` nesnesini başlatma sırasında sağlar, MFC uzantısı DLL dışarı aktarmak için `CRuntimeClass` nesneleri veya istemci uygulamasına kaynakları.

MFC uzantısı DLL dosyasından bir veya daha fazla Normal MFC DLL'leri kullanacaksanız, oluşturan bir başlatma işlev dışarı bir `CDynLinkLibrary` nesne. Bu işlev her MFC uzantısı DLL kullanan Normal MFC DLL'leri çağrılmalıdır. Bu başlatma işlevi çağırmak için uygun bir yere bulunduğu `InitInstance` Normal MFC DLL üye işlevinin `CWinApp`-nesne MFC uzantısı DLL dışarı aktarılan sınıflar veya İşlevler kullanmadan önce türetilmiş.

İçinde `DllMain` MFC DLL Sihirbazı'nın ürettiği çağrısı `AfxInitExtensionModule` modülünün çalışma zamanı sınıflar yakalar (`CRuntimeClass` yapıları), nesne fabrikaları yanı sıra (`COleObjectFactory` nesneleri) için kullanmak `CDynLinkLibrary` nesnesi oluşturulur. Dönüş değerini denetlemeniz gerekir `AfxInitExtensionModule`; sıfır değeri döndürdüyse `AfxInitExtensionModule`, sıfırdan döndürür, `DllMain` işlevi.

MFC uzantısı DLL için bir yürütülebilir açıkça bağlanacaksa (yürütülebilir çağrıları anlamı `AfxLoadLibrary` DLL'ye bağlandığı için), bir çağrı eklemeniz gerekir `AfxTermExtensionModule` üzerinde `DLL_PROCESS_DETACH`. Her işlem MFC uzantısı DLL ayırdığında MFC uzantısı DLL temizlemek MFC'nin bu işlevi sağlar (işlem çıktığında veya DLL sonucu olarak kaldırıldığında gerçekleşir bir `AfxFreeLibrary` arayın). MFC uzantısı DLL dolaylı çağrı uygulama bağlanacaksa `AfxTermExtensionModule` gerekli değildir.

MFC uzantı DLL'leri bağlantı açıkça çağırmalıdır uygulamaları `AfxTermExtensionModule` DLL'i. Ayrıca kullanması gereken `AfxLoadLibrary` ve `AfxFreeLibrary` (Win32 işlevlerini yerine `LoadLibrary` ve `FreeLibrary`) uygulama birden çok iş parçacığı kullanıyorsa. Kullanarak `AfxLoadLibrary` ve `AfxFreeLibrary` MFC uzantısı DLL yüklendiğinde ve kaldırıldığında genel MFC durumunun bozulmasına neden değil, yürütülen başlatma ve kapatma kod sağlar.

MFCx0.dll zaman tam olarak başlatılmış olduğundan `DllMain` olan çağrılır, bellek ve içinde MFC işlevleri çağırma `DllMain` (aksine, MFC 16-bit sürümü).

Uzantı DLL'leri halletmeniz işleme çoklu iş parçacığı `DLL_THREAD_ATTACH` ve `DLL_THREAD_DETACH` içinde durumlarda `DllMain` işlevi. Bu gibi durumlarda geçirilen `DllMain` zaman iş parçacığı ekleme ve DLL'den. Çağırma [TlsAlloc](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-tlsalloc) ne zaman bir DLL iliştiriyor iş parçacığı yerel depolama (TLS) dizinler için DLL bağlı her iş parçacığı için korumak DLL sağlar.

Üst bilgi dosyası yapı tanımları tanımı gibi MFC uzantısı DLL'leri içinde kullanılan yapılar için özel tanımları içerir Not `AFX_EXTENSION_MODULE` ve `CDynLinkLibrary`. MFC uzantısı DLL Bu başlık dosyasının içermelidir.

> [!NOTE]
>  Size tanımlama ne herhangi birini Kaldır, önemlidir `_AFX_NO_XXX` Stdafx.h makrolarındaki. Bu makrolar, yalnızca belirli hedef platform veya bu özelliği destekleyen olup olmadığını denetleme amacıyla mevcut. Bu makrolar denetlemek için programınızı yazabilirsiniz (örneğin, `#ifndef _AFX_NO_OLE_SUPPORT`), ancak programınızın hiçbir zaman tanımlayın veya bu makroların tanımlarını Kaldır.

Çoklu iş parçacığı kullanımı tanıtıcıları dahil bir örnek başlatma işlevi [kullanarak iş parçacığı yerel depolama dinamik bağlantı kitaplığı](/windows/desktop/Dlls/using-thread-local-storage-in-a-dynamic-link-library) Windows SDK. Örnek adlı bir giriş noktası işlevi içeren Not `LibMain`, ancak bu işlev adlandırmalısınız. `DllMain` böylece MFC ve C çalışma zamanı kitaplıkları ile çalışır.

## <a name="see-also"></a>Ayrıca bkz.

[Visual C++'ta DLL'ler](dlls-in-visual-cpp.md)<br/>
[DllMain giriş noktası](/windows/desktop/Dlls/dllmain)<br/>
[Dinamik bağlantı kitaplığı en iyi uygulamalar](/windows/desktop/Dlls/dynamic-link-library-best-practices)
