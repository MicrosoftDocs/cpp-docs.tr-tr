---
title: _CrtGetReportHook
ms.date: 11/04/2016
apiname:
- _CrtGetReportHook
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
- CrtGetReportHook
- _CrtGetReportHook
helpviewer_keywords:
- CrtGetReportHook function
- _CrtGetReportHook function
ms.assetid: 922758ed-7edd-4359-9c92-0535192dc11a
ms.openlocfilehash: 0b8b666093807c95312d4328ca9b3043ad1e09df
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536766"
---
# <a name="crtgetreporthook"></a>_CrtGetReportHook

C çalışma zamanı hata ayıklama işlemi (yalnızca hata ayıklama sürümü) raporlama için içine takma için istemci tanımlı raporlama işlevi alır.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_REPORT_HOOK _CrtGetReportHook( void );
```

## <a name="return-value"></a>Dönüş Değeri

Geçerli istemci tanımlı raporlama işlevi döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtGetReportHook** raporlama sürecini C çalışma zamanı hata ayıklama kitaplığı için geçerli raporlama işlevi almak bir uygulama sağlar.

Kanca özellikli diğer çalışma zamanı işlevleri ve kendi istemci tarafından tanımlanan yazma hakkında daha fazla bilgi için kanca işlevleri, bkz: [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtGetReportHook**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="example"></a>Örnek

Nasıl kullanılacağını gösteren bir örnek **_CrtSetReportHook**, bkz: [rapor](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/report).

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetReportHook](crtsetreporthook.md)<br/>
