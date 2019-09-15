---
title: _get_timezone
ms.date: 11/04/2016
api_name:
- _get_timezone
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
- _get_timezone
- get_timezone
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
ms.openlocfilehash: cf77ca21383bcae6919b6c1d00b99c082ef99919
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70955631"
---
# <a name="_get_timezone"></a>_get_timezone

Eşgüdümlü Evrensel Saat (UTC) ve yerel saat arasındaki farkı saniye cinsinden alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_timezone(
    long* seconds
);
```

### <a name="parameters"></a>Parametreler

*saniyeden*<br/>
UTC ve yerel saat arasındaki saniye cinsinden fark.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır veya bir hata oluşursa **errno** değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_timezone** işlevi UTC ve yerel saat arasındaki farkı saniye cinsinden bir tamsayı olarak alır. Varsayılan değer, Pasifik standart saati için 28.800 saniyedir (UTC 'nin arkasında sekiz saat).

*Saniyeler* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlev **errno** ' ı **EINVAL** olarak ayarlar ve **EINVAL**döndürür.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_timezone**|\<Time. h >|

Daha fazla bilgi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_tzname](get-tzname.md)<br/>
