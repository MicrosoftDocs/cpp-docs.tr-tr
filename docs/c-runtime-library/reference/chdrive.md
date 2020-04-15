---
title: _chdrive
ms.date: 4/2/2020
api_name:
- _chdrive
- _o__chdrive
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
- api-ms-win-crt-filesystem-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- chdrive
- _chdrive
helpviewer_keywords:
- drives, changing
- _chdrive function
- chdrive function
ms.assetid: 212a1a4b-4fa8-444e-9677-7fca4c8c47e3
ms.openlocfilehash: 0c19fefcf6a766842ee2e25cbe6bdb61bbf48e7d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333353"
---
# <a name="_chdrive"></a>_chdrive

Geçerli çalışma sürücüsünün değiştirir.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _chdrive(
   int drive
);
```

### <a name="parameters"></a>Parametreler

*Sürücü*<br/>
Geçerli çalışma sürücüsü (1=A, 2=B vb.) belirten 1'den 26'ya kadar bir tamsayı.

## <a name="return-value"></a>Dönüş Değeri

Sıfır (0) geçerli çalışma sürücüsü başarıyla değiştirildiyse; aksi takdirde, -1.

## <a name="remarks"></a>Açıklamalar

*Sürücü* 1 ile 26 arasında aralıkta değilse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **_chdrive** işlevi -1 döndürür, **errno** **EACCES**olarak ayarlanır ve **_doserrno** **ERROR_INVALID_DRIVE**ayarlanır.

İş parçacığı nın kendisi güvenli olmayan **SetCurrentDirectory** işlevine bağlı **olduğundan, _chdrive** işlevi iş parçacığı için güvenli değildir. çok iş parçacığı uygulamasında **_chdrive** güvenli bir şekilde kullanmak için kendi iş parçacığı eşitlemenizi sağlamanız gerekir. Daha fazla bilgi için [SetCurrentDirectory'ye](/windows/win32/api/winbase/nf-winbase-setcurrentdirectory)bakın.

**_chdrive** işlevi yalnızca geçerli çalışma sürücüsünu değiştirir;  **_chdir** geçerli çalışma dizinini değiştirir.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_chdrive**|\<direct.h>|

Daha fazla bilgi için [Uyumluluk'a](../../c-runtime-library/compatibility.md)bakın.

## <a name="example"></a>Örnek

[_getdrive](getdrive.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dizin Kontrolü](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_fullpath, _wfullpath](fullpath-wfullpath.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
[system, _wsystem](system-wsystem.md)<br/>
