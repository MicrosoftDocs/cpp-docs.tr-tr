---
title: _CrtGetAllocHook
ms.date: 11/04/2016
apiname:
- _CrtGetAllocHook
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
- CrtGetAllocHook
- _CrtGetAllocHook
helpviewer_keywords:
- _CrtGetAllocHook function
- CrtGetAllocHook function
ms.assetid: 036acf7c-547a-4b3f-a636-80451070d7ed
ms.openlocfilehash: b49c4cfc820a925187d0ea4d1562965295bea817
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50514965"
---
# <a name="crtgetallochook"></a>_CrtGetAllocHook

C çalışma zamanı hata ayıklama bellek ayırma işlemine (yalnızca hata ayıklama sürümü) takma için geçerli istemci tanımlı ayırma işlevi alır.

## <a name="syntax"></a>Sözdizimi

```C
_CRT_ALLOC_HOOK _CrtGetAllocHook( void );
```

## <a name="return-value"></a>Dönüş Değeri

Şu anda tanımlı ayırma kanca işlevini döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtGetAllocHook** C çalışma zamanı hata ayıklama kitaplığı bellek ayırma işlemi için geçerli uygulama istemci tanımlı kanca işlevini alır.

Kanca özellikli diğer çalışma zamanı işlevleri ve kendi istemci tarafından tanımlanan yazma hakkında daha fazla bilgi için kanca işlevleri, bkz: [hata ayıklama kanca işlevi yazma](/visualstudio/debugger/debug-hook-function-writing).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_CrtGetAllocHook**|\<crtdbg.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

Hata ayıklama sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md) yalnızca.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_CrtSetAllocHook](crtsetallochook.md)<br/>
