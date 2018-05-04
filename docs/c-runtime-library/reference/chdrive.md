---
title: _chdrive | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8f95169f62fa2eaf9c562bff463ad84c0827db9a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="chdrive"></a>_chdrive

Geçerli çalışma sürücüyü değiştirir.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Parametreler

*Sürücü*<br/>
Geçerli çalışma belirten 1-26 arasında bir tamsayı sürücü (1 = A, 2 = B ve benzeri).

## <a name="return-value"></a>Dönüş Değeri

Sıfır (geçerli çalışma sürücüsünü başarıyla; değiştirilmişse, 0) Aksi durumda, -1.

## <a name="remarks"></a>Açıklamalar

Varsa *sürücü* olan aralığı içinde 1 ila 26, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **_chdrive** işlev döndürür -1, **errno** ayarlanır **EACCES**, ve **_doserrno** içinayarlama **ERROR_INVALID_DRIVE**.

**_Chdrive** işlevi değil iş parçacığı bağımlı olduğundan dolayı **SetCurrentDirectory** kendisi iş parçacığı açısından güvenli işlevi. Kullanılacak **_chdrive** güvenli bir çok iş parçacıklı uygulamada kendi iş parçacığı eşitleme sağlamanız gerekir. Daha fazla bilgi için Git [MSDN Kitaplığı](http://go.microsoft.com/fwlink/p/?linkid=150542) arayın ve sonra **SetCurrentDirectory**.

**_Chdrive** işlevi değişiklikler yalnızca geçerli çalışma sürücü;  **_chdir** geçerli çalışma dizini değiştirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_chdrive**|\<Direct.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_getdrive](getdrive.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
