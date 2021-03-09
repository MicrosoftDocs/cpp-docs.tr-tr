---
title: _CrtMemDifference
description: 'Hakkında daha fazla bilgi edinin: _CrtMemDifference'
ms.date: 3/8/2021
api_name:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.openlocfilehash: 9a6a213df867f98bfb921abd940ba23297c5ffef
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514609"
---
# `_CrtMemDifference`

İki bellek durumunu karşılaştırır ve farklarını döndürür (yalnızca hata ayıklama sürümü).

## <a name="syntax"></a>Sözdizimi

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>Parametreler

*`stateDiff`*\
**`_CrtMemState`** İki bellek durumu (döndürülen) arasındaki farkları depolamak için kullanılan bir yapıya yönelik işaretçi.

*`oldState`*\
Önceki bir bellek durumuna ( **`_CrtMemState`** Yapı) yönelik işaretçi.

*`newState`*\
Daha sonraki bir bellek durumuna yönelik işaretçi ( **`_CrtMemState`** Yapı).

## <a name="return-value"></a>Dönüş Değeri

Bellek durumları önemli ölçüde farklıysa, **`_CrtMemDifference`** döndürür `TRUE` . Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**`_CrtMemDifference`** İşlevi ve üzerindeki *`oldState`* *`newState`* farklarını depolar ve bu sayede *`stateDiff`* , bellek sızıntılarını ve diğer bellek sorunlarını algılamak için uygulama tarafından kullanılabilir. [_DEBUG](../../c-runtime-library/debug.md) tanımlanmadığında, çağrıları **`_CrtMemDifference`** ön işleme sırasında kaldırılır.

*`newState`* ve, *`oldState`* **`_CrtMemState`** çağrılmadan önce tarafından doldurulmuş olan Crtdbg. h içinde tanımlanan bir yapıya geçerli bir işaretçi olmalıdır [`_CrtMemCheckpoint`](crtmemcheckpoint.md) **`_CrtMemDifference`** . *`stateDiff`* yapının önceden ayrılmış örneğine bir işaretçi olmalıdır **`_CrtMemState`** . *`stateDiff`*, *`newState`* Veya Ise, *`oldState`* **`NULL`** [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) olarak ayarlanır **`EINVAL`** ve işlev FALSE döndürür.

**`_CrtMemDifference`** içindeki **`_CrtMemState`** blokların alan değerlerini içinde *`oldState`* olanlarla karşılaştırır *`newState`* ve sonucu içinde depolar *`stateDiff`* . Ayrılmış blok türlerinin sayısı veya her tür için ayrılan toplam blok sayısı iki bellek durumu arasında farklılık gösterdiğinde, durumların önemli ölçüde farklı olduğu söylenir. İki durum için bir kerede şimdiye kadar ayrılan en büyük miktar arasındaki fark ve iki durumun toplam ayırmaları arasındaki fark içinde de depolanır *`stateDiff`* .

Varsayılan olarak, iç C çalışma zamanı blokları ( **`_CRT_BLOCK`** ) bellek durumu işlemlerine dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi, **`_CRTDBG_CHECK_CRT_DF`** **`_crtDbgFlag`** sızıntı algılamasında ve diğer bellek durumu işlemlerinde bu blokları dahil etmek için bit ' i etkinleştirmek üzere kullanılabilir. Serbest bırakılan bellek blokları ( **`_FREE_BLOCK`** ) **`_CrtMemDifference`** döndürülmemesine neden olmaz `TRUE` .

Yığın durumu işlevleri ve yapısı hakkında daha fazla bilgi için **`_CrtMemState`** bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**`_CrtMemDifference`**|`<crtdbg.h>`|`<errno.h>`|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Yalnızca [C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md) hata ayıklama sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)\
[`_crtDbgFlag`](../../c-runtime-library/crtdbgflag.md)\
