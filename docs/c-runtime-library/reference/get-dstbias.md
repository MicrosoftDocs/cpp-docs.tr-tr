---
title: _get_dstbias
ms.date: 11/04/2016
apiname:
- _get_dstbias
- __dstbias
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
- __dstbias
- _get_dstbias
- get_dstbias
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
ms.openlocfilehash: 61807f854dc9c2f7de6f0acd5bbf4668987ce49e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62332383"
---
# <a name="getdstbias"></a>_get_dstbias

Yaz Saati farkı saniye cinsinden alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Parametreler

*saniye*<br/>
Yaz Saati saniye cinsinden uzaklığı.

## <a name="return-value"></a>Dönüş Değeri

Sıfır başarılı olursa ya da bir **errno** bir hata oluşursa değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_dstbias** işlevi yaz saati bir tamsayı olarak saniye sayısını alır. Gün ışığından yararlanma etkinse, varsayılan uzaklık 3600 saniye (Bazı bölgelerde iki saat uzaklığı gözlemleyin rağmen) saniye cinsinden bir saat sayısı olduğu dayalıdır.

Varsa *saniye* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütme devam etmesine izin verilirse, bu işlev ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

Makro yerine bu işlevi kullanmanız önerilir **_dstbias** veya kullanım dışı işlevine **__dstbias**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_dstbias**|\<TIME.h >|

Daha fazla bilgi için [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
