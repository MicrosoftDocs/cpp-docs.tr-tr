---
title: Kullanılmayan işlevler
ms.date: 01/22/2019
apiname:
- _beep
- _sleep
- _loaddll
- _getdllprocaddr
- _seterrormode
- is_wctype
- _getsystime
- _setsystime
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-process-l1-1-0.dll
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- is_wctype
- _loaddll
- _unloaddll
- _getdllprocaddr
- _seterrormode
- _beep
- _sleep
- _getsystime
- corecrt_wctype/is_wctype
- process/_loaddll
- process/_unloaddll
- process/_getdllprocaddr
- stdlib/_seterrormode
- stdlib/_beep
- stdlib/_sleep
- time/_getsystime
- time/_setsystime
helpviewer_keywords:
- obsolete functions
- _beep function
- _sleep function
- _seterrormode function
ms.assetid: 8e14c2d4-1481-4240-8586-47eb43db02b0
ms.openlocfilehash: edac8fde530752c911058acdaccccea6d0318b8c
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702680"
---
# <a name="obsolete-functions"></a>Kullanılmayan işlevler

Belirli bir kitaplığı işlevleri artık kullanılmayan ve daha yeni eşdeğerleri vardır. Bu hizmetin güncel sürümleriyle değiştirmeniz önerilir. Eski diğer işlevleri CRT kaldırılmıştır. Bu konu, kullanılmayan olarak kullanım dışı işlevleri ve Visual Studio'nun belirli bir sürümde kaldırılan işlevleri listeler.

## <a name="deprecated-as-obsolete-in-visual-studio-2015"></a>Visual Studio 2015'te eski olarak kullanım dışı

|Eski işlevi|Alternatif|
|-----------------------|-----------------|
|`is_wctype`|[iswctype](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|
|`_loaddll`|[LoadLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibrarya), [LoadLibraryEx](/windows/desktop/api/libloaderapi/nf-libloaderapi-loadlibraryexa), veya [LoadPackagedLibrary](/windows/desktop/api/winbase/nf-winbase-loadpackagedlibrary)|
|`_unloaddll`|[FreeLibrary](/windows/desktop/api/libloaderapi/nf-libloaderapi-freelibrary)|
|`_getdllprocaddr`|[GetProcAddress](../build/getprocaddress.md)|
|`_seterrormode`|[SetErrorMode](https://msdn.microsoft.com/library/windows/desktop/ms680621)|
|`_beep`|[Bip sesi](/windows/desktop/api/utilapiset/nf-utilapiset-beep)|
|`_sleep`|[Uyku](/windows/desktop/api/synchapi/nf-synchapi-sleep)|
|`_getsystime`|[GetLocalTime](/windows/desktop/api/sysinfoapi/nf-sysinfoapi-getlocaltime)|
|`_setsystime`|[SetLocalTime](/windows/desktop/api/sysinfoapi/nf-sysinfoapi-setlocaltime)|

## <a name="removed-from-the-crt-in-visual-studio-2015"></a>Visual Studio 2015'te CRT kaldırıldı

|Eski işlevi|Alternatif|
|-----------------------|-----------------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md)|[_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|
|[gets, _getws](../c-runtime-library/gets-getws.md)|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|
|[_get_output_format](../c-runtime-library/get-output-format.md)|Hiçbiri|
|[_heapadd](../c-runtime-library/heapadd.md)|Hiçbiri|
|[_heapset](../c-runtime-library/heapset.md)|Hiçbiri|
|[inp, inpw](../c-runtime-library/inp-inpw.md)|Hiçbiri|
|[_inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)|Hiçbiri|
|[outp, outpw](../c-runtime-library/outp-outpw.md)|Hiçbiri|
|[_outp, _outpw, _outpd](../c-runtime-library/outp-outpw-outpd.md)|Hiçbiri|
|[_set_output_format](../c-runtime-library/set-output-format.md)|Hiçbiri|

## <a name="removed-from-the-crt-in-earlier-versions-of-visual-studio"></a>Visual Studio'nun önceki sürümlerinde CRT kaldırıldı

[_lock](../c-runtime-library/lock.md)

[_unlock](../c-runtime-library/unlock.md)