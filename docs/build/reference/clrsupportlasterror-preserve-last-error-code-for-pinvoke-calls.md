---
title: -CLRSUPPORTLASTERROR (son hata kodunu Koru PInvoke çağrıları için) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /CLRSUPPORTLASTERROR
dev_langs:
- C++
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a80adfe34677c15a36af96ac412b7934747e68bc
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45707479"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR (PInvoke Çağrıları için Son Hata Kodunu Koru)

**/ CLRSUPPORTLASTERROR**, varsayılan olarak açıktır, işlevlerin son hata kodunu adlı kodundan DLL'LERDE yerel işlevleri çağırma olanak tanıyan bir P/Invoke mekanizmasıyla aracılığıyla korur ile derlenmiş olan **/CLR**.

## <a name="syntax"></a>Sözdizimi

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>Açıklamalar

Son hata kodunu koruma performans düşüklüğü anlamına gelir.  Performans etkisini son hata kodunu koruma uygulanmaya istemiyorsanız ile bağlantı **/CLRSUPPORTLASTERROR:NO**.

İle bağlayarak performans etkisini en aza indirebilirsiniz **/CLRSUPPORTLASTERROR:SYSTEMDLL**, hangi yalnızca korur işlevler için son hata kodunu sistem DLL'lerini.  Bir sistem DLL Dosyasına aşağıdakilerden biri tanımlanır:

|||||
|-|-|-|-|
|ACLUI. DLL|ACTIVEDS. DLL|ADPTIF. DLL|ADVAPI32. DLL|
|ASYCFILT. DLL|AUTHZ. DLL|AVICAP32. DLL|AVIFIL32. DLL|
|DOLAP. DLL|CLUSAPI. DLL|COMCTL32. DLL|COMDLG32. DLL|
|COMSVCS. DLL|CREDUI. DLL|CRYPT32. DLL|CRYPTNET. DLL|
|KULLANILAMIYOR. DLL|D3D8THK. DLL|DBGENG. DLL|DBGHELP. DLL|
|DCIMAN32. DLL|DNSAPI. DLL|DSPROP. DLL|DSUIEXT. DLL|
|GDI32. DLL|GLU32. DLL|HLINK. DLL|ICM32. DLL|
|IMAGEHLP. DLL|IMM32. DLL|IPHLPAPI. DLL|IPROP. DLL|
|KERNEL32. DLL|KSUSER. DLL|LOADPERF. DLL|LZ32. DLL|
|MAPI32. DLL|MGMTAPI. DLL|MOBSYNC. DLL|MPR'I. DLL|
|MPRAPI. DLL|MQRT. DLL|MSACM32. DLL|MSCMS. DLL|
|MSI. DLL|MSIMG32. DLL|MSRATING. DLL|MSTASK. DLL|
|MSVFW32. DLL|MSWSOCK. DLL|MTXEX. DLL|NDDEAPI. DLL|
|NETAPI32. DLL|NPPTOOLS. DLL|NTDSAPI. DLL|NTDSBCLI. DLL|
|NTMSAPI. DLL|ODBC32. DLL|ODBCBCP. DLL|OLE32. DLL|
|OLEACC. DLL|OLEAUT32. DLL|OLEDLG. DLL|OPENGL32. DLL|
|PDH. DLL|POWRPROF. DLL|QOSNAME. DLL|SORGU. DLL|
|RASAPI32. DLL|RASDLG. DLL|RASSAPI. DLL|RESUTILS. DLL|
|RICHED20. DLL|RPCNS4. DLL|RPCRT4. DLL|RTM. DLL|
|RTUTILS. DLL|SCARDDLG. DLL|SECUR32. DLL|SENSAPI. DLL|
|SETUPAPI. DLL|SFC. DLL|SHELL32. DLL|SHFOLDER. DLL|
|SHLWAPI. DLL|SISBKUP. DLL|SNMPAPI. DLL|SRCLIENT. DLL|
|STI'YA. DLL|TAPI32. DLL|TRAFİĞİ. DLL|URL. DLL|
|URLMON. DLL|USER32. DLL|USERENV. DLL|USP10. DLL|
|UXTHEME. DLL|VDMDBG. DLL|SÜRÜM. DLL|WINFAX. DLL|
|WINHTTP. DLL|WİNINET. DLL|WINMM. DLL|WINSCARD. DLL|
|WINTRUST. DLL|WLDAP32. DLL|WOW32. DLL|WS2_32.DLL|
|WSNMP32. DLL|WSOCK32.DLL|WTSAPI32. DLL|XOLEHLP. DLL|

> [!NOTE]
>  Son hata koruma aynı modülde CLR kod tarafından kullanılan yönetilmeyen işlevleri için desteklenmiyor.

- Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **komut satırı** özellik sayfası.

1. Seçeneğini yazın **ek seçenekler** kutusu.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="example"></a>Örnek

Aşağıdaki örnek, yerel bir DLL işleviyle son hata değiştiren bir dışarı aktarılan tanımlar.

```
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

Aşağıdaki örnek nasıl kullanılacağını gösteren, DLL kullanan **/CLRSUPPORTLASTERROR**.

```
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

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)