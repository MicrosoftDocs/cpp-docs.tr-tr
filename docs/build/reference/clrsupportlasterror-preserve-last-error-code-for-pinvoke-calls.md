---
title: /CLRSUPPORTLASTERROR (PInvoke Çağrıları için Son Hata Kodunu Koru)
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 19930591c2d0406c68b1a408622a49c9e8b1d551
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81322271"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (PInvoke Çağrıları için Son Hata Kodunu Koru)

**/CLRSUPPORTLASTERROR**, varsayılan olarak, **/clr**ile derlenen koddan, DLLS'de yerel işlevleri aramanızı sağlayan P/Invoke mekanizması aracılığıyla çağrılan işlevlerin son hata kodunu korur.

## <a name="syntax"></a>Sözdizimi

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Açıklamalar

Son hata kodunun korunması, performansın düşmesi anlamına gelir.  Son hata kodunu korumanın performans etkisine maruz kalmak istemiyorsanız, **/CLRSUPPORTLASTERROR:NO**ile bağlantı kurun.

**/CLRSUPPORTLASTERROR:SYSTEMDLL**ile bağlantı yaparak performans etkisini en aza indirebilirsiniz, bu da yalnızca sistem DL'leri üzerindeki işlevler için son hata kodunu korur.  Bir sistem DLL aşağıdakilerden biri olarak tanımlanır:

|||||
|-|-|-|-|
|ACLUI, ne kadar. Dll|EtkİnLİkLER. Dll|ADPTIF. Dll|ADVAPI32. Dll|
|ASYCFILT. Dll|AUTHZ'da. Dll|AVICAP32. Dll|AVIFIL32. Dll|
|Kabine. Dll|CLUSAPI' ye. Dll|COMCTL32. Dll|COMDLG32. Dll|
|COMSVCS. Dll|CREDUI, ne kadar çok şey var? Dll|CRYPT32' YE. Dll|CRYPTNET' E. Dll|
|CRYPTUI. Dll|D3D8THK. Dll|DBGENG. Dll|DBGHELP. Dll|
|DCIMAN32. Dll|DNSAPI' ya. Dll|DSPROP. Dll|DSUIEXT' den. Dll|
|GDI32' ye göre. Dll|GLU32' ye göre. Dll|HLINK. Dll|ICM32' ye ait. Dll|
|IMAGEHLP. Dll|IMM32' ye ait. Dll|IPHLPAPI' ya. Dll|IPROP' dan. Dll|
|KERNEL32. Dll|KSUSER. Dll|LOADPERF. Dll|LZ32'de. Dll|
|MAPI32' ye ait. Dll|MGMTAPI. Dll|MOBSYNC. Dll|Mpr. Dll|
|MPRAPI' de. Dll|MQRT' dan. Dll|MSACM32' ye. Dll|MSCMS. Dll|
|Msı. Dll|MSIMG32. Dll|MSRATING. Dll|MSTASK. Dll|
|MSVFW32. Dll|MSWSOCK' A Mı AIT? Dll|MTXEX. Dll|NDDEAPI. Dll|
|NETAPI32. Dll|NPPTOOLS. Dll|NTDSAPI' den. Dll|NTDSBCLI. Dll|
|NTMSAPI' ye. Dll|ODBC32. Dll|ODBCBCP. Dll|OLE32. Dll|
|OLEACC' da. Dll|OLEAUT32. Dll|OLEDLG, NE? Dll|OPENGL32' YE AIT. Dll|
|Pdh. Dll|POWRPROF. Dll|QOSNAME. Dll|Sorgu. Dll|
|RASAPI32. Dll|RASDLG, NE? Dll|RASSAPI, NE? Dll|RESUTILS. Dll|
|RICHED20. Dll|RPCNS4' de. Dll|RPCRT4' e. Dll|Rtm. Dll|
|RTUTILS, ne kadar çok şey var? Dll|SCARDDLG. Dll|SECUR32. Dll|SENSAPI. Dll|
|Setupapı. Dll|Sfc. Dll|KABUK 32. Dll|SHFOLDER. Dll|
|SHLWAPI. Dll|SISBKUP. Dll|SNMPAPI, ne oldu? Dll|SRCLIENT. Dll|
|Şti. Dll|TAPI32. Dll|Trafik. Dll|Url. Dll|
|URLMON' da. Dll|KULLANıCı 32. Dll|Userenv. Dll|USP10' u. Dll|
|Uxtheme. Dll|VDMDBG' den. Dll|Sürüm. Dll|Winfax. Dll|
|WINHTTP. Dll|Winınet. Dll|WINMM' DEN. Dll|WINSCARD' ı. Dll|
|WINTRUST' ı. Dll|WLDAP32. Dll|VAY CANıNa32. Dll|WS2_32.DLL|
|WSNMP32. Dll|WSOCK32.DLL|WTSAPI32. Dll|XOLEHLP. Dll|

> [!NOTE]
> Son hatanın korunması, clr kodu tarafından tüketilen yönetilmeyen işlevler için aynı modülde desteklenmez.

- Daha fazla bilgi için bkz: [/clr (Ortak Dil Çalışma Zamanı Derlemesi).](clr-common-language-runtime-compilation.md)

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik Sayfaları** iletişim kutusunu açın. Ayrıntılar için [Visual Studio'da C++ derleyicisi ayarlanın ve özellikler oluşturun.](../working-with-project-properties.md)

1. **Bağlayıcı** klasörünü tıklatın.

1. Komut **Satırı** özelliği sayfasını tıklatın.

1. Seçeneği **Ek Seçenekler** kutusuna yazın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, son hatayı değiştiren bir dışa aktarılan işleve sahip yerel bir DLL tanımlar.

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

Aşağıdaki örnek , **/CLRSUPPORTLASTERROR'ın**nasıl kullanılacağını gösteren DLL'yi tüketir.

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
