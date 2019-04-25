---
title: _get_timezone
ms.date: 11/04/2016
apiname:
- _get_timezone
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
- api-ms-win-crt-time-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _get_timezone
- get_timezone
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
ms.openlocfilehash: 26cf8114ab766bdb394d2db9ad5842622a447bd1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62287449"
---
# <a name="gettimezone"></a>_get_timezone

Eşgüdümlü Evrensel Saat (UTC) ve yerel saat arasındaki farkı saniye cinsinden alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_timezone(
    long* seconds
);
```

### <a name="parameters"></a>Parametreler

*saniye*<br/>
Yerel saat ile UTC arasındaki saniye farkı.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı olursa ya da bir **errno** bir hata oluşursa değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_timezone** işlevi farkı saniye cinsinden UTC ve yerel saat arasındaki bir tamsayı olarak alır. Pasifik Standart Saati (UTC arkasında sekiz saat) için 28.800 saniye cinsinden varsayılan değerdir.

Varsa *saniye* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_timezone**|\<TIME.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_tzname](get-tzname.md)<br/>
