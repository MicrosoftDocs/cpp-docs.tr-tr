---
title: _get_dstbias
ms.date: 4/2/2020
api_name:
- _get_dstbias
- __dstbias
- _o___dstbias
- _o__get_dstbias
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
- api-ms-win-crt-time-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 969b6d2dfd83a1a136fdfb3d17f8f843337b792c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345223"
---
# <a name="_get_dstbias"></a>_get_dstbias

Gün ışığından yararlanma saatini saniyeler içinde alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Parametreler

*Saniye*<br/>
Gün ışığından yararlanma saati saniye içinde ofset.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa başarılı veya **bir errno** değeri sıfır.

## <a name="remarks"></a>Açıklamalar

**_get_dstbias** işlevi gün ışığından yararlanma saatindesaniye sayısını tamsayı olarak alır. Gün ışığından yararlanma saati etkinse, varsayılan ofset 3600 saniyedir, bu da bir saat içinde saniye sayısıdır (ancak birkaç bölge iki saatlik bir mahsup gözlemlemektedir).

*Saniye* **NULL**ise, geçersiz parametre işleyicisi [Parametre Doğrulama](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

Makro **_dstbias** veya __dstbias amortismana __dstbias **işlevi**yerine bu işlevi kullanmanızı öneririz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_dstbias**|\<time.h>|

Daha fazla bilgi için [Uyumluluk'a](../../c-runtime-library/compatibility.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
