---
title: Kullanılmayan işlevler
description: Kullanım dışı bırakılan ve Microsoft C çalışma zamanı kitaplığı 'ndan (CRT) kaldırılan eski işlevleri listeler.
ms.date: 4/2/2020
api_name:
- _beep
- _sleep
- _loaddll
- _getdllprocaddr
- _seterrormode
- is_wctype
- _getsystime
- _setsystime
- _unloaddll
- _o__beep
- _o__getdllprocaddr
- _o__getsystime
- _o__loaddll
- _o__seterrormode
- _o__setsystime
- _o__sleep
- _o__unloaddll
- _o_is_wctype
api_location:
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: b8a094294abba46ae78e9d3529ccf3a7b0a31f39
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919887"
---
# <a name="obsolete-functions"></a>Kullanımdan kalkmış Işlevler

Belirli kitaplık işlevleri artık kullanılmıyor ve daha yeni en son eşdeğerleri var. Bu işlevleri güncelleştirilmiş sürümlere değiştirmenizi öneririz. Diğer Kullanımdan kaldırılmış işlevler CRT 'den kaldırılmıştır. Bu makalede kullanımdan kaldırılan işlevler ve Visual Studio 'nun belirli bir sürümünde kaldırılan işlevler listelenmektedir.

## <a name="deprecated-as-obsolete-in-visual-studio-2015"></a>Visual Studio 2015 ' de kullanımdan kalktı

|Kullanımdan kalktı işlevi|Yapıyı|
|-----------------------|-----------------|
|`is_wctype`|[iswctype](../c-runtime-library/reference/isctype-iswctype-isctype-l-iswctype-l.md)|
|`_loaddll`|[LoadLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryw), [LoadLibraryEx](/windows/win32/api/libloaderapi/nf-libloaderapi-loadlibraryexw)veya [loadpackagedlibrary](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary)|
|`_unloaddll`|[FreeLibrary](/windows/win32/api/libloaderapi/nf-libloaderapi-freelibrary)|
|`_getdllprocaddr`|[GetProcAddress](../build/getprocaddress.md)|
|`_seterrormode`|[SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode)|
|`_beep`|[Bip sesi](/windows/win32/api/utilapiset/nf-utilapiset-beep)|
|`_sleep`|[Uyku](/windows/win32/api/synchapi/nf-synchapi-sleep)|
|`_getsystime`|[GetLocalTime](/windows/win32/api/sysinfoapi/nf-sysinfoapi-getlocaltime)|
|`_setsystime`|[SetLocalTime](/windows/win32/api/sysinfoapi/nf-sysinfoapi-setlocaltime)|

## <a name="removed-from-the-crt-in-visual-studio-2015"></a>Visual Studio 2015 ' de CRT 'tan kaldırıldı

|Kullanımdan kalktı işlevi|Yapıyı|
|-----------------------|-----------------|
|[_cgets, _cgetws](../c-runtime-library/cgets-cgetws.md)|[_cgets_s, _cgetws_s](../c-runtime-library/reference/cgets-s-cgetws-s.md)|
|[gets, _getws](../c-runtime-library/gets-getws.md)|[gets_s, _getws_s](../c-runtime-library/reference/gets-s-getws-s.md)|
|[_get_output_format](../c-runtime-library/get-output-format.md)|Yok|
|[_heapadd](../c-runtime-library/heapadd.md)|Yok|
|[_heapset](../c-runtime-library/heapset.md)|Yok|
|[INP, ınpw, _inp, _inpw, _inpd](../c-runtime-library/inp-inpw-inpd.md)|Yok|
|[outp, outpw, _outp, _outpw _outpd](../c-runtime-library/outp-outpw-outpd.md)|Yok|
|[_set_output_format](../c-runtime-library/set-output-format.md)|Yok|

## <a name="removed-from-the-crt-in-earlier-versions-of-visual-studio"></a>Visual Studio 'nun önceki sürümlerindeki CRT 'den kaldırılmıştır

[_lock](../c-runtime-library/lock.md)

[_unlock](../c-runtime-library/unlock.md)
