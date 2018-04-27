---
title: _get_daylight | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- __daylight
- _get_daylight
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
- get_daylight
- _get_daylight
dev_langs:
- C++
helpviewer_keywords:
- get_daylight function
- daylight saving time offset
- _get_daylight function
ms.assetid: f85a6ba3-e187-4ca7-aed7-ffc694c8ac4c
caps.latest.revision: 17
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9df76bb56ace99f4242c31d843274cc30628eccf
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="getdaylight"></a>_get_daylight

Saat gün ışığından yararlanma saati uzaklığı alır.

## <a name="syntax"></a>Sözdizimi

```C
error_t _get_daylight( int* hours );
```

### <a name="parameters"></a>Parametreler

*Saatleri*<br/>
Saat gün ışığından yararlanma saati olarak uzaklığı.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa ya da bir sıfır **errno** bir hata oluşursa değeri.

## <a name="remarks"></a>Açıklamalar

**_Get_daylight** işlevi yaz saati bir tamsayı olarak saat sayısını alır. Yaz Saati etkinse, (birkaç bölgeler iki saatlik uzaklığı gözlemlemek rağmen) varsayılan bir saat uzaklığı.

Varsa *saatleri* olan **NULL**, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev devam etmek için yürütülmesine izin veriliyorsa, ayarlar **errno** için **EINVAL** ve döndürür **EINVAL**.

Makro yerine bu işlev kullanmanızı öneririz **_daylight** veya kullanım dışı işlev **__daylight**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_get_daylight**|\<time.h >|

Daha fazla bilgi için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Zaman Yönetimi](../../c-runtime-library/time-management.md)<br/>
[errno, _doserrno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)<br/>
[_get_dstbias](get-dstbias.md)<br/>
[_get_timezone](get-timezone.md)<br/>
[_get_tzname](get-tzname.md)<br/>
