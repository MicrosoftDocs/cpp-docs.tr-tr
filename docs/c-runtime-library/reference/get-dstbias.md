---
title: _get_dstbias | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- __dstbias
- daylight saving time offset
- get_dstbias function
- _get_dstbias function
ms.assetid: e751358c-1ecc-411b-ae2c-81b2ec54ea45
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 82e334c6fcb282bebb003992219f6cf215ab7437
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32397772"
---
# <a name="getdstbias"></a>_get_dstbias

Yaz Saati farkı saniye cinsinden alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_dstbias( int* seconds );
```

### <a name="parameters"></a>Parametreler

*Saniye*<br/>
Yaz Saati saniye cinsinden uzaklık.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ya da bir sıfır **errno** bir hata oluşursa değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_dstbias** işlevi bir tamsayı olarak gün ışığından yararlanma saati saniye sayısını alır. Yaz Saati etkinse, varsayılan 3600 saniye (birkaç bölgeler iki saatlik uzaklığı gözlemlemek rağmen) bir saat içinde saniye sayısını olduğu uzaklığı.

Varsa *saniye* olan **NULL**, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

Makro yerine bu işlev kullanmanızı öneririz **_dstbias** veya kullanım dışı işlev **__dstbias**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_dstbias**|\<time.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
