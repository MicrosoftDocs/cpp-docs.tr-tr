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
ms.openlocfilehash: 7e36867bb8237c549fd250be88a99244766920ba
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69500280"
---
# <a name="_chdrive"></a>_chdrive

Geçerli çalışma sürücüsünü değiştirir.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Parametreler

*sürücü*<br/>
Geçerli çalışma sürücüsünü belirten (1 = A, 2 = B vb.) 1 ila 26 arasında bir tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Geçerli çalışma sürücüsü başarıyla değiştirilmişse sıfır (0); Aksi takdirde,-1.

## <a name="remarks"></a>Açıklamalar

*Sürücü* 1 ile 26 arasında değilse, geçersiz parametre Işleyicisi [parametre doğrulamada](../../c-runtime-library/parameter-validation.md)açıklandığı şekilde çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **_chdrive** işlevi-1 döndürür, **errno** , **EACCES**olarak ayarlanır ve **_doserrno** , **ERROR_INVALID_DRIVE**olarak ayarlanır.

**_Chdrive** işlevi, iş parçacığı açısından güvenli olmayan **SetCurrentDirectory** işlevine bağlı olduğundan iş parçacığı açısından güvenli değildir. Çok iş parçacıklı bir uygulamada **_chdrive** 'u güvenle kullanmak için kendi iş parçacığı eşitlemesini sağlamanız gerekir. Daha fazla bilgi için bkz. [SetCurrentDirectory](/windows/win32/api/winbase/nf-winbase-setcurrentdirectory).

**_Chdrive** işlevi yalnızca geçerli çalışma sürücüsünü değiştirir;  **_chdir** geçerli çalışma dizinini değiştirir.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_chdrive**|\<Direct. h >|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Getdrive](getdrive.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
