---
title: DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı
ms.date: 08/19/2019
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
ms.openlocfilehash: 2f2ffb13e6a80b144298bbf8cd76b5666a10b4dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81335658"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı

Visual Studio kullanarak bir dinamik bağlantı kitaplığı (DLL) oluşturduğunuzda, varsayılan olarak bağlayıcı Visual C++ çalışma zamanı kitaplığı (VCRuntime) içerir. VCRuntime bir C/C++ yürütülebilirini başlatmak ve sonlandırmak için gereken kodu içerir. Bir DLL 'ye bağlandığında, VCRuntime kodu, bir işlem veya iş parçacığına iliştirilecek veya bu bilgisayardan ayrımak üzere DLL 'ye Windows işletim sistemi iletilerini işleyen adlı `_DllMainCRTStartup` BIR iç DLL giriş noktası işlevi sağlar. `_DllMainCRTStartup` İşlevi yığın arabelleği güvenlik kurulumu, C çalışma zamanı KITAPLıĞı (CRT) başlatma ve sonlandırma ve statik ve genel nesneler için oluşturucular ve Yıkıcılar çağrıları gibi önemli görevleri gerçekleştirir. `_DllMainCRTStartup`Ayrıca kendi başlatma ve sonlandırma işlemleri gerçekleştirmek için WinRT, MFC ve ATL gibi diğer kitaplıklar için de kanca işlevleri çağırır. Bu başlatma olmadan, CRT ve diğer kitaplıklar, statik değişkenleriniz de başlatılmamış bir durumda bırakılır. Aynı VCRuntime iç başlatma ve sonlandırma yordamları, DLL 'nizin statik olarak bağlı bir CRT veya dinamik olarak bağlı bir CRT DLL kullanıp kullanmamasından bağımsız olarak adlandırılır.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>Varsayılan DLL giriş noktası _DllMainCRTStartup

Windows 'da, tüm dll 'Ler genellikle `DllMain`başlatma ve sonlandırma için çağrılan isteğe bağlı bir giriş noktası işlevi içerebilir. Bu, gerektiğinde ek kaynaklar ayırma veya serbest bırakma fırsatı sağlar. Windows, giriş noktası işlevini dört durumda çağırır: işlem iliştirme, işlem ayırma, iş parçacığı iliştirme ve iş parçacığı ayırma. Bir DLL bir işlem adres alanına yüklendiğinde, onu kullanan bir uygulama yüklendiğinde ya da uygulama çalışma zamanında DLL istediğinde, işletim sistemi DLL verilerinin ayrı bir kopyasını oluşturur. Buna *işlem iliştirme*denir. *Iş parçacığı iliştirme* , dll 'nin yüklendiği işlem yeni bir iş parçacığı oluşturduğunda oluşur. İş parçacığı *ayırma* , iş parçacığı sonlandırıldığında oluşur ve *işlem ayırma* dll artık gerekli olmadığında ve bir uygulama tarafından serbest bırakıldığında gerçekleşir. İşletim sistemi, her olay türü için bir *neden* bağımsız değişkeni geçirerek, bu olayların her bırı için DLL giriş noktasına ayrı bir çağrı yapar. Örneğin, işletim sistemi, işlem `DLL_PROCESS_ATTACH` eklemeyi bildirmek için *neden* bağımsız değişkeni olarak gönderir.

VCRuntime kitaplığı, varsayılan başlatma ve sonlandırma işlemlerini işlemek için `_DllMainCRTStartup` çağrılan bir giriş noktası işlevi sağlar. İşlem iliştirme üzerinde, `_DllMainCRTStartup` işlev arabellek güvenliği denetimleri AYARLıYOR, CRT ve diğer kitaplıkları başlatır, çalışma zamanı türü bilgilerini başlatır, statik ve yerel olmayan veriler için Oluşturucu başlatır ve çağırır, iş parçacığı yerel depolamayı başlatır, her iliştirme için bir iç statik sayacı artırır ve ardından bir kullanıcı veya kitaplığı çağırır. `DllMain` İşlem ayırma sırasında, işlev bu adımları tersine geçer. Çağrı `DllMain`, iç sayacı azaltır, yıkıcıları ÇAĞıRıR, CRT sonlandırma işlevlerini ve kayıtlı `atexit` işlevleri çağırır ve diğer sonlandırma kitaplıklarına bildirir. Ek sayacı sıfıra gittiğinde, işlevi `FALSE` WINDOWS 'un dll 'nin kaldırılabiliyor olduğunu gösterir. İşlev `_DllMainCRTStartup` , iş parçacığı iliştirme ve iş parçacığı ayırma sırasında da çağrılır. Bu durumlarda, VCRuntime kodu hiç ek başlatma veya sonlandırma yapmaz ve yalnızca iletiyi anında geçirmek için çağırır `DllMain` . İşlem `DllMain` iliştirme `FALSE` 'den döndürürse, sinyal hatası, `_DllMainCRTStartup` yeniden çağırır `DllMain` ve *neden* bağımsız `DLL_PROCESS_DETACH` değişkeni olarak geçerse, sonlandırma sürecinin geri kalanı üzerinden ilerler.

Visual Studio 'da dll 'Ler oluştururken, VCRuntime tarafından sağlanan `_DllMainCRTStartup` varsayılan giriş noktası otomatik olarak bağlanır. [/Entry (giriş noktası simgesi)](reference/entry-entry-point-symbol.md) bağlayıcı SEÇENEĞINI kullanarak dll 'niz için bir giriş noktası işlevi belirtmeniz gerekmez.

> [!NOTE]
> /ENTRY: bağlayıcı seçeneğini kullanarak bir DLL için başka bir giriş noktası işlevi belirtmek mümkün olsa da, giriş noktası işlevinizin her şeyi `_DllMainCRTStartup` aynı sırada yinelemeyeceğinden, bunu önermiyoruz. VCRuntime, davranışını çoğalttığınızda size izin veren işlevler sağlar. Örneğin, [/GS (arabellek güvenlik denetimi)](reference/gs-buffer-security-check.md) arabellek denetimi seçeneğini desteklemek için işlem iliştirme üzerinde hemen [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) çağırabilirsiniz. DLL başlatma veya sonlandırma `_CRT_INIT` işlevlerinin geri kalanını gerçekleştirmek için, giriş noktası işleviyle aynı parametreleri geçirerek işlevi çağırabilirsiniz.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL 'yi başlatma

Dll 'niz, DLL 'niz yüklenirken yürütülmesi gereken başlatma koduna sahip olabilir. Kendi DLL başlatma ve sonlandırma işlevlerinizi gerçekleştirebilmeniz için, `_DllMainCRTStartup` sağlayabilmeniz için adlı `DllMain` bir işlev çağırır. DLL `DllMain` giriş noktası için gerekli imzaya sahip olmanız gerekir. Varsayılan giriş noktası işlevi `_DllMainCRTStartup` , Windows `DllMain` tarafından geçirilen parametreleri kullanarak çağırır. Varsayılan olarak, bir `DllMain` işlev sağlamazsanız, Visual Studio sizin için bir tane sağlar ve her zaman çağrılabilecek `_DllMainCRTStartup` bir şey olması için öğesine bağlanır. Bu, DLL 'nizi başlatmanıza gerek kalmadığında, DLL 'nizi oluştururken yapmanız gereken özel bir şey olmadığı anlamına gelir.

Bu imza şu şekilde kullanılır `DllMain`:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Bazı kitaplıklar `DllMain` işlevi sizin için sarmalıdır. Örneğin, normal bir MFC DLL 'de, DLL 'niz için `CWinApp` gereken başlatma `InitInstance` ve `ExitInstance` sonlandırma gerçekleştirmek üzere nesnenin ve üye işlevlerini uygulayın. Daha ayrıntılı bilgi için bkz. [normal MFC DLL 'Leri başlatma](#initializing-regular-dlls) bölümü.

> [!WARNING]
> Bir DLL giriş noktasında güvenle yapabilecekleriniz için önemli sınırlamalar vardır. ' `DllMain`İ çağırmak güvenli olmayan belirli Windows API 'Leri Için [Genel en iyi uygulamalar](/windows/win32/Dlls/dynamic-link-library-best-practices) bölümüne bakın. En basit başlatma için bir işlem yapmanız gerekiyorsa, bunu DLL için başlatma işlevinde yapın. Çalıştırıldıktan sonra `DllMain` ve DLL 'deki diğer işlevleri çağırmadan önce, uygulamaların başlatma işlevini çağırmasını zorunlu kılabilirsiniz.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>Sıradan (MFC olmayan) dll 'Leri başlatma

VCRuntime tarafından sağlanan `_DllMainCRTStartup` giriş noktasını kullanan sıradan (MFC olmayan) dll 'lerde kendi başlatma işlemini GERÇEKLEŞTIRMEK için DLL kaynak kodunuzun adlı `DllMain`bir işlev içermesi gerekir. Aşağıdaki kod, tanımının ne gibi `DllMain` görünebileceğini gösteren temel bir iskelet sunar:

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
> Daha eski Windows SDK belgeler, DLL giriş noktası işlevinin gerçek adının,/ENTRY seçeneğiyle bağlayıcı komut satırında belirtilmesi gerektiğini belirtir. Visual Studio ile, giriş noktası işlevinizin adı ise `DllMain`/entry seçeneğini kullanmanıza gerek kalmaz. Aslında,/ENTRY seçeneğini kullanırsanız ve giriş noktası işlevinizi dışında `DllMain`bir şey olarak adlandırırsanız, giriş noktası işleviniz `_DllMainCRTStartup` yaptığı başlatma çağrılarını yaptığı müddetçe CRT düzgün başlatılmaz.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Normal MFC DLL 'Leri başlatma

Normal MFC DLL 'Leri `CWinApp` bir nesne içerdiğinden, bir MFC uygulamasıyla aynı konumda başlatma ve sonlandırma görevlerini GERÇEKLEŞTIRMELIDIR: DLL 'nin `InitInstance` `ExitInstance` `CWinApp`türetilmiş sınıfının ve üye işlevlerinde. `DllMain` MFC ve `_DllMainCRTStartup` `DLL_PROCESS_DETACH` `DllMain` için `DLL_PROCESS_ATTACH` tarafından çağrılan bir işlev sağladığından, kendi işlevinizi yazmamalıdır. MFC tarafından sunulan `DllMain` işlev dll 'niz `InitInstance` yüklendiğinde çağırır ve DLL kaldırılmadan önce çağrılır `ExitInstance` .

Normal bir MFC DLL 'SI, `InitInstance` Işlevine [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) ve [TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) çağırarak birden çok iş parçacığını izleyebilir. Bu işlevler, DLL 'nin iş parçacığına özgü verileri izlemesini sağlar.

MFC 'ye dinamik olarak bağlanan normal MFC DLL 'inizde MFC OLE, MFC veritabanı (veya DAO) veya MFC Yuvaları desteği kullanıyorsanız, hata ayıkla MFC uzantı dll 'Leri MFCO*Sürüm*d. dll, mfcd*Sürüm*d. dll ve mfcn*Sürüm*d. dll *(sürüm numarası* sürümü) otomatik olarak bağlanır. Normal MFC DLL 'leriniz içinde kullandığınız her dll için aşağıdaki önceden tanımlanmış başlatma işlevlerinden birini çağırmanız gerekir `CWinApp::InitInstance`.

|MFC desteğinin türü|Çağırmak için başlatma işlevi|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*sürümü*D. dll)|`AfxOleInitModule`|
|MFC veritabanı (MFCD*Sürüm*D. dll)|`AfxDbInitModule`|
|MFC Yuvaları (MFCN*Sürüm*D. dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC uzantı dll 'Lerini Başlat

MFC uzantı dll 'Leri türetilmiş bir `CWinApp`nesneye sahip olmadığından (normal MFC DLL 'leri gibi), başlatma ve sonlandırma kodunuzu MFC DLL Sihirbazının oluşturduğu `DllMain` işleve eklemeniz gerekir.

Sihirbaz MFC uzantı dll 'Leri için aşağıdaki kodu sağlar. Kodda, `PROJNAME` projenizin adı için bir yer tutucudur.

```cpp
#include "pch.h" // For Visual Studio 2017 and earlier, use "stdafx.h"
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

Başlatma sırasında yeni `CDynLinkLibrary` bir nesne oluşturmak, MFC uzantı dll 'inin nesneleri veya `CRuntimeClass` kaynakları istemci uygulamasına dışarı aktarmaya izin verir.

MFC uzantı DLL 'nizi bir veya daha fazla normal MFC DLL 'lerden kullanacaksanız, `CDynLinkLibrary` nesne oluşturan bir başlatma işlevini dışarı aktarmanız gerekir. Bu işlev, MFC uzantı DLL 'sini kullanan normal MFC DLL 'Lerinin her birinden çağrılmalıdır. Bu başlatma işlevini çağırmak için uygun bir yer, MFC uzantı `InitInstance` dll 'inin ya da işlevlerinin hiçbirini kullanmadan önce `CWinApp`normal MFC DLL 'nin türetilmiş nesnesinin üye işlevleridir.

MFC DLL `DllMain` Sihirbazı 'nın ürettiği bir çağrı, modülün çalışma zamanı sınıflarını `AfxInitExtensionModule` (`CRuntimeClass` yapılar) ve`COleObjectFactory` `CDynLinkLibrary` nesne oluşturulduğunda kullanılmak üzere nesne fabrikalarını (nesneleri) yakalar. Dönüş değerini denetlemeniz gerekir `AfxInitExtensionModule`; öğesinden `AfxInitExtensionModule`sıfır değeri döndürülürse, işlevinizden `DllMain` sıfır döndürün.

MFC uzantı DLL 'niz bir yürütülebilir dosya ile açıkça bağlantılandırılır (DLL 'ye bağlantı yapılacak yürütülebilir `AfxLoadLibrary` çağrılar anlamına gelir), `AfxTermExtensionModule` üzerine `DLL_PROCESS_DETACH`bir çağrısı eklemeniz gerekir. Bu işlev, MFC 'nin her bir işlem MFC uzantısı DLL 'sinden ayrıldığında (işlem çıktığında veya bir `AfxFreeLibrary` çağrı sonucu olarak DLL kaldırıldığında gerçekleşir) MFC uzantı dll 'sini temizleyesağlar. MFC uzantı DLL 'niz uygulamaya örtük olarak bağlanırsa, çağrısı `AfxTermExtensionModule` gerekli değildir.

MFC uzantısı DLL 'Leri açıkça bağlayan uygulamaların DLL boşaltılırken `AfxTermExtensionModule` çağrılması gerekir. Uygulamanın birden çok iş `AfxLoadLibrary` parçacığı `AfxFreeLibrary` kullanması durumunda ve (Win32 işlevleri `LoadLibrary` yerine `FreeLibrary`) ve de kullanmaları gerekir. Kullanarak `AfxLoadLibrary` , `AfxFreeLibrary` MFC uzantı dll 'si yüklendiğinde ve kaldırıldığında çalıştırılan başlatma ve başlatma kodunun genel MFC durumunu bozmamasını sağlar.

MFCx0. dll, zaman `DllMain` tarafından tam olarak başlatıldığından, bellek AYıRABILIR ve MFC işlevlerini IÇINDE `DllMain` (MFC 'nin 16 bit sürümünden farklı olarak) çağırabilirsiniz.

Uzantı dll 'Leri, `DLL_THREAD_ATTACH` `DLL_THREAD_DETACH` `DllMain` işlevindeki ve durumlarını işleyerek çoklu iş parçacıklı işlem yapabilir. Bu durumlar, iş parçacıkları `DllMain` dll 'ye iliştirildiğinde ve bu sunucudan ayrıldığınızda ' a geçirilir. Bir DLL eklendiğinde [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) çağrısı, DLL 'nin dll 'ye bağlı her iş parçacığı için iş parçacığı yerel depolama (TLS) dizinlerini korumasına olanak tanır.

Afxdllx. h üstbilgi dosyasının, ve `AFX_EXTENSION_MODULE` `CDynLinkLibrary`için tanımı gibi MFC uzantı dll 'lerinde kullanılan yapılar için özel tanımlar içerdiğini unutmayın. Bu üstbilgi dosyasını MFC uzantı DLL 'nize dahil etmelisiniz.

> [!NOTE]
> `_AFX_NO_XXX` *Pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) içindeki hiçbir makroyu tanımlamanız veya tanımlamadığınız önemlidir. Bu makrolar yalnızca belirli bir hedef platformun bu özelliği destekleyip desteklemediğini denetleme amacıyla mevcuttur. Bu makroları denetlemek için programınızı yazabilirsiniz (örneğin, `#ifndef _AFX_NO_OLE_SUPPORT`), ancak programınız bu makroları asla tanımlamaz veya tanımlamaz.

Çoklu iş parçacığını işleyen örnek bir başlatma işlevi, Windows SDK [dinamik bağlantı kitaplığında Iş parçacığı yerel depolama alanı kullanımına](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) dahildir. Örnek adlı `LibMain`bir giriş noktası işlevi içerdiğini, ancak MFC ve C çalışma zamanı kitaplıklarıyla çalışacak şekilde bu `DllMain` işlevi adlandırmalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)<br/>
[DllMain giriş noktası](/windows/win32/Dlls/dllmain)<br/>
[Dinamik bağlantı kitaplığı En Iyi uygulamaları](/windows/win32/Dlls/dynamic-link-library-best-practices)
