---
title: _get_timezone | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- time zones
- get_timezone function
- _get_timezone function
ms.assetid: 30ab0838-0ae9-4a2f-bfe6-a49ee443b21e
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d878d97b365fb2f3c5e897fec3989f336a3d67c
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="gettimezone"></a>_get_timezone

Saniye cinsinden Eşgüdümlü Evrensel Saat (UTC) ve yerel saat arasındaki farkı alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_timezone(
    long* seconds
);
```

### <a name="parameters"></a>Parametreler

*Saniye*<br/>
UTC ve yerel saat arasındaki farkı saniye cinsinden.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ya da bir sıfır **errno** bir hata oluşursa değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_timezone** işlevi fark saniye cinsinden UTC ve yerel saat arasında bir tamsayı olarak alır. Varsayılan değer 28.800, Pasifik Standart Saati (UTC arkasında sekiz saat) için saniyedir.

Varsa *saniye* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_timezone**|\<time.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_daylight](get-daylight.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_tzname](get-tzname.md)<br/>
