---
description: 'Hakkında daha fazla bilgi edinin: _InterlockedExchangeAdd iç işlevler'
title: _InterlockedExchangeAdd iç işlevler
ms.date: 09/02/2019
f1_keywords:
- _InterlockedExchangeAdd64_nf
- _InterlockedExchangeAdd64_rel
- _InterlockedExchangeAdd16_rel
- _InterlockedExchangeAdd_acq
- _InterlockedExchangeAdd_nf
- _InterlockedExchangeAdd_rel
- _InterlockedExchangeAdd8_acq
- _InterlockedExchangeAdd16_nf
- _InterlockedExchangeAdd_acq_cpp
- _InterlockedExchangeAdd64_acq_cpp
- _InterlockedExchangeAdd16_acq
- _InterlockedExchangeAdd_HLERelease
- _InterlockedExchangeAdd64_cpp
- _InterlockedExchangeAdd64_HLERelease
- _InterlockedExchangeAdd64_acq
- _InterlockedExchangeAdd8
- _InterlockedExchangeAdd64
- _InterlockedExchangeAdd8_nf
- _InterlockedExchangeAdd16
- _InterlockedExchangeAdd64_rel_cpp
- _InterlockedExchangeAdd_cpp
- _InterlockedExchangeAdd8_rel
- _InterlockedExchangeAdd_HLEAcquire
- _InterlockedExchangeAdd64_HLEAcquire
- _InterlockedExchangeAdd
helpviewer_keywords:
- _InterlockedExchangeAdd8_nf intrinsic
- InterlockedExchangeAdd64_acq intrinsic
- _InterlockedExchangeAdd8_acq intrinsic
- _InterlockedExchangeAdd64 intrinsic
- _InterlockedExchangeAdd intrinsic
- _InterlockedExchangeAdd8_rel intrinsic
- _InterlockedExchangeAdd_acq intrinsic
- _InterlockedExchangeAdd_HLEAcquire intrinsic
- _InterlockedExchangeAdd8 intrinsic
- _InterlockedExchangeAdd_rel intrinsic
- _InterlockedExchangeAdd64_HLERelease intrinsic
- _InterlockedExchangeAdd64_nf intrinsic
- InterlockedExchangeAdd_rel intrinsic
- InterlockedExchangeAdd intrinsic
- _InterlockedExchangeAdd_nf intrinsic
- _InterlockedExchangeAdd16_rel intrinsic
- InterlockedExchangeAdd_acq intrinsic
- _InterlockedExchangeAdd64_HLEAcquire intrinsic
- _InterlockedExchangeAdd16 intrinsic
- _InterlockedExchangeAdd64_acq intrinsic
- InterlockedExchangeAdd64_rel intrinsic
- _InterlockedExchangeAdd16_acq intrinsic
- InterlockedExchangeAdd64 intrinsic
- _InterlockedExchangeAdd_HLERelease intrinsic
- _InterlockedExchangeAdd16_nf intrinsic
- _InterlockedExchangeAdd64_rel intrinsic
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
ms.openlocfilehash: fa1403889aec15ba8cdaae135db2b7563636c21e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168026"
---
# <a name="_interlockedexchangeadd-intrinsic-functions"></a>_InterlockedExchangeAdd iç işlevler

**Microsoft'a Özgü**

Win32 Windows SDK [_InterlockedExchangeAdd iç işlevler](../intrinsics/interlockedexchangeadd-intrinsic-functions.md) işlevi için derleyicinin iç desteğini sağlayın.

## <a name="syntax"></a>Sözdizimi

```C
long _InterlockedExchangeAdd(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_acq(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_rel(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_nf(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_HLEAcquire(
   long volatile * Addend,
   long Value
);
long _InterlockedExchangeAdd_HLERelease(
   long volatile * Addend,
   long Value
);
char _InterlockedExchangeAdd8(
   char volatile * Addend,
   char Value
);
char _InterlockedExchangeAdd8_acq(
   char volatile * Addend,
   char Value
);
char _InterlockedExchangeAdd8_rel(
   char volatile * Addend,
   char Value
);
char _InterlockedExchangeAdd8_nf(
   char volatile * Addend,
   char Value
);
short _InterlockedExchangeAdd16(
   short volatile * Addend,
   short Value
);
short _InterlockedExchangeAdd16_acq(
   short volatile * Addend,
   short Value
);
short _InterlockedExchangeAdd16_rel(
   short volatile * Addend,
   short Value
);
short _InterlockedExchangeAdd16_nf(
   short volatile * Addend,
   short Value
);
__int64 _InterlockedExchangeAdd64(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_acq(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_rel(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_nf(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_HLEAcquire(
   __int64 volatile * Addend,
   __int64 Value
);
__int64 _InterlockedExchangeAdd64_HLERelease(
   __int64 volatile * Addend,
   __int64 Value
);
```

### <a name="parameters"></a>Parametreler

*Doğrusal formülündeki toplanan*\
[in, out] Eklenecek değer; ekleme sonucuyla değiştirilmiştir.

*Deeri*\
'ndaki Eklenecek değer.

## <a name="return-value"></a>Döndürülen değer

Dönüş değeri, parametresi tarafından işaret edilen değişkenin başlangıç değeridir `Addend` .

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_InterlockedExchangeAdd`, `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedExchangeAdd64`|ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`,`_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM, ARM64|\<intrin.h>|
|`_InterlockedExchangeAdd_HLEAcquire`, `_InterlockedExchangeAdd_HLERelease`|x86, x64|\<immintrin.h>|
|`_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x64|\<immintrin.h>|

## <a name="remarks"></a>Açıklamalar

Üzerinde bulunan `_InterlockedExchangeAdd` veri türlerine göre farklılık gösteren çeşitli çeşitlemeler vardır ve işlemciye özgü alma veya yayınlama semantiği kullanılıp kullanılmayacağını belirtir.

`_InterlockedExchangeAdd`İşlev 32 bitlik tamsayı değerlerinde çalışırken, `_InterlockedExchangeAdd8` 8 bit tamsayı değerleri üzerinde çalışır, `_InterlockedExchangeAdd16` 16 bit tam sayı değerlerinde çalışır ve `_InterlockedExchangeAdd64` 64 bit tamsayı değerlerinde çalışır.

ARM platformlarında, `_acq` `_rel` önemli bir bölümün başındaki ve sonundaki gibi alma ve bırakma semantiklerine ihtiyacınız varsa, iç bilgileri ve son eklerini kullanın. `_nf`("Sınır olmayan") son ek olan iç bilgiler bellek engeli olarak davranmaz.

Donanım kilidi (HLE) yönergelerini destekleyen Intel platformlarında, `_HLEAcquire` ve `_HLERelease` son ekler, donanımda bir kilit yazma adımını ortadan kaldırarak işlemciyi hızlandıran bir ipucu içerir. Bu iç bilgiler HLE 'yı desteklemeyen platformlarda çağrılırsa, ipucu yok sayılır.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir. Bunlar, [/Oi](../build/reference/oi-generate-intrinsic-functions.md) veya [#pragma iç](../preprocessor/intrinsic.md) kullanıldığında bile iç olurlar. Bu iç yapıları üzerinde [#pragma işlevi](../preprocessor/function-c-cpp.md) kullanılamaz.

## <a name="example"></a>Örnek

Öğesinin nasıl kullanılacağına ilişkin bir örnek için `_InterlockedExchangeAdd` bkz. [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Lerimi](../cpp/keywords-cpp.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
