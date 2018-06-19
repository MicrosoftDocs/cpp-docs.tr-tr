---
title: _CrtMemDumpStatistics | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtMemDumpStatistics
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
apitype: DLLExport
f1_keywords:
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 688cef94721ac7ea3a36ccd375185b922b23a15f
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32395610"
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics

Kullanıcı tarafından okunabilir bir biçimde (yalnızca hata ayıklama sürümü) belirtilen yığın durumu için hata ayıklama üstbilgiyi dökümünü yapar.

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*Durum* yığın durumu dökümü işaretçi.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDumpStatistics** işlevi öbeğe kullanıcı okunabilir bir form, belirtilen bir durum için hata ayıklama üst bilgileri dökümünü yapar. Döküm istatistikleri ayırmaları izlemek ve bellek sorunları algılamak için uygulama tarafından kullanılabilir. Bellek durumu belirli yığın durumu veya iki durumlu arasındaki farkı içerebilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtMemDumpStatistics** ön işleme sırasında kaldırılır.

*Durumu* parametresi için bir işaretçi olmalıdır bir **_CrtMemState** tarafından doldurulmuştur yapısı [_CrtMemCheckpoint](crtmemcheckpoint.md) veya tarafından döndürülen [_ CrtMemDifference](crtmemdifference.md) önce **_CrtMemDumpStatistics** olarak adlandırılır. Varsa *durumu* olan **NULL**, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa **errno** ayarlanır **EINVAL** ve hiçbir işlem yapılmadı. Daha fazla bilgi için bkz: [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Yığın durumu İşlevler hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılmış, başlatılmış ve temel yığın hata ayıklama sürümü yönetilen hakkında daha fazla bilgi için bkz: [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h >|\<errno.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
