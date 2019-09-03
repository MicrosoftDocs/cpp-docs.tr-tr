---
title: _InterlockedOr iç işlevleri
ms.date: 09/02/2019
f1_keywords:
- _InterlockedOr8_nf
- _InterlockedOr_HLEAcquire
- _InterlockedOr16_nf
- _InterlockedOr64
- _InterlockedOr8_np
- _InterlockedOr64_cpp
- _InterlockedOr8_acq
- _InterlockedOr_nf
- _InterlockedOr64_acq
- _InterlockedOr_np
- _InterlockedOr8
- _InterlockedOr
- _InterlockedOr64_np
- _InterlockedOr_acq
- _InterlockedOr64_HLERelease
- _InterlockedOr16_np
- _InterlockedOr_cpp
- _InterlockedOr8_rel
- _InterlockedOr64_rel
- _InterlockedOr16_acq
- _InterlockedOr_rel
- _InterlockedOr16_rel
- _InterlockedOr_HLERelease
- _InterlockedOr64_HLEAcquire
- _InterlockedOr16
- _InterlockedOr64_nf
helpviewer_keywords:
- _InterlockedOr_acq intrinsic
- InterlockedOr64 intrinsic
- _InterlockedOr_nf intrinsic
- _InterlockedOr intrinsic
- _InterlockedOr64_HLERelease intrinsic
- _InterlockedOr8_rel intrinsic
- _InterlockedOr8_np intrinsic
- _InterlockedOr64_nf intrinsic
- _InterlockedOr_HLERelease intrinsic
- _InterlockedOr16_np intrinsic
- InterlockedOr intrinsic
- _InterlockedOr8_nf intrinsic
- _InterlockedOr16_nf intrinsic
- _InterlockedOr8_acq intrinsic
- _InterlockedOr64 intrinsic
- _InterlockedOr16 intrinsic
- _InterlockedOr64_acq intrinsic
- _InterlockedOr64_HLEAcquire intrinsic
- _InterlockedOr_np intrinsic
- _InterlockedOr64_rel intrinsic
- _InterlockedOr64_np intrinsic
- _InterlockedOr_rel intrinsic
- _InterlockedOr8 intrinsic
- _InterlockedOr16_acq intrinsic
- _InterlockedOr16_rel intrinsic
- _InterlockedOr_HLEAcquire intrinsic
ms.assetid: 5f265240-7af8-44b7-b952-19f3a9c56186
ms.openlocfilehash: baad724c85d2d8fb981ec7836d7a46152000fae3
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217591"
---
# <a name="_interlockedor-intrinsic-functions"></a>_InterlockedOr iç işlevleri

**Microsoft 'a özgü**

Birden çok iş parçacığı tarafından paylaşılan bir değişkende atomik bit düzeyinde veya işlemi gerçekleştirin.

## <a name="syntax"></a>Sözdizimi

```C
long _InterlockedOr(
   long volatile * Value,
   long Mask
);
long _InterlockedOr_acq(
   long volatile * Value,
   long Mask
);
long _InterlockedOr_HLEAcquire(
   long volatile * Value,
   long Mask
);
long _InterlockedOr_HLERelease(
   long volatile * Value,
   long Mask
);
long _InterlockedOr_nf(
   long volatile * Value,
   long Mask
);
long _InterlockedOr_np(
   long volatile * Value,
   long Mask
);
long _InterlockedOr_rel(
   long volatile * Value,
   long Mask
);
char _InterlockedOr8(
   char volatile * Value,
   long Mask
);
char _InterlockedOr8_acq(
   char volatile * Value,
   char Mask
);
char _InterlockedOr8_nf(
   char volatile * Value,
   char Mask
);
char _InterlockedOr8_np(
   char volatile * Value,
   char Mask
);
char _InterlockedOr8_rel(
   char volatile * Value,
   char Mask
);
short _InterlockedOr16(
   short volatile * Value,
   short Mask
);
short _InterlockedOr16_acq(
   short volatile * Value,
   short Mask
);
short _InterlockedOr16_nf(
   short volatile * Value,
   short Mask
);
short _InterlockedOr16_np(
   short volatile * Value,
   short Mask
);
short _InterlockedOr16_rel(
   short volatile * Value,
   short Mask
);
__int64 _InterlockedOr64(
   __int64 volatile * Value,
   __int64 Mask
);
__int64 _InterlockedOr64_acq(
   __int64 volatile * Value,
   __int64 Mask
);
__int64 _InterlockedOr64_HLEAcquire(
   __int64 volatile * Value,
   __int64 Mask
);
__int64 _InterlockedOr64_HLERelease(
   __int64 volatile * Value,
   __int64 Mask
);
__int64 _InterlockedOr64_nf(
   __int64 volatile * Value,
   __int64 Mask
);
__int64 _InterlockedOr64_np(
   __int64 volatile * Value,
   __int64 Mask
);
__int64 _InterlockedOr64_rel(
   __int64 volatile * Value,
   __int64 Mask
);
```

### <a name="parameters"></a>Parametreler

*Deeri*\
[in, out] Sonuçla değiştirilmeleri için ilk işlenenin işaretçisi.

*Maskesi*\
'ndaki İkinci işlenen.

## <a name="return-value"></a>Dönüş değeri

İlk parametre tarafından işaret edilen özgün değer.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_InterlockedOr`, `_InterlockedOr8`, `_InterlockedOr16`|x86, ARM, x64, ARM64|\<Intrin. h >|
|`_InterlockedOr64`|ARM, x64, ARM64|\<Intrin. h >|
|`_InterlockedOr_acq`, `_InterlockedOr_nf`, `_InterlockedOr_rel`, `_InterlockedOr8_acq`, `_InterlockedOr8_nf`, `_InterlockedOr8_rel`, `_InterlockedOr16_acq`, `_InterlockedOr16_nf`, `_InterlockedOr16_rel`, `_InterlockedOr64_acq`, `_InterlockedOr64_nf`, `_InterlockedOr64_rel`|ARM, ARM64|\<Intrin. h >|
|`_InterlockedOr_np`, `_InterlockedOr8_np`, `_InterlockedOr16_np`, `_InterlockedOr64_np`|X64|\<Intrin. h >|
|`_InterlockedOr_HLEAcquire`, `_InterlockedOr_HLERelease`|x86, x64|\<ımintrin. h >|
|`_InterlockedOr64_HLEAcquire`, `_InterlockedOr64_HLERelease`|X64|\<ımintrin. h >|

## <a name="remarks"></a>Açıklamalar

Her işlevin adındaki sayı, bağımsız değişkenlerin bit boyutunu belirtir.

ARM platformlarında, önemli bir bölümün başındaki ve `_acq` sonundaki `_rel` gibi alma ve bırakma semantiklerine ihtiyacınız varsa, iç bilgileri ve son eklerini kullanın. `_nf` ("Sınır yok") son ek olan ARM iç bilgileri bellek engeli olarak davranmaz.

`_np` ("Önceden getirme yok") sonekine sahip iç bilgiler, olası bir önceden getirme işleminin derleyici tarafından eklenmesini engeller.

Donanım kilidi (HLE) yönergelerini destekleyen Intel platformlarında, `_HLEAcquire` ve `_HLERelease` son ekler, donanımda bir kilit yazma adımını ortadan kaldırarak işlemciyi hızlandıran bir ipucu içerir. Bu iç bilgiler HLE 'yı desteklemeyen platformlarda çağrılırsa, ipucu yok sayılır.

## <a name="example"></a>Örnek

```cpp
// _InterlockedOr.cpp
#include <stdio.h>
#include <intrin.h>

#pragma intrinsic(_InterlockedOr)

int main()
{
        long data1 = 0xFF00FF00;
        long data2 = 0x00FFFF00;
        long retval;
        retval = _InterlockedOr(&data1, data2);
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);
}
```

```Output
0xffffff00 0xffff00 0xff00ff00
```

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
