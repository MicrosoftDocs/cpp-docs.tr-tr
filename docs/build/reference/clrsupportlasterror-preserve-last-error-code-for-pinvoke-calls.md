---
title: /CLRSUPPORTLASTERROR (PInvoke Çağrıları için Son Hata Kodunu Koru)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 64948d81759d415245e741bc6152d56bb35480d2
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988345"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (PInvoke Çağrıları için Son Hata Kodunu Koru)

Varsayılan olarak açık olan **/CLRSUPPORTLASTERROR**, P/Invoke mekanizması aracılığıyla çağrılan işlevlerin son hata kodunu korur, bu da **/clr**ile derlenen koddan dll 'lerde yerel işlevleri çağırmanıza olanak sağlar.

## <a name="syntax"></a>Sözdizimi

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Açıklamalar

Son hata kodunun korunması, performansı azaltır.  Son hata kodunu korumak için performans etkisi uygulanmasını istemiyorsanız, **/CLRSUPPORTLASTERROR: No**ile bağlayın.

Yalnızca sistem dll 'Lerinde işlevlere yönelik son hata kodunu koruyan **/CLRSUPPORTLASTERROR: SYSTEMDLL**ile bağlantı kurarak performans etkisini en aza indirmenize sağlayabilirsiniz.  Bir sistem DLL 'SI, aşağıdakilerden biri olarak tanımlanır:

|||||
|-|-|-|-|
|ACLUI. DOSYASıNı|ACTIVED. DOSYASıNı|ADPTIF. DOSYASıNı|ADVAPI32. DOSYASıNı|
|ASYCFILT. DOSYASıNı|AUTHZ. DOSYASıNı|AVICAP32. DOSYASıNı|AVIFIL32. DOSYASıNı|
|Dolap. DOSYASıNı|CLUSAPı. DOSYASıNı|Comctl32. DOSYASıNı|COMDLG32. DOSYASıNı|
|COMSVCS. DOSYASıNı|CREDUı. DOSYASıNı|Crypt32. DOSYASıNı|CRYPTNET. DOSYASıNı|
|CRYPTUI. DOSYASıNı|D3D8THK. DOSYASıNı|DBGENG. DOSYASıNı|DBGHELP. DOSYASıNı|
|DCIMAN32. DOSYASıNı|DNSAPI. DOSYASıNı|DSPROP. DOSYASıNı|DSUIEXT. DOSYASıNı|
|GDI32. DOSYASıNı|GLU32. DOSYASıNı|H. DOSYASıNı|ICM32. DOSYASıNı|
|Gereken Imagehlp. DOSYASıNı|IMM32. DOSYASıNı|IPHLPAPI. DOSYASıNı|IPROP. DOSYASıNı|
|Kernel32. DOSYASıNı|KSUSER. DOSYASıNı|LOADPERF. DOSYASıNı|LZ32. DOSYASıNı|
|MAPI32. DOSYASıNı|MGMTAPI. DOSYASıNı|MOBSYNC. DOSYASıNı|MPR. DOSYASıNı|
|MPRAPı. DOSYASıNı|MQRT. DOSYASıNı|MSACM32. DOSYASıNı|Mscms. DOSYASıNı|
|Defteri. DOSYASıNı|MSIMG32. DOSYASıNı|MSRATING. DOSYASıNı|Mstask. DOSYASıNı|
|MSVFW32. DOSYASıNı|MSWSOCK. DOSYASıNı|MTXEX. DOSYASıNı|NDDEAPı. DOSYASıNı|
|NETAPI32. DOSYASıNı|NPPTOOLS. DOSYASıNı|NTDSAPı. DOSYASıNı|NTDSBCLI. DOSYASıNı|
|NTMSAPı. DOSYASıNı|Odbc32. DOSYASıNı|ODBCBCP. DOSYASıNı|Ole32. DOSYASıNı|
|OLEACC. DOSYASıNı|Duy. DOSYASıNı|OLEDLG. DOSYASıNı|OPENGL32. DOSYASıNı|
|PDH. DOSYASıNı|POWRPROF. DOSYASıNı|QOSNAME. DOSYASıNı|Sorgulayamadı. DOSYASıNı|
|RASAPI32. DOSYASıNı|OYSDLG. DOSYASıNı|RASSAPı. DOSYASıNı|RESUTILS. DOSYASıNı|
|RICHED20. DOSYASıNı|RPCNS4. DOSYASıNı|RPCRT4. DOSYASıNı|RTM. DOSYASıNı|
|RTUTILS. DOSYASıNı|SCARDDLG. DOSYASıNı|Aracılığıyla secur32 kullanır. DOSYASıNı|SENSAPı. DOSYASıNı|
|SETUPAPI. DOSYASıNı|Sfc. DOSYASıNı|Shell32. DOSYASıNı|SHFOLDER. DOSYASıNı|
|SHLWAPI. DOSYASıNı|SISDK. DOSYASıNı|SNMPAPı. DOSYASıNı|SRCLIENT. DOSYASıNı|
|I. DOSYASıNı|TAPI32. DOSYASıNı|Ğinden. DOSYASıNı|'Deki. DOSYASıNı|
|Urlmon. DOSYASıNı|User32. DOSYASıNı|Userenv. DOSYASıNı|USP10. DOSYASıNı|
|UXTHEME. DOSYASıNı|VDMDBG. DOSYASıNı|Sürüm. DOSYASıNı|WINFAX. DOSYASıNı|
|WINHTTP. DOSYASıNı|Dosyasında. DOSYASıNı|WıNMM. DOSYASıNı|WINSCARD. DOSYASıNı|
|WINTRUST. DOSYASıNı|WLDAP32. DOSYASıNı|WOW32. DOSYASıNı|WS2_32. DLL|
|WSNMP32. DOSYASıNı|WSOCK32.DLL|WTSAPI32. DOSYASıNı|XOLEHLP. DOSYASıNı|

> [!NOTE]
>  Son hatanın korunması, CLR kodu tarafından tüketilen yönetilmeyen işlevlerde aynı modülde desteklenmez.

- Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](clr-common-language-runtime-compilation.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Komut satırı** Özellik sayfasına tıklayın.

1. Seçeneği **ek seçenekler** kutusuna yazın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, son hatayı değiştiren bir içe aktarılmış işlevle yerel bir DLL tanımlar.

```cpp
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

## <a name="example"></a>Örnek

Aşağıdaki örnek, **/CLRSUPPORTLASTERROR**'in nasıl KULLANıLACAĞıNı gösteren dll 'yi kullanır.

```cpp
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC Bağlayıcı Seçenekleri](linker-options.md)
