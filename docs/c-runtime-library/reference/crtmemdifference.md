---
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
ms.openlocfilehash: 51bfa014d54f55843fcb112f318f143774abf8f3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70938705"
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
İki bellek durumu (döndürülen) arasındaki farkları depolamak için kullanılan bir **_Crtmemstate** yapısına yönelik işaretçi.

*Eski durum*<br/>
Önceki bir bellek durumuna yönelik işaretçi ( **_Crtmemstate** yapısı).

*Yeni durum*<br/>
Daha sonraki bir bellek durumuna yönelik işaretçi ( **_Crtmemstate** yapısı).

## <a name="return-value"></a>Dönüş Değeri

Bellek durumları önemli ölçüde farklıysa **_Crtmemdifference** true değerini döndürür. Aksi takdirde, işlev FALSE döndürür.

## <a name="remarks"></a>Açıklamalar

**_Crtmemdifference** Işlevi, *OldState* ve *NewState* 'i karşılaştırır ve daha sonra, bellek sızıntılarını ve diğer bellek sorunlarını algılamak için uygulama tarafından kullanılabilen *stateDiff*ile aralarındaki farkları depolar. [_Hata ayıklama](../../c-runtime-library/debug.md) tanımlanmadığında, **_Crtmemdifference** çağrıları ön işleme sırasında kaldırılır.

*NewState* ve *OldState* her biri Crtdbg. h içinde tanımlanan bir **_CrtMemState** yapısına, **_Crtmemdifference**çağrılmadan önce [_CrtMemCheckpoint](crtmemcheckpoint.md) tarafından doldurulmuş geçerli bir işaretçi olmalıdır. *stateDiff* , **_Crtmemstate** yapısının önceden ayrılmış bir örneğine yönelik bir işaretçi olmalıdır. *StateDiff*, *NewState*veya *OldState* **null**ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) **EINVAL** olarak ayarlanır ve işlev FALSE döndürür.

**_Crtmemdifference** , *OldState* 'Teki blokların **_CrtMemState** alan değerlerini *NewState* 'dakilerle karşılaştırır ve sonucu *stateDiff*içinde depolar. Ayrılmış blok türlerinin sayısı veya her tür için ayrılan toplam blok sayısı iki bellek durumu arasında farklılık gösterdiğinde, durumların önemli ölçüde farklı olduğu söylenir. İki durum için bir kerede şimdiye kadar ayrılan en büyük miktar arasındaki fark ve iki durumun toplam ayırmaları arasındaki fark, *stateDiff*'da da depolanır.

Varsayılan olarak, iç C çalışma zamanı blokları ( **_CRT_BLOCK**) bellek durumu işlemlerine dahil edilmez. [_Crtsetdbgflag](crtsetdbgflag.md) işlevi, sızıntı algılamasında ve diğer bellek durumu işlemlerinde bu blokları dahil etmek Için **_Crtdbgflag** **_CRTDBG_CHECK_CRT_DF** bitini açmak üzere kullanılabilir. Serbest bırakılan bellek blokları ( **_Free_block**), **_Crtmemdifference** 'in true döndürmesine neden olmaz.

Yığın durumu işlevleri ve **_Crtmemstate** yapısı hakkında daha fazla bilgi için bkz. [yığın durum raporlama işlevleri](/visualstudio/debugger/crt-debug-heap-details). Bellek bloklarının taban yığının hata ayıklama sürümünde nasıl ayrıldığı, başlatıldığı ve yönetildiği hakkında bilgi için bkz. [CRT hata ayıklama yığını ayrıntıları](/visualstudio/debugger/crt-debug-heap-details).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<Crtdbg. h >|\<errno. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

**Kütüphaneler** Yalnızca [CRT kitaplığı özelliklerinin](../../c-runtime-library/crt-library-features.md) hatalarını ayıklayın.

## <a name="see-also"></a>Ayrıca bkz.

[Hata Ayıklama Yordamları](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
