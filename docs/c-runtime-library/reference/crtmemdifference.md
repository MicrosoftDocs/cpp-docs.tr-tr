---
description: 'Hakkında daha fazla bilgi edinin: _CrtMemDifference'
title: _CrtMemDifference
ms.date: 11/04/2016
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
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: 076cead5f60df457171bbcdf2fd8690f0361870b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319657"
---
# <a name="_crtmemdifference"></a>_CrtMemDifference

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

*stateDiff*<br/>
İki bellek durumu (döndürülen) arasındaki farkları depolamak için kullanılan **_CrtMemState** yapısına yönelik işaretçi.

*Eski durum*<br/>
Daha önceki bir bellek durumuna yönelik işaretçi (**_CrtMemState** yapısı).

*Yeni durum*<br/>
Daha sonraki bir bellek durumuna yönelik işaretçi (**_CrtMemState** yapısı).

## <a name="return-value"></a>Dönüş Değeri

Bellek durumları önemli ölçüde farklıysa, **_CRTMEMDIFFERENCE** true değerini döndürür. Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_CrtMemDifference** Işlevi *OldState* ve *NewState* ' i karşılaştırır ve farklarını *stateDiff* bölümünde depolar ve bu sayede, bellek sızıntılarını ve diğer bellek sorunlarını tespit etmek için uygulama tarafından kullanılabilir. [_DEBUG](../../c-runtime-library/debug.md) tanımlı olmadığında, **_CrtMemDifference** çağrıları ön işleme sırasında kaldırılır.

*NewState* ve *OldState* her birinin, [_CrtMemCheckpoint](crtmemcheckpoint.md) **_CrtMemDifference** çağrılmadan önce, Crtdbg. h içinde tanımlanan **_CrtMemState** yapısına yönelik geçerli bir işaretçi olması gerekir. *stateDiff* , **_CrtMemState** yapısının daha önceden ayrılmış bir örneğine yönelik bir işaretçi olmalıdır. *StateDiff*, *NewState* veya *OldState* **null** ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, [errno, _doserrno, _sys_errlist ve _Sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **EINVAL** olarak ayarlanır ve işlev FALSE döndürür.

**_CrtMemDifference** , *OldState* 'teki blokların **_CrtMemState** alan değerlerini *NewState* 'dakilerle karşılaştırır ve sonucu *stateDiff* içinde depolar. Ayrılmış blok türlerinin sayısı veya her tür için ayrılan toplam blok sayısı iki bellek durumu arasında farklılık gösterdiğinde, durumların önemli ölçüde farklı olduğu söylenir. İki durum için bir kerede şimdiye kadar ayrılan en büyük miktar arasındaki fark ve iki durumun toplam ayırmaları arasındaki fark, *stateDiff*'da da depolanır.

Varsayılan olarak, iç C çalışma zamanı blokları (**_CRT_BLOCK**) bellek durumu işlemlerine dahil edilmez. [_CrtSetDbgFlag](crtsetdbgflag.md) işlevi, bu blokları sızıntı algılamasına ve diğer bellek durumu işlemlerine dahil etmek için **_crtDbgFlag** **_CRTDBG_CHECK_CRT_DF** bitini açmak üzere kullanılabilir. Serbest bırakılan bellek blokları (**_free_block**) **_CrtMemDifference** true döndürmesine neden olmaz.

Yığın durumu işlevleri ve **_CrtMemState** yapısı hakkında daha fazla bilgi için bkz. [yığın durumu raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kitaplıklar:** Yalnızca [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md) hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata ayıklama yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
