---
title: _get_daylight
ms.date: 4/2/2020
api_name:
- __daylight
- _get_daylight
- _o___daylight
- _o__get_daylight
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
- get_daylight
- _get_daylight
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
ms.openlocfilehash: 0abab77b1429b263c7e5d84a6d395f0411ebf8a4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345311"
---
# <a name="_get_daylight"></a>_get_daylight

Gün ışığından yararlanma saatini saatler içinde dengeler.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_daylight( int* hours );
```

### <a name="parameters"></a>Parametreler

*Saat*<br/>
Gün ışığından yararlanma saatinde ofset.

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluşursa başarılı veya **bir errno** değeri sıfır.

## <a name="remarks"></a>Açıklamalar

**_get_daylight** işlevi gün ışığından yararlanma saatindeki saat sayısını tamsayı olarak alır. Gün ışığından yararlanma saati etkinse, varsayılan mahsup bir saattir (ancak birkaç bölge iki saatlik bir mahsup gözlemlemektedir).

*Saatler* **NULL**ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlev **EINVAL için errno** ayarlar ve **EINVAL** döndürür. **EINVAL**

Makro **_daylight** veya __daylight amortismana **işlevi**yerine bu işlevi kullanmanızı öneririz.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_daylight**|\<time.h>|

Daha fazla bilgi için [Uyumluluk'a](../../c-runtime-library/compatibility.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
