---
description: "Daha fazla bilgi edinin: DLL 'Ler ve Visual C++ çalışma zamanı kitaplığı davranışı"
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
ms.openlocfilehash: 5b76ec562b87969350b49d38e24c33ce7a4fabf8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275457"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>DLL’ler ve Visual C++ çalışma zamanı kitaplığı davranışı

Visual Studio kullanarak bir dinamik bağlantı kitaplığı (DLL) oluşturduğunuzda, varsayılan olarak bağlayıcı Visual C++ çalışma zamanı kitaplığı (VCRuntime) içerir. VCRuntime bir C/C++ yürütülebilirini başlatmak ve sonlandırmak için gereken kodu içerir. Bir DLL 'ye bağlandığında, VCRuntime kodu, `_DllMainCRTStartup` bir işlem veya iş parçacığına iliştirilecek veya bu bilgisayardan ayrımak üzere dll 'ye Windows işletim sistemi iletilerini işleyen adlı bir Iç DLL giriş noktası işlevi sağlar. `_DllMainCRTStartup`İşlevi yığın arabelleği güvenlik kurulumu, C çalışma zamanı kitaplığı (CRT) başlatma ve sonlandırma ve statik ve genel nesneler için oluşturucular ve Yıkıcılar çağrıları gibi önemli görevleri gerçekleştirir. `_DllMainCRTStartup` Ayrıca kendi başlatma ve sonlandırma işlemleri gerçekleştirmek için WinRT, MFC ve ATL gibi diğer kitaplıklar için de kanca işlevleri çağırır. Bu başlatma olmadan, CRT ve diğer kitaplıklar, statik değişkenleriniz de başlatılmamış bir durumda bırakılır. Aynı VCRuntime iç başlatma ve sonlandırma yordamları, DLL 'nizin statik olarak bağlı bir CRT veya dinamik olarak bağlı bir CRT DLL kullanıp kullanmamasından bağımsız olarak adlandırılır.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>Varsayılan DLL giriş noktası _DllMainCRTStartup

Windows 'da, tüm dll 'Ler genellikle `DllMain` başlatma ve sonlandırma için çağrılan isteğe bağlı bir giriş noktası işlevi içerebilir. Bu, gerektiğinde ek kaynaklar ayırma veya serbest bırakma fırsatı sağlar. Windows, giriş noktası işlevini dört durumda çağırır: işlem iliştirme, işlem ayırma, iş parçacığı iliştirme ve iş parçacığı ayırma. Bir DLL bir işlem adres alanına yüklendiğinde, onu kullanan bir uygulama yüklendiğinde ya da uygulama çalışma zamanında DLL istediğinde, işletim sistemi DLL verilerinin ayrı bir kopyasını oluşturur. Buna *işlem iliştirme* denir. *Iş parçacığı iliştirme* , dll 'nin yüklendiği işlem yeni bir iş parçacığı oluşturduğunda oluşur. İş parçacığı *ayırma* , iş parçacığı sonlandırıldığında oluşur ve *işlem ayırma* dll artık gerekli olmadığında ve bir uygulama tarafından serbest bırakıldığında gerçekleşir. İşletim sistemi, her olay türü için bir *neden* bağımsız değişkeni geçirerek, bu olayların her bırı için DLL giriş noktasına ayrı bir çağrı yapar. Örneğin, işletim sistemi, `DLL_PROCESS_ATTACH` işlem eklemeyi bildirmek için *neden* bağımsız değişkeni olarak gönderir.

VCRuntime kitaplığı, `_DllMainCRTStartup` varsayılan başlatma ve sonlandırma işlemlerini işlemek için çağrılan bir giriş noktası işlevi sağlar. İşlem iliştirme üzerinde, `_DllMainCRTStartup` işlev arabellek güvenliği denetimleri ayarlıyor, CRT ve diğer kitaplıkları başlatır, çalışma zamanı türü bilgilerini başlatır, statik ve yerel olmayan veriler için Oluşturucu başlatır ve çağırır, iş parçacığı yerel depolamayı başlatır, her iliştirme için bir iç statik sayacı artırır ve ardından bir kullanıcı veya kitaplığı çağırır `DllMain` . İşlem ayırma sırasında, işlev bu adımları tersine geçer. Çağrı `DllMain` , iç sayacı azaltır, yıkıcıları çağırır, CRT sonlandırma işlevlerini ve kayıtlı `atexit` işlevleri çağırır ve diğer sonlandırma kitaplıklarına bildirir. Ek sayacı sıfıra gittiğinde, işlevi `FALSE` Windows 'un dll 'nin kaldırılabiliyor olduğunu gösterir. `_DllMainCRTStartup`İşlev, iş parçacığı iliştirme ve iş parçacığı ayırma sırasında da çağrılır. Bu durumlarda, VCRuntime kodu hiç ek başlatma veya sonlandırma yapmaz ve yalnızca `DllMain` iletiyi anında geçirmek için çağırır. `DllMain` `FALSE` İşlem iliştirme 'den döndürürse, sinyal hatası, `_DllMainCRTStartup` yeniden çağırır `DllMain` ve `DLL_PROCESS_DETACH` *neden* bağımsız değişkeni olarak geçerse, sonlandırma sürecinin geri kalanı üzerinden ilerler.

Visual Studio 'da dll 'Ler oluştururken,  `_DllMainCRTStartup` VCRuntime tarafından sağlanan varsayılan giriş noktası otomatik olarak bağlanır. [/Entry (giriş noktası simgesi)](reference/entry-entry-point-symbol.md) bağlayıcı SEÇENEĞINI kullanarak dll 'niz için bir giriş noktası işlevi belirtmeniz gerekmez.

> [!NOTE]
> /ENTRY: bağlayıcı seçeneğini kullanarak bir DLL için başka bir giriş noktası işlevi belirtmek mümkün olsa da, giriş noktası işlevinizin her şeyi aynı sırada yinelemeyeceğinden, bunu önermiyoruz `_DllMainCRTStartup` . VCRuntime, davranışını çoğalttığınızda size izin veren işlevler sağlar. Örneğin, [/GS (arabellek güvenlik denetimi)](reference/gs-buffer-security-check.md) arabellek denetimi seçeneğini desteklemek için işlem iliştirme üzerinde hemen [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) çağırabilirsiniz. `_CRT_INIT`DLL başlatma veya sonlandırma işlevlerinin geri kalanını gerçekleştirmek için, giriş noktası işleviyle aynı parametreleri geçirerek işlevi çağırabilirsiniz.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL 'yi başlatma

Dll 'niz, DLL 'niz yüklenirken yürütülmesi gereken başlatma koduna sahip olabilir. Kendi DLL başlatma ve sonlandırma işlevlerinizi gerçekleştirebilmeniz için, `_DllMainCRTStartup` sağlayabilmeniz için adlı bir işlev çağırır `DllMain` . `DllMain`DLL giriş noktası için gerekli imzaya sahip olmanız gerekir. Varsayılan giriş noktası işlevi, `_DllMainCRTStartup` `DllMain` Windows tarafından geçirilen parametreleri kullanarak çağırır. Varsayılan olarak, bir `DllMain` işlev sağlamazsanız, Visual Studio sizin için bir tane sağlar ve `_DllMainCRTStartup` her zaman çağrılabilecek bir şey olması için öğesine bağlanır. Bu, DLL 'nizi başlatmanıza gerek kalmadığında, DLL 'nizi oluştururken yapmanız gereken özel bir şey olmadığı anlamına gelir.

Bu imza şu şekilde kullanılır `DllMain` :

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Bazı kitaplıklar `DllMain` işlevi sizin için sarmalıdır. Örneğin, normal bir MFC DLL 'de, `CWinApp` `InitInstance` `ExitInstance` DLL 'niz için gereken başlatma ve sonlandırma gerçekleştirmek üzere nesnenin ve üye işlevlerini uygulayın. Daha ayrıntılı bilgi için bkz. [normal MFC DLL 'Leri başlatma](#initializing-regular-dlls) bölümü.

> [!WARNING]
> Bir DLL giriş noktasında güvenle yapabilecekleriniz için önemli sınırlamalar vardır. ' İ çağırmak güvenli olmayan belirli Windows API 'Leri için [Genel En Iyi uygulamalar](/windows/win32/Dlls/dynamic-link-library-best-practices) bölümüne bakın `DllMain` . En basit başlatma için bir işlem yapmanız gerekiyorsa, bunu DLL için başlatma işlevinde yapın. `DllMain`Çalıştırıldıktan sonra ve DLL 'deki diğer işlevleri çağırmadan önce, uygulamaların başlatma işlevini çağırmasını zorunlu kılabilirsiniz.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>Sıradan (MFC olmayan) dll 'Leri başlatma

VCRuntime tarafından sağlanan giriş noktasını kullanan sıradan (MFC olmayan) dll 'lerde kendi başlatma işlemini gerçekleştirmek için `_DllMainCRTStartup` DLL kaynak kodunuzun adlı bir işlev içermesi gerekir `DllMain` . Aşağıdaki kod, tanımının ne gibi görünebileceğini gösteren temel bir iskelet sunar `DllMain` :

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
> Daha eski Windows SDK belgeler, DLL giriş noktası işlevinin gerçek adının,/ENTRY seçeneğiyle bağlayıcı komut satırında belirtilmesi gerektiğini belirtir. Visual Studio ile, giriş noktası işlevinizin adı ise/ENTRY seçeneğini kullanmanıza gerek kalmaz `DllMain` . Aslında,/ENTRY seçeneğini kullanırsanız ve giriş noktası işlevinizi dışında bir şey `DllMain` olarak adlandırırsanız, giriş noktası işleviniz yaptığı başlatma çağrılarını yaptığı müddetçe CRT düzgün başlatılmaz `_DllMainCRTStartup` .

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Normal MFC DLL 'Leri başlatma

Normal MFC DLL 'Leri bir `CWinApp` nesne içerdiğinden, BIR MFC uygulamasıyla aynı konumda başlatma ve sonlandırma görevlerini gerçekleştirmelidir: `InitInstance` `ExitInstance` DLL 'nin türetilmiş sınıfının ve üye işlevlerinde `CWinApp` . MFC `DllMain` ve için tarafından çağrılan bir işlev sağladığından `_DllMainCRTStartup` `DLL_PROCESS_ATTACH` `DLL_PROCESS_DETACH` , kendi `DllMain` işlevinizi yazmamalıdır. MFC tarafından sunulan `DllMain` Işlev `InitInstance` DLL 'niz yüklendiğinde ÇAĞıRıR ve `ExitInstance` DLL kaldırılmadan önce çağrılır.

Normal bir MFC DLL 'SI, işlevine [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) ve [TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) çağırarak birden çok iş parçacığını izleyebilir `InitInstance` . Bu işlevler, DLL 'nin iş parçacığına özgü verileri izlemesini sağlar.

MFC 'ye dinamik olarak bağlanan normal MFC DLL 'inizde MFC OLE, MFC veritabanı (veya DAO) veya MFC Yuvaları desteğini kullanıyorsanız, hata ayıkla MFC uzantı dll 'Leri MFCO *sürümü* D.dll, mfcd *sürümü* D.dll ve *mfcn sürüm* D.dll *(sürüm numarası* sürümü) otomatik olarak bağlanır. Normal MFC DLL 'leriniz içinde kullandığınız her dll için aşağıdaki önceden tanımlanmış başlatma işlevlerinden birini çağırmanız gerekir `CWinApp::InitInstance` .

|MFC desteğinin türü|Çağırmak için başlatma işlevi|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO *sürümü* D.dll)|`AfxOleInitModule`|
|MFC veritabanı (MFCD *sürüm* D.dll)|`AfxDbInitModule`|
|MFC Yuvaları (MFCN *sürüm* D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC uzantı dll 'Lerini Başlat

MFC uzantı dll 'Leri türetilmiş bir nesneye sahip olmadığından `CWinApp` (normal MFC DLL 'leri gibi), başlatma ve sonlandırma kodunuzu `DllMain` MFC DLL Sihirbazının oluşturduğu işleve eklemeniz gerekir.

Sihirbaz MFC uzantı dll 'Leri için aşağıdaki kodu sağlar. Kodda, `PROJNAME` projenizin adı için bir yer tutucudur.

```cpp
#include "pch.h" // For Visual Studio 2017 and earlier, use "stdafx.h"
#include <afxdllx.h>

#ifdef _DEBUG
#define new DEBUG_NEW
#undef THIS_FILE
static char THIS_FILE[] = __FILE__;
#endif
static AFX_EXTENSION_MODULE PROJNAMEDLL;

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

`CDynLinkLibrary`Başlatma sırasında yeni bir nesne oluşturmak, MFC uzantı DLL 'inin `CRuntimeClass` nesneleri veya kaynakları istemci uygulamasına dışarı aktarmaya izin verir.

MFC uzantı DLL 'nizi bir veya daha fazla normal MFC DLL 'lerden kullanacaksanız, nesne oluşturan bir başlatma işlevini dışarı aktarmanız gerekir `CDynLinkLibrary` . Bu işlev, MFC uzantı DLL 'sini kullanan normal MFC DLL 'Lerinin her birinden çağrılmalıdır. Bu başlatma işlevini çağırmak için uygun bir yer, `InitInstance` `CWinApp` MFC uzantı dll 'inin ya da işlevlerinin hiçbirini kullanmadan önce normal MFC DLL 'nin türetilmiş nesnesinin üye işlevleridir.

`DllMain`MFC DLL Sihirbazı 'nın ürettiği bir çağrı, `AfxInitExtensionModule` modülün çalışma zamanı sınıflarını ( `CRuntimeClass` yapılar) ve `COleObjectFactory` nesne oluşturulduğunda kullanılmak üzere nesne fabrikalarını (nesneleri) yakalar `CDynLinkLibrary` . Dönüş değerini denetlemeniz gerekir `AfxInitExtensionModule` ; öğesinden sıfır değer döndürülürse `AfxInitExtensionModule` , `DllMain` işlevinizden sıfır döndürün.

MFC uzantı DLL 'niz bir yürütülebilir dosya ile açıkça bağlantılandırılır ( `AfxLoadLibrary` DLL 'ye bağlantı yapılacak yürütülebilir çağrılar anlamına gelir), üzerine bir çağrısı eklemeniz gerekir `AfxTermExtensionModule` `DLL_PROCESS_DETACH` . Bu işlev, MFC 'nin her bir işlem MFC uzantısı DLL 'sinden ayrıldığında (işlem çıktığında veya bir çağrı sonucu olarak DLL kaldırıldığında gerçekleşir) MFC uzantı DLL 'sini temizleyesağlar `AfxFreeLibrary` . MFC uzantı DLL 'niz uygulamaya örtük olarak bağlanırsa, çağrısı `AfxTermExtensionModule` gerekli değildir.

MFC uzantısı DLL 'Leri açıkça bağlayan uygulamaların `AfxTermExtensionModule` DLL boşaltılırken çağrılması gerekir. `AfxLoadLibrary` `AfxFreeLibrary` `LoadLibrary` `FreeLibrary` Uygulamanın birden çok iş parçacığı kullanması durumunda ve (Win32 işlevleri yerine) ve de kullanmaları gerekir. Kullanarak `AfxLoadLibrary` , `AfxFreeLibrary` MFC uzantı dll 'si yüklendiğinde ve kaldırıldığında çalıştırılan başlatma ve başlatma kodunun genel MFC durumunu bozmamasını sağlar.

MFCx0.dll, çağrıldığı zaman tarafından tam olarak başlatıldığından `DllMain` , bellek ayırabilir ve IÇINDEKI MFC işlevlerini çağırabilirsiniz `DllMain` (16 bitlik MFC sürümünden farklı olarak).

Uzantı dll 'Leri, `DLL_THREAD_ATTACH` işlevindeki ve durumlarını işleyerek çoklu iş parçacıklı işlem yapabilir `DLL_THREAD_DETACH` `DllMain` . Bu durumlar `DllMain` , iş PARÇACıKLARı dll 'ye iliştirildiğinde ve bu sunucudan ayrıldığınızda ' a geçirilir. Bir DLL eklendiğinde [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) çağrısı, DLL 'nin dll 'ye bağlı her iş parçacığı için iş parçacığı yerel depolama (TLS) dizinlerini korumasına olanak tanır.

Afxdllx. h üstbilgi dosyasının, ve için tanımı gibi MFC uzantı dll 'Lerinde kullanılan yapılar için özel tanımlar içerdiğini unutmayın `AFX_EXTENSION_MODULE` `CDynLinkLibrary` . Bu üstbilgi dosyasını MFC uzantı DLL 'nize dahil etmelisiniz.

> [!NOTE]
> `_AFX_NO_XXX` *Pch. h* (Visual Studio 2017 ve önceki sürümlerde *stdadfx. h* ) içindeki hiçbir makroyu tanımlamanız veya tanımlamadığınız önemlidir. Bu makrolar yalnızca belirli bir hedef platformun bu özelliği destekleyip desteklemediğini denetleme amacıyla mevcuttur. Bu makroları denetlemek için programınızı yazabilirsiniz (örneğin, `#ifndef _AFX_NO_OLE_SUPPORT` ), ancak programınız bu makroları asla tanımlamaz veya tanımlamaz.

Çoklu iş parçacığını işleyen örnek bir başlatma işlevi, Windows SDK [bir Dynamic-Link kitaplığında Iş parçacığı yerel depolaması kullanımına](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) dahildir. Örnek adlı bir giriş noktası işlevi içerdiğini `LibMain` , ancak `DllMain` MFC ve C çalışma zamanı kitaplıklarıyla çalışacak şekilde bu işlevi adlandırmalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)<br/>
[DllMain giriş noktası](/windows/win32/Dlls/dllmain)<br/>
[Dinamik bağlantı kitaplığı En Iyi uygulamaları](/windows/win32/Dlls/dynamic-link-library-best-practices)
