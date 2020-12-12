---
description: 'Hakkında daha fazla bilgi edinin: _CrtMemDumpStatistics'
title: _CrtMemDumpStatistics
ms.date: 11/04/2016
api_name:
- _CrtMemDumpStatistics
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
ms.openlocfilehash: 2f02c35ff61dc2bc5ac7e8dfbe921fa48731c2b3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319630"
---
# <a name="_crtmemdumpstatistics"></a>_CrtMemDumpStatistics

Belirtilen yığın durumu için hata ayıklama üst bilgisi bilgilerini Kullanıcı tarafından okunabilen bir biçimde döker (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumunda*<br/>
Döküm için yığın durumunun işaretçisi.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDumpStatistics** işlevi, yığın için belirtilen bir durum için hata ayıklama üst bilgisini Kullanıcı tarafından okunabilen bir biçimde döker. Döküm istatistikleri, uygulama tarafından ayırmaları izlemek ve bellek sorunlarını algılamak için kullanılabilir. Bellek durumu belirli bir yığın durumu veya iki durum arasındaki farkı içerebilir. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtMemDumpStatistics** çağrıları ön işleme sırasında kaldırılır.

*Durum* parametresi, [_CrtMemCheckpoint](crtmemcheckpoint.md) tarafından doldurulmuş veya **_CrtMemDumpStatistics** çağrılmadan önce [_CrtMemDifference](crtmemdifference.md) tarafından döndürülen **_CrtMemState** yapısına yönelik bir işaretçi olmalıdır. *Durum* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve hiçbir işlem yapılmaz. Daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Yığın durumu işlevleri ve **_CrtMemState** yapısı hakkında daha fazla bilgi için bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında daha fazla bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Yalnızca [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md) hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
