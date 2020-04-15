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

Visual Studio'yu kullanarak bir Dinamik bağlantı kitaplığı (DLL) oluşturduğunuzda, bağlayıcı Visual C++ çalışma zamanı kitaplığını (VCRuntime) içerir. VCRuntime, c/c++ çalıştırılabilir bir başlatma ve sonlandırma için gereken kodu içerir. Bir DLL'ye bağlandığında, VCRuntime kodu, windows işletim `_DllMainCRTStartup` sistemi iletilerini dll'ye iliştiren veya bir işlem veya iş parçacığından ayırmak için bir iç DLL giriş noktası işlevi sağlar. İşlev, `_DllMainCRTStartup` yığın arabelleği güvenliği kurulumu, C çalışma zamanı kitaplığı (CRT) başlatma ve sonlandırma gibi temel görevleri gerçekleştirir ve statik ve genel nesneler için oluşturuculara ve yıkıcılara çağrı yapar. `_DllMainCRTStartup`Ayrıca WinRT, MFC ve ATL gibi diğer kitaplıklar için kanca işlevlerini kendi başlatma ve sonlandırma gerçekleştirmeleri için çağırır. Bu başlatma olmadan, CRT ve diğer kitaplıklar yanı sıra statik değişkenler, başharfsiz bir durumda bırakılır. Aynı VCRuntime dahili başlatma ve sonlandırma yordamları DLL statik bağlı CRT veya dinamik bağlantılı CRT DLL kullanıp kullanmadığını denir.

## <a name="default-dll-entry-point-_dllmaincrtstartup"></a>Varsayılan DLL giriş noktası _DllMainCRTStartup

Windows'da, tüm DL'ler genellikle `DllMain`hem başlatma hem de sonlandırma için çağrılan isteğe bağlı bir giriş noktası işlevi içerebilir. Bu, gerektiğinde ek kaynak ayırma veya serbest bırakma fırsatı verir. Windows giriş noktası işlevini dört durumda çağırır: işlem ekleme, işlem ayırma, iş parçacığı ekleme ve iş parçacığı ayırma. Bir DLL bir işlem adresi alanına yüklendiğinde, onu kullanan bir uygulama yüklendiğinde veya uygulama çalışma zamanında DLL istediğinde, işletim sistemi DLL verilerinin ayrı bir kopyasını oluşturur. Buna *işlem iliştirme*denir. DLL'nin yüklendiği işlem yeni bir iş parçacığı oluşturduğunda *iş parçacığı ataşesi* oluşur. *İş parçacığı* ayırma, iş parçacığı sona erdiğinde oluşur ve *işlem ayırma* dll artık gerekli değildir ve bir uygulama tarafından serbest bırakılır. İşletim sistemi, her olay türü için bir *neden* bağımsız değişkeni geçirerek, bu olayların her biri için DLL giriş noktasına ayrı bir arama yapar. Örneğin, işletim sistemi `DLL_PROCESS_ATTACH` sinyal işlemi eklemek için *neden* bağımsız değişkenolarak gönderir.

VCRuntime kitaplığı varsayılan başlatma ve `_DllMainCRTStartup` sonlandırma işlemlerini işlemek için çağrılan bir giriş noktası işlevi sağlar. İşlem eklemede, `_DllMainCRTStartup` işlev arabellek güvenlik denetimleri kurar, CRT ve diğer kitaplıkları başharfe getirir, çalışma zamanı türü bilgilerini başharfe getirir, statik ve yerel olmayan veriler için oluşturucuları başharfe çağırır ve çağırır, `DllMain`iş parçacığı yerel depolamayı başharfe çağırır, her ekleme için bir dahili statik sayaç oluşturur ve ardından kullanıcı veya kitaplık verilen leri çağırır. İşlem ayırmada, işlev bu adımlardan ters yönde gider. `DllMain`Çağırır, dahili sayacı yok eder, CRT sonlandırma işlevlerini ve kayıtlı `atexit` işlevleri çağırır ve diğer sonlandırma kitaplıklarını da çağırır. Ek sayacı sıfıra gittiğinde, `FALSE` işlev Windows'a DLL'nin boşaltılabilir olduğunu belirtmek için geri döner. İş `_DllMainCRTStartup` parçacığı ekleme ve iş parçacığı ayırma sırasında işlev de denir. Bu gibi durumlarda, VCRuntime kodu kendi başına ek bir başlatma `DllMain` veya sonlandırma yapmaz ve sadece iletiyi iletmek için çağrıda bulunur. İşlem `DllMain` `FALSE` eki, sinyal hatası, `_DllMainCRTStartup` `DllMain` yeniden çağırır `DLL_PROCESS_DETACH` ve *neden* bağımsız değişkenolarak geçerse, sonra sonlandırma işleminin geri kalanı geçer döner.

Visual Studio'da DL'ler inşa edilirken, VCRuntime tarafından sağlanan varsayılan giriş noktası `_DllMainCRTStartup` otomatik olarak bağlanır. [/ENTRY (Giriş noktası simgesi)](reference/entry-entry-point-symbol.md) bağlantı seçeneğini kullanarak DLL'niz için bir giriş noktası işlevi belirtmeniz gerekmez.

> [!NOTE]
> /ENTRY: linker seçeneğini kullanarak bir DLL için başka bir giriş noktası işlevi belirtmek mümkün olsa da, giriş noktası işleviniz `_DllMainCRTStartup` aynı sırada olan her şeyi yinelemek zorunda kalacağından, bunu önermiyoruz. VCRuntime, davranışını yinelemenize olanak tanıyan işlevler sağlar. Örneğin, [/GS (Arabellek güvenlik denetimi)](reference/gs-buffer-security-check.md) arabellek denetleme seçeneğini desteklemek için işlem eklemek te __security_init_cookie [hemen](../c-runtime-library/reference/security-init-cookie.md) arayabilirsiniz. DLL başlatma `_CRT_INIT` veya sonlandırma işlevlerinin geri kalanını gerçekleştirmek için, giriş noktası işleviyle aynı parametreleri geçen işlevi arayabilirsiniz.

<a name="initializing-a-dll"></a>

## <a name="initialize-a-dll"></a>Bir DLL'yi başlatma

DLL'niz, DLL'niz yüklendiğinde çalıştırılması gereken başlatma koduna sahip olabilir. Kendi DLL başlatma ve sonlandırma işlevlerini gerçekleştirmek `_DllMainCRTStartup` için, `DllMain` sağlayabileceğiniz bir işlev çağırır. Bir `DllMain` DLL giriş noktası için gerekli imzaya sahip olmalısınız. Varsayılan giriş noktası `_DllMainCRTStartup` `DllMain` işlevi, Windows tarafından geçirilen parametreleri kullanarak çağrılar. Varsayılan olarak, bir `DllMain` işlev sağlamazsanız, Visual Studio sizin için bir `_DllMainCRTStartup` tane sağlar ve her zaman aramak için bir şey var, böylece bağlantılar. Bu, DLL'nizi başlatmanız gerekmiyorsa, DLL'nizi yaparken yapmanız gereken özel bir şey olmadığı anlamına gelir.

Bu için `DllMain`kullanılan imza:

```cpp
#include <windows.h>

extern "C" BOOL WINAPI DllMain (
    HINSTANCE const instance,  // handle to DLL module
    DWORD     const reason,    // reason for calling function
    LPVOID    const reserved); // reserved
```

Bazı kütüphaneler `DllMain` işlevi sizin için sarar. Örneğin, normal bir MFC DLL'de, `CWinApp` `InitInstance` DLL'nizin gerektirdiği başlatma ve sonlandırmayı gerçekleştirmek için nesnenin ve `ExitInstance` üye işlevlerini uygulayın. Daha fazla bilgi için [normal MFC DL'ler](#initializing-regular-dlls) bölümünü başlatma bölümüne bakın.

> [!WARNING]
> Bir DLL giriş noktasında güvenle yapabileceklerin önemli sınırları vardır. Arama güvenli olmayan belirli Windows API'ları için `DllMain`Genel En İyi [Uygulamalar'a](/windows/win32/Dlls/dynamic-link-library-best-practices) bakın. Eğer bir şey ama basit başlatma gerekiyorsa o zaman DLL için bir başlatma işlevi bunu. DLL'deki diğer işlevleri aramadan `DllMain` önce ve çalıştırıldıktan sonra başlatma işlevini çağırmak için uygulamalar gerektirebilirsiniz.

<a name="initializing-non-mfc-dlls"></a>

### <a name="initialize-ordinary-non-mfc-dlls"></a>Sıradan (MFC olmayan) DL'leri başlatma

VCRuntime tarafından sağlanan `_DllMainCRTStartup` giriş noktasını kullanan sıradan (MFC olmayan) DL'lerde kendi başlatma işleminizi gerçekleştirmek için, `DllMain`DLL kaynak kodunuz . Aşağıdaki kod, tanımının `DllMain` nasıl görünebileceğini gösteren temel bir iskelet sunar:

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
> Eski Windows SDK belgeleri, DLL giriş noktası işlevinin gerçek adının /ENTRY seçeneği ile bağlayıcı komut satırında belirtilmesi gerektiğini söyler. Visual Studio ile giriş noktası işlevinizin adı `DllMain`. Aslında, /ENTRY seçeneğini kullanır ve giriş noktası işlevinizi başka `DllMain`bir şey olarak adlandırırsanız, giriş noktası işleviniz aynı başlatma çağrısı `_DllMainCRTStartup` yapmadıkça CRT düzgün bir şekilde başharfe para almaz.

<a name="initializing-regular-dlls"></a>

### <a name="initialize-regular-mfc-dlls"></a>Normal MFC DLL'leri başlatma

Normal MFC DLL'lerinin `CWinApp` bir nesnesi olduğundan, başlangıç ve sonlandırma görevlerini Bir MFC `InitInstance` `ExitInstance` uygulamasıyla aynı konumda gerçekleştirmeleri gerekir: DLL'nin `CWinApp`türetilmiş sınıfının ve üye işlevlerinde. Çünkü MFC `DllMain` `_DllMainCRTStartup` için `DLL_PROCESS_ATTACH` çağrılan bir işlev `DLL_PROCESS_DETACH`sağlar ve , `DllMain` kendi işlevini yazmamalısınız. DLL'niz `DllMain` yüklendiğinde `InitInstance` MFC tarafından sağlanan işlev `ExitInstance` çağrır ve DLL boşaltılmadan önce çağırır.

Normal bir MFC DLL, işlevinde [TlsAlloc](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) ve [TlsGetValue'i](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsgetvalue) arayarak birden fazla iş parçacığının takibini `InitInstance` yapabilir. Bu işlevler, DLL'nin iş parçacığına özgü verileri izlemesine olanak sağlar.

MFC'ye dinamik olarak bağlanan normal MFC DLL'nizde, sırasıyla mfc OLE, MFC Veritabanı (veya DAO) veya MFC Soketleri desteği kullanıyorsanız, hata ayıklama MFC uzantısı DLSs MFCO*version*D.dll, MFCD*version*D.dll ve MFCN*sürüm*D.dll *(sürüm* numarasının bulunduğu yer) otomatik olarak bağlanır. Normal MFC DLL'nizde kullandığınız bu DL'lerin her biri için aşağıdaki önceden tanımlanmış başlatma `CWinApp::InitInstance`işlevlerinden birini aramalısınız.

|MFC desteği türü|Aramak için başlatma işlevi|
|-------------------------|-------------------------------------|
|MFC OLE (MFCO*sürüm*D.dll)|`AfxOleInitModule`|
|MFC Veritabanı (MFCD*sürüm*D.dll)|`AfxDbInitModule`|
|MFC Soketleri (MFCN*sürüm*D.dll)|`AfxNetInitModule`|

<a name="initializing-extension-dlls"></a>

### <a name="initialize-mfc-extension-dlls"></a>MFC uzantılı DL'leri başlatma

MFC uzantılı DL'lerin `CWinApp`türetilmiş bir nesnesi olmadığından (normal MFC DLL'leri gibi), başlangıç ve sonlandırma kodunuzu MFC DLL Sihirbazı'nın `DllMain` oluşturduğu işleve eklemeniz gerekir.

Sihirbaz, MFC uzantılı DL'ler için aşağıdaki kodu sağlar. Kodda, `PROJNAME` projenizin adı için bir yer tutucu.

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

Başlatma sırasında `CDynLinkLibrary` yeni bir nesne oluşturmak, MFC `CRuntimeClass` uzantısı DLL'nin nesneleri veya kaynakları istemci uygulamasına dışa aktarmasına olanak tanır.

MFC uzantınızı bir veya daha fazla normal MFC DLL'den kullanacaksanız, nesne `CDynLinkLibrary` oluşturan bir başlatma işlevi dışa aktarmanız gerekir. Bu işlev, MFC uzantısı DLL'yi kullanan normal MFC DL'lerinin her birinden çağrılmalıdır. Bu başlatma işlevini çağırmak için uygun `InitInstance` bir yer, MFC uzantısı DLL'nin dışa aktarılan sınıfları veya işlevlerinden herhangi birini kullanmadan önce normal MFC DLL'nin `CWinApp`türetilmiş nesnesinin üye işlevindedir.

`DllMain` MFC DLL Sihirbazı'nın oluşturduğu çağrıda, `AfxInitExtensionModule` `CRuntimeClass` `CDynLinkLibrary` nesne oluşturulduğunda kullanılmak üzere modülün çalışma zamanı sınıflarını (yapıları) ve nesne fabrikalarını (nesneleri)`COleObjectFactory` yakalar. Geri dönüş değerini kontrol `AfxInitExtensionModule`etmelisiniz; sıfır değeri döndürülürse, `AfxInitExtensionModule`işlevinizden `DllMain` sıfır döndürün.

MFC uzantınız DLL'niz çalıştırılabilir bir çağrıya açıkça `AfxLoadLibrary` bağlanacaksa (Yani DLL'ye `AfxTermExtensionModule` bağlanmak `DLL_PROCESS_DETACH`için çalıştırılabilir aramalar), bir çağrı eklemeniz gerekir. Bu işlev, her işlem MFC uzantısı DLL'den ayrılan (işlem çıktığında veya `AfxFreeLibrary` bir çağrı sonucunda DLL boşaltıldığında meydana gelen) MFC uzantısı DLL'yi temizlemesine olanak tanır. MFC uzantıdınız DLL uygulamaya dolaylı olarak bağlanacaksa, çağrı gerekmez. `AfxTermExtensionModule`

MFC uzantılı DL'lere açıkça bağlanan `AfxTermExtensionModule` uygulamalar, DLL'yi serbest düşürürken aramalıdır. Ayrıca kullanmaları `AfxLoadLibrary` `AfxFreeLibrary` ve (Win32 işlevleri `LoadLibrary` `FreeLibrary`yerine ve) uygulama birden çok iş parçacığı kullanıyorsa. MFC uzantısı DLL yüklendiğinde ve boşaltıldığında çalıştıran başlatma ve kapatma kodunun kullanılması `AfxLoadLibrary` ve `AfxFreeLibrary` genel MFC durumunun bozulmamasını sağlar.

MFCx0.dll çağrıldığında `DllMain` tamamen başharfe çevrildiği için, belleği ayırabilir `DllMain` ve MFC işlevlerini arayabilirsiniz (MFC'nin 16 bit sürümünden farklı olarak).

Uzatma DL'leri, fonksiyondaki `DLL_THREAD_ATTACH` ve `DLL_THREAD_DETACH` servis taleplerini ele `DllMain` alarak çok iş parçacığı nın icabına bakabilir. Bu servis parçacıkları `DllMain` DLL'den bağlandığında ve çıkarıldıklarında bu servis talepleri aktarılır. DLL takıldığında [TlsAlloc'u](/windows/win32/api/processthreadsapi/nf-processthreadsapi-tlsalloc) çağırmak, DLL'ye bağlı her iş parçacığı için dizin yerel depolama (TLS) dizinlerini korumasını sağlar.

Üstbilgi dosyası Afxdllx.h'nin MFC uzantılı DL'lerde kullanılan yapılar için `AFX_EXTENSION_MODULE` tanım `CDynLinkLibrary`ve . Bu üstbilgi dosyanı MFC uzantısı DLL'nize eklemelisiniz.

> [!NOTE]
> `_AFX_NO_XXX` *Pch.h* 'deki (Visual Studio 2017 ve öncesinde*stdafx.h)* makroların hiçbirini tanımlamanız veya tanımlamamış sınız dır. Bu makrolar yalnızca belirli bir hedef platformun bu özelliği destekleyip desteklemediğini denetlemek amacıyla bulunur. Programınızı bu makroları denetlemek için yazabilirsiniz `#ifndef _AFX_NO_OLE_SUPPORT`(örneğin, ), ancak programınız bu makroları asla tanımlamamalı veya tanımlamamalıdır.

Windows SDK'daki [Dinamik Bağlantı Kitaplığında İş Parçacığı Yerel Depolama'yı kullanma](/windows/win32/Dlls/using-thread-local-storage-in-a-dynamic-link-library) işlemine çok iş parçacığı işleyen örnek bir başlatma işlevi dahildir. Örneğin ,, MFC ve C `LibMain`çalışma zamanı kitaplıklarıyla çalışması için bu işlevi `DllMain` adlandırmanız gerektiğini unutmayın.

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C/C++ DL'ler oluşturma](dlls-in-visual-cpp.md)<br/>
[DllMain giriş noktası](/windows/win32/Dlls/dllmain)<br/>
[Dinamik bağlantı Kitaplık En İyi Uygulamalar](/windows/win32/Dlls/dynamic-link-library-best-practices)
