---
title: _get_daylight
ms.date: 11/04/2016
api_name:
- __daylight
- _get_daylight
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
- get_daylight
- _get_daylight
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
ms.openlocfilehash: 9f63d3baa1e9411039d1482b4cbfbf4bce4e9872
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70956048"
---
# <a name="_get_daylight"></a>_get_daylight

Gün ışığından yararlanma saati farkını saat olarak alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_daylight( int* hours );
```

### <a name="parameters"></a>Parametreler

*saatlerinin*<br/>
Gün ışığından yararlanma saatine göre saat cinsinden fark.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır veya bir hata oluşursa **errno** değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_günışığı** işlevi, gün ışığından yararlanma saatine göre saat sayısını tamsayı olarak alır. Gün ışığından yararlanma saati etkin ise, varsayılan konum bir saattir (birkaç bölge iki saatlik bir sapmayı gözlemlese de).

*Saatler* **null**ise, geçersiz parametre işleyicisi [parametre doğrulamada](../../c-runtime-library/parameter-validation.md)açıklandığı şekilde çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL**döndürür.

Bu işlevi makro **_yaz** veya kullanım dışı **__Yaz**işlevi yerine kullanmanızı öneririz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_daylight**|\<Time. h >|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
