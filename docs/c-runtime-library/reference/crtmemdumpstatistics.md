---
title: _CrtMemDumpStatistics
ms.date: 11/04/2016
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
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
ms.openlocfilehash: 66eb58b65f3fa20e01ad16d68f3fe1baafd8cd04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605133"
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics

Bir kullanıcı tarafından okunabilir bir biçimde (yalnızca hata ayıklama sürümü) belirtilen yığın durumda hata ayıklama başlık bilgilerini dökümünü yapar.

## <a name="syntax"></a>Sözdizimi

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>Parametreler

*durumu*<br/>
Yığın Dökümü durumuna yönelik işaretçi.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDumpStatistics** işlevi hata ayıklama üst bilgi bilgileri için kullanıcı tarafından okunabilir bir biçimde yığının belirtilen bir durum dökümünü yapar. Döküm istatistikleri ayırmaları İzle ve bellek sorunlarını algılamak için uygulama tarafından kullanılabilir. Bellek durumu, belirli bir yığın durumu veya iki durum arasındaki farkı içerebilir. Zaman [_DEBUG](../../c-runtime-library/debug.md) tanımlı değil, çağrılar **_CrtMemDumpStatistics** ön işleme sırasında kaldırılır.

*Durumu* parametresi işaretçi olmalıdır bir **_CrtMemState** ile doldurulmuştur yapısı [_CrtMemCheckpoint](crtmemcheckpoint.md) veya tarafından döndürülen [_ CrtMemDifference](crtmemdifference.md) önce **_CrtMemDumpStatistics** çağrılır. Varsa *durumu* olduğu **NULL**, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve hiçbir işlem yapılmaz. Daha fazla bilgi için [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

Yığın durumu işlevleri hakkında daha fazla bilgi ve **_CrtMemState** yapısı için bkz: [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Nasıl bellek blokları ayrılan, başlatılır ve taban yığının hata ayıklama sürümünde yönetilen hakkında daha fazla bilgi için bkz. [CRT hata ayıklama öbeği ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üst bilgiler|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h >|\<errno.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** hata ayıklama sürümleri [CRT kitaplık özellikleri](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
