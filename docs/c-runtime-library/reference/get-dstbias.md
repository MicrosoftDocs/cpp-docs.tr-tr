---
title: _get_dstbias
ms.date: 11/04/2016
api_name:
- _get_dstbias
- __dstbias
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
ms.openlocfilehash: a48cc4fe35a1bbd18342750571214ed0977cf3ee
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955945"
---
# <a name="_get_dstbias"></a>_get_dstbias

Gün ışığından yararlanma saati sapmasını saniye cinsinden alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Parametreler

*saniyeden*<br/>
Gün ışığından yararlanma zamanının saniye cinsinden değeri.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır veya bir hata oluşursa **errno** değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_dstsapma** işlevi, gün ışığından yararlanma saatine saniye sayısını tamsayı olarak alır. Gün ışığından yararlanma saati etkin ise, varsayılan değer 3600 saniyedir ve bu da bir saatteki saniye sayısıdır (birkaç bölge iki saatlik bir sapmayı gözlemlebilse de).

*Saniyeler* **null**ise, [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı şekilde geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL**döndürür.

Bu işlevi, makro **_dstsapma** veya kullanım dışı işlev **__dstsapması**yerine kullanmanızı öneririz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_dstbias**|\<Time. h >|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
