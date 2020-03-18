---
title: Dll 'Ler ve C++ görsel çalışma zamanı kitaplığı davranışı
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
ms.openlocfilehash: 572a0ba70c1ba2d46d2d9fd6d8ac543a77bbbc01
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79417315"
---
# <a name="dlls-and-visual-c-run-time-library-behavior"></a>Dll 'Ler ve C++ görsel çalışma zamanı kitaplığı davranışı

Visual Studio kullanarak bir dinamik bağlantı kitaplığı (DLL) oluşturduğunuzda, varsayılan olarak bağlayıcı, görsel C++ çalışma zamanı kitaplığını (vcruntime) içerir. VCRuntime bir C/C++ yürütülebiliri başlatmak ve sonlandırmak için gereken kodu içerir. Bir DLL 'ye bağlandığında, VCRuntime kodu, bir işlem veya iş parçacığına iliştirilecek veya bu bilgisayardan ayrılmak üzere DLL 'ye Windows işletim sistemi iletilerini işleyen `_DllMainCRTStartup` adlı iç DLL giriş noktası işlevini sağlar. `_DllMainCRTStartup` işlevi yığın arabelleği güvenlik kurulumu, C çalışma zamanı kitaplığı (CRT) başlatma ve sonlandırma ve statik ve genel nesneler için oluşturucular ve Yıkıcılar çağrıları gibi önemli görevleri gerçekleştirir. `_DllMainCRTStartup` Ayrıca kendi başlatma ve sonlandırma işlemleri gerçekleştirmek için WinRT, MFC ve ATL gibi diğer kitaplıkların kanca işlevlerini çağırır. Bu başlatma olmadan, CRT ve diğer kitaplıklar, statik değişkenleriniz de başlatılmamış bir durumda bırakılır. Aynı VCRuntime iç başlatma ve sonlandırma yordamları, DLL 'nizin statik olarak bağlı bir CRT veya dinamik olarak bağlı bir CRT DLL kullanıp kullanmamasından bağımsız olarak adlandırılır.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>Varsayılan DLL giriş noktası _DllMainCRTStartup

Windows 'da, tüm dll 'Ler, genellikle başlatma ve sonlandırma için çağrılan `DllMain`olarak adlandırılan isteğe bağlı bir giriş noktası işlevi içerebilir. Bu, gerektiğinde ek kaynaklar ayırma veya serbest bırakma fırsatı sağlar. Windows, giriş noktası işlevini dört durumda çağırır: işlem iliştirme, işlem ayırma, iş parçacığı iliştirme ve iş parçacığı ayırma. Bir DLL bir işlem adres alanına yüklendiğinde, onu kullanan bir uygulama yüklendiğinde ya da uygulama çalışma zamanında DLL istediğinde, işletim sistemi DLL verilerinin ayrı bir kopyasını oluşturur. Buna *işlem iliştirme*denir. *Iş parçacığı iliştirme* , dll 'nin yüklendiği işlem yeni bir iş parçacığı oluşturduğunda oluşur. İş parçacığı *ayırma* , iş parçacığı sonlandırıldığında oluşur ve *işlem ayırma* dll artık gerekli olmadığında ve bir uygulama tarafından serbest bırakıldığında gerçekleşir. İşletim sistemi, her olay türü için bir *neden* bağımsız değişkeni geçirerek, bu olayların her bırı için DLL giriş noktasına ayrı bir çağrı yapar. Örneğin, işletim sistemi, işlem eklemeyi bildirmek için *neden* bağımsız değişkeni olarak `DLL_PROCESS_ATTACH` gönderir.

VCRuntime kitaplığı, varsayılan başlatma ve sonlandırma işlemlerini işlemek için `_DllMainCRTStartup` adlı bir giriş noktası işlevi sağlar. İşlem iliştirme 'de `_DllMainCRTStartup` işlevi, arabellek güvenliği denetimlerini ayarlar, CRT ve diğer kitaplıkları başlatır, çalışma zamanı türü bilgilerini başlatır, statik ve yerel olmayan veriler için Oluşturucu başlatır ve çağırır, iş parçacığı yerel depolamayı başlatır, her iliştirme için bir iç statik sayacı artırır ve ardından Kullanıcı veya kitaplık tarafından sağlanan bir `DllMain`çağırır. İşlem ayırma sırasında, işlev bu adımları tersine geçer. `DllMain`çağırır, iç sayacı azaltır, yıkıcıları çağırır, CRT sonlandırma `atexit` işlevlerini çağırır ve diğer sonlandırma kitaplıklarına bildirir. Ek sayacı sıfır olduğunda işlev, Windows 'un DLL 'nin kaldırılabiliyor olduğunu göstermek için `FALSE` döndürür. `_DllMainCRTStartup` işlevi, iş parçacığı iliştirme ve iş parçacığı ayırma sırasında da çağrılır. Bu durumlarda, VCRuntime kodu hiç ek başlatma veya sonlandırma yapmaz ve yalnızca iletiyi iletmek için `DllMain` çağırır. `DllMain` işlem iliştirme 'den `FALSE` döndürürse, sinyal arızası `_DllMainCRTStartup` `DllMain` yeniden çağırır ve *neden* bağımsız değişkeni olarak `DLL_PROCESS_DETACH` geçirir, sonra sonlandırma sürecinin geri kalanı üzerinden ilerler.

Visual Studio 'da dll 'Ler oluştururken, VCRuntime tarafından sağlanan varsayılan giriş noktası `_DllMainCRTStartup` otomatik olarak bağlanır. [/Entry (giriş noktası simgesi)](reference/entry-entry-point-symbol.md) bağlayıcı SEÇENEĞINI kullanarak dll 'niz için bir giriş noktası işlevi belirtmeniz gerekmez.

> [!NOTE]
> /ENTRY: bağlayıcı seçeneğini kullanarak bir DLL için başka bir giriş noktası işlevi belirtmek mümkün olsa da, giriş noktası işlevinizin `_DllMainCRTStartup` yaptığı her şeyi aynı sırada yinelemeyeceğinden, bunu önermiyoruz. VCRuntime, davranışını çoğalttığınızda size izin veren işlevler sağlar. Örneğin, [/GS (arabellek güvenlik denetimi)](reference/gs-buffer-security-check.md) arabellek denetimi seçeneğini desteklemek için işlem iliştirme üzerinde hemen [__security_init_cookie](../c-runtime-library/reference/security-init-cookie.md) çağırabilirsiniz. DLL başlatma veya sonlandırma işlevlerinin geri kalanını gerçekleştirmek için, giriş noktası işleviyle aynı parametreleri geçirerek `_CRT_INIT` işlevini çağırabilirsiniz.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>DLL 'yi başlatma

Dll 'niz, DLL 'niz yüklenirken yürütülmesi gereken başlatma koduna sahip olabilir. Kendi DLL başlatma ve sonlandırma işlevlerinizi gerçekleştirebilmeniz için `_DllMainCRTStartup`, sağlayabilmeniz için `DllMain` adlı bir işlev çağırır. `DllMain`, DLL giriş noktası için gerekli imzaya sahip olmalıdır. Varsayılan giriş noktası işlevi, Windows tarafından geçirilen aynı parametreleri kullanarak `DllMain` çağırır `_DllMainCRTStartup`. Varsayılan olarak, bir `DllMain` işlevi sağlamazsanız, Visual Studio sizin için bir tane sağlar ve `_DllMainCRTStartup` her zaman çağrılabilecek bir şey olacak şekilde onunla bağlantı sağlar. Bu, DLL 'nizi başlatmanıza gerek kalmadığında, DLL 'nizi oluştururken yapmanız gereken özel bir şey olmadığı anlamına gelir.

Bu, `DllMain`için kullanılan imzadır:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Bazı kitaplıklar `DllMain` işlevini sizin için sarmalıdır. Örneğin, normal bir MFC DLL 'de, DLL 'niz için gereken başlatma ve sonlandırma gerçekleştirmek üzere `CWinApp` nesnenin `InitInstance` ve `ExitInstance` üye işlevlerini uygulayın. Daha ayrıntılı bilgi için bkz. [normal MFC DLL 'Leri başlatma](#initializing-regular-dlls) bölümü.

> [!WARNING]
> Bir DLL giriş noktasında güvenle yapabilecekleriniz için önemli sınırlamalar vardır. `DllMain`çağrısı güvensiz olan belirli Windows API 'Leri için [Genel En Iyi uygulamalar](/windows/win32/Dlls/dynamic-link-library-best-practices) bölümüne bakın. En basit başlatma için bir işlem yapmanız gerekiyorsa, bunu DLL için başlatma işlevinde yapın. `DllMain` çalıştıktan sonra ve DLL 'deki diğer işlevleri çağırmadan önce, uygulamaların başlatma işlevini çağırmasını zorunlu kılabilirsiniz.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>Sıradan (MFC olmayan) dll 'Leri başlatma

VCRuntime tarafından sağlanan `_DllMainCRTStartup` giriş noktasını kullanan sıradan (MFC olmayan) dll 'lerde kendi başlatma işlemini gerçekleştirmek için, DLL kaynak kodunuzun `DllMain`adlı bir işlev içermesi gerekir. Aşağıdaki kod, `DllMain` tanımının ne gibi görünebileceğini gösteren temel bir iskelet sunar:

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
> Daha eski Windows SDK belgeler, DLL giriş noktası işlevinin gerçek adının,/ENTRY seçeneğiyle bağlayıcı komut satırında belirtilmesi gerektiğini belirtir. Visual Studio ile, giriş noktası işlevinizin adı `DllMain`ise/ENTRY seçeneğini kullanmanız gerekmez. Aslında,/ENTRY seçeneğini kullanırsanız ve giriş noktası işlevinizi `DllMain`dışında bir şekilde adlandırırsanız, giriş noktası işleviniz `_DllMainCRTStartup` yaptığı aynı başlatma çağrılarını yaptığı takdirde CRT düzgün başlatılmaz.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Normal MFC DLL 'Leri başlatma

Normal MFC DLL 'Lerinin bir `CWinApp` nesnesi olduğundan, kendi başlatma ve sonlandırma görevlerini bir MFC uygulamasıyla aynı konumda gerçekleştirmeleri gerekir: DLL 'nin `CWinApp`türetilmiş sınıfının `InitInstance` ve `ExitInstance` üye işlevleri. MFC `DLL_PROCESS_ATTACH` ve `DLL_PROCESS_DETACH`için `_DllMainCRTStartup` tarafından çağrılan bir `DllMain` işlevi sağladığından kendi `DllMain` işlevinizi yazmamalıdır. MFC tarafından sağlanmış `DllMain` işlevi DLL 'niz yüklendiğinde `InitInstance` çağırır ve DLL kaldırılmadan önce `ExitInstance` çağırır.

Normal bir MFC DLL, `InitInstance` işlevinde [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) ve [TlsGetValue](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) çağırarak birden çok iş parçacığını takip edebilir. Bu işlevler, DLL 'nin iş parçacığına özgü verileri izlemesini sağlar.

MFC 'ye dinamik olarak bağlanan normal MFC DLL 'inizde MFC OLE, MFC veritabanı (veya DAO) veya MFC Yuvaları desteği kullanıyorsanız, hata ayıkla MFC uzantı dll 'Leri MFCO*Sürüm*d. dll, mfcd*Sürüm*d. dll ve mfcn*Sürüm*d. dll *(sürüm numarası* sürümü) otomatik olarak bağlanır. Normal MFC DLL 'nizin `CWinApp::InitInstance`kullanmakta olduğunuz bu DLL 'Lerden her biri için aşağıdaki önceden tanımlanmış başlatma işlevlerinden birini çağırmanız gerekir.

|MFC desteğinin türü|Çağırmak için başlatma işlevi|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*sürümü*D. dll)|`AfxOleInitModule`|
|MFC veritabanı (MFCD*Sürüm*D. dll)|`AfxDbInitModule`|
|MFC Yuvaları (MFCN*Sürüm*D. dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC uzantı dll 'Lerini Başlat

MFC uzantı dll 'Lerinin `CWinApp`türetilmiş bir nesnesi olmadığından (normal MFC DLL 'Leri gibi), başlatma ve sonlandırma kodunuzu MFC DLL Sihirbazının oluşturduğu `DllMain` işlevine eklemeniz gerekir.

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

Başlatma sırasında yeni bir `CDynLinkLibrary` nesnesi oluşturmak MFC uzantısı DLL 'sinin istemci uygulamasına `CRuntimeClass` nesneleri veya kaynakları dışarı aktarmaya izin verir.

MFC uzantı DLL 'nizi bir veya daha fazla normal MFC DLL 'lerden kullanacaksanız, `CDynLinkLibrary` nesnesi oluşturan bir başlatma işlevini dışarı aktarmanız gerekir. Bu işlev, MFC uzantı DLL 'sini kullanan normal MFC DLL 'Lerinin her birinden çağrılmalıdır. Bu başlatma işlevini çağırmak için uygun bir yer, MFC uzantısı DLL 'sinin veya işlevlerinin hiçbirini kullanmadan önce normal MFC DLL 'sinin `CWinApp`türetilmiş nesnesinin `InitInstance` üye işlevleridir.

MFC DLL Sihirbazı 'Nın ürettiği `DllMain`, `AfxInitExtensionModule` çağrısı modülün çalışma zamanı sınıflarını (`CRuntimeClass` yapılarını) ve `CDynLinkLibrary` nesnesi oluşturulduğunda kullanılmak üzere nesne fabrikalarını (`COleObjectFactory` nesneleri) yakalar. `AfxInitExtensionModule`dönüş değerini denetlemeniz gerekir; `AfxInitExtensionModule`sıfır değeri döndürülürse `DllMain` işlevinizden sıfır döndürün.

MFC uzantı DLL 'niz açık bir yürütülebilir dosya ile bağlantılandırılır (yürütülebilir dosya `AfxLoadLibrary` DLL 'ye bağlanması anlamına gelir), `DLL_PROCESS_DETACH``AfxTermExtensionModule` için bir çağrı eklemeniz gerekir. Bu işlev, MFC 'nin her bir işlem MFC uzantı DLL 'sinden ayrıldığında (işlem çıktığında veya bir `AfxFreeLibrary` çağrısının sonucu olarak DLL kaldırıldığında gerçekleşir) MFC uzantı DLL 'sini temizleyesağlar. MFC uzantı DLL 'niz uygulamaya örtük olarak bağlanılacağını `AfxTermExtensionModule` çağrısı gerekli değildir.

MFC uzantı dll 'Leri açıkça bağlayan uygulamalar, DLL 'yi boşaltırken `AfxTermExtensionModule` çağırmalıdır. Ayrıca, uygulama birden çok iş parçacığı kullanıyorsa, `AfxLoadLibrary` ve `AfxFreeLibrary` (Win32 işlevleri `LoadLibrary` ve `FreeLibrary`) kullanmaları gerekir. `AfxLoadLibrary` ve `AfxFreeLibrary` kullanmak, MFC uzantı DLL 'SI yüklendiğinde ve bellekten kaldırıldığında yürütülen başlatma ve başlatma kodunun genel MFC durumunu bozmamasını sağlar.

MFCx0. dll, `DllMain` çağrıldığı zaman tarafından tam olarak başlatıldığından, bellek ayırabilir ve MFC işlevlerini `DllMain` içinde (MFC 'nin 16 bit sürümünden farklı olarak) çağırabilirsiniz.

Uzantı dll 'Leri, `DllMain` işlevindeki `DLL_THREAD_ATTACH` ve `DLL_THREAD_DETACH` durumlarını işleyerek çoklu iş parçacıklı işlem yapabilir. Bu durumlar, iş parçacıkları DLL 'ye iliştirildiğinde ve bu sunucudan ayrıldığınızda `DllMain` geçirilir. Bir DLL eklendiğinde [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) çağrısı, DLL 'nin dll 'ye bağlı her iş parçacığı için iş parçacığı yerel depolama (TLS) dizinlerini korumasına olanak tanır.

Afxdllx. h üstbilgi dosyasının `AFX_EXTENSION_MODULE` ve `CDynLinkLibrary`tanımı gibi MFC uzantı dll 'Lerinde kullanılan yapılar için özel tanımlar içerdiğini unutmayın. Bu üstbilgi dosyasını MFC uzantı DLL 'nize dahil etmelisiniz.

> [!NOTE]
>  *Pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) içinde `_AFX_NO_XXX` makrolarından hiçbirini tanımlamanız veya tanımlamayın. Bu makrolar yalnızca belirli bir hedef platformun bu özelliği destekleyip desteklemediğini denetleme amacıyla mevcuttur. Bu makroları denetlemek için programınızı yazabilirsiniz (örneğin, `#ifndef _AFX_NO_OLE_SUPPORT`), ancak programınız bu makroları asla tanımlamaz veya tanımlamaz.

Çoklu iş parçacığını işleyen örnek bir başlatma işlevi, Windows SDK [dinamik bağlantı kitaplığında Iş parçacığı yerel depolama alanı kullanımına](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) dahildir. Örneğin, `LibMain`adlı bir giriş noktası işlevi içerdiğini unutmayın, ancak MFC ve C çalışma zamanı kitaplıklarıyla çalışacak şekilde bu işlevi `DllMain` adlandırmalısınız.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'daC++ C/dll oluşturma](dlls-in-visual-cpp.md)<br/>
[DllMain giriş noktası](/windows/win32/Dlls/dllmain)<br/>
[Dinamik bağlantı kitaplığı En Iyi uygulamaları](/windows/win32/Dlls/dynamic-link-library-best-practices)
