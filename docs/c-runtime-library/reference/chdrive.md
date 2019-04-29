---
title: _chdrive
ms.date: 11/04/2016
apiname:
- _chdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- chdrive
- _chdrive
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
ms.openlocfilehash: 963b7b7b40b632981abfc1529beb9c48a5b991ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335483"
---
# <a name="chdrive"></a>_chdrive

Geçerli çalışma sürücüsünü değiştirir.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Parametreler

*Sürücü*<br/>
Geçerli çalışma belirten 1 ila 26 arasındaki bir tamsayı sürücü (1 = A, 2 = B vb.).

## <a name="return-value"></a>Dönüş Değeri

Sıfır (geçerli çalışma sürücüsü başarıyla değiştirilmişse, 0) Aksi durumda, -1.

## <a name="remarks"></a>Açıklamalar

Varsa *sürücü* olduğu bir aralıkta 1 ila 26 arasındaki, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **_chdrive** işlev -1 döndürür, **errno** ayarlanır **SPAWN**, ve **_doserrno** içinayarlayın **ERROR_INVALID_DRIVE**.

**_Chdrive** işlevi değil iş parçacığı bağımlı olduğundan dolayı **SetCurrentDirectory** işlevin kendisi iş parçacığı güvenli değildir. Kullanılacak **_chdrive** güvenli bir şekilde birden çok iş parçacıklı bir uygulamada, kendi iş parçacığı eşitlemenizi sağlamalısınız. Daha fazla bilgi için [SetCurrentDirectory](/windows/desktop/api/winbase/nf-winbase-setcurrentdirectory).

**_Chdrive** işlevi yalnızca geçerli çalışma sürücüsünü; değiştirir  **_chdir** geçerli çalışma dizinini değiştirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_chdrive**|\<Direct.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_getdrive](getdrive.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
