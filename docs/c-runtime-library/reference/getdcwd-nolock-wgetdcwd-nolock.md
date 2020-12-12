---
description: 'Hakkında daha fazla bilgi edinin: _getdcwd_nolock _wgetdcwd_nolock'
title: _getdcwd_nolock, _wgetdcwd_nolock
ms.date: 11/04/2016
api_name:
- _wgetdcwd_nolock
- _getdcwd_nolock
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _wgetdcwd_nolock
- tgetdcwd_nolock
- wgetdcwd_nolock
- _getdcwd_nolock
- _tgetdcwd_nolock
- getdcwd_nolock
helpviewer_keywords:
- getdcwd_nolock function
- _tgetdcwd_nolock function
- working directory
- tgetdcwd_nolock function
- _getdcwd_nolock function
- current working directory
- wgetdcwd_nolock function
- _wgetdcwd_nolock function
- directories [C++], current working
ms.assetid: d9bdf712-43f8-4173-8f9a-844e82beaa97
ms.openlocfilehash: d40bd7a3cf8d666ad7ba108fc71e443ea262c13f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256568"
---
# <a name="_getdcwd_nolock-_wgetdcwd_nolock"></a>_getdcwd_nolock, _wgetdcwd_nolock

Belirtilen sürücüdeki geçerli çalışma dizininin tam yolunu alır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_getdcwd_nolock(
   int drive,
   char *buffer,
   int maxlen
);
wchar_t *_wgetdcwd_nolock(
   int drive,
   wchar_t *buffer,
   int maxlen
);
```

### <a name="parameters"></a>Parametreler

*sürücü*<br/>
Disk sürücüsü.

*arabelleğin*<br/>
Yol için depolama konumu.

*maxlen*<br/>
Karakter cinsinden en fazla yol uzunluğu: **`char`** **_getdcwd** ve **`wchar_t`** **_wgetdcwd** için.

## <a name="return-value"></a>Dönüş Değeri

Bkz. [_getdcwd, _wgetdcwd](getdcwd-wgetdcwd.md).

## <a name="remarks"></a>Açıklamalar

**_getdcwd_nolock** ve **_wgetdcwd_nolock** , sırasıyla **_getdcwd** ve **_wgetdcwd** aynıdır, ancak diğer iş parçacıkları tarafından girişim tarafından korunmazlar. Diğer iş parçacıklarını kilitleme yükünü sunmadığından daha hızlı olabilir. Bu işlevleri yalnızca, tek iş parçacıklı uygulamalar gibi iş parçacığı güvenli bağlamlarda veya çağırma kapsamının iş parçacığı yalıtımını zaten işlediği yerde kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tgetdcwd_nolock**|**_getdcwd_nolock**|**_getdcwd_nolock**|**_wgetdcwd_nolock**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_getdcwd_nolock**|\<direct.h>|
|**_wgetdcwd_nolock**|\<direct.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dizin denetimi](../../c-runtime-library/directory-control.md)<br/>
[_chdir, _wchdir](chdir-wchdir.md)<br/>
[_getcwd, _wgetcwd](getcwd-wgetcwd.md)<br/>
[_getdrive](getdrive.md)<br/>
[_mkdir, _wmkdir](mkdir-wmkdir.md)<br/>
[_rmdir, _wrmdir](rmdir-wrmdir.md)<br/>
