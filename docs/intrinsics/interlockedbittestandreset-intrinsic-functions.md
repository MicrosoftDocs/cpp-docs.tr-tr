---
description: 'Hakkında daha fazla bilgi edinin: _interlockedbittestandreset iç işlevler'
title: _interlockedbittestandreset iç işlevler
ms.date: 09/02/2019
f1_keywords:
- _interlockedbittestandreset_rel
- _interlockedbittestandreset64
- _interlockedbittestandreset64_acq
- _interlockedbittestandreset64_nf
- _interlockedbittestandreset64_rel
- _interlockedbittestandreset64_HLERelease
- _interlockedbittestandreset_HLERelease
- _interlockedbittestandreset_HLEAcquire
- _interlockedbittestandreset_acq
- _interlockedbittestandreset_cpp
- _interlockedbittestandreset_nf
- _interlockedbittestandreset64_cpp
- _interlockedbittestandreset64_HLEAcquire
- _interlockedbittestandreset
helpviewer_keywords:
- lock_btr instruction
- _interlockedbittestandreset64 intrinsic
- _interlockedbittestandreset intrinsic
ms.assetid: 9bbb1442-f2e9-4dc2-b0da-97f3de3493b9
ms.openlocfilehash: 10bd636fb25d0f4025530f0bd7a8c3f877cc1556
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168221"
---
# <a name="_interlockedbittestandreset-intrinsic-functions"></a>_interlockedbittestandreset iç işlevler

**Microsoft'a Özgü**

Adresin bitini sıfıra ayarlamak için bir yönerge oluşturur `b` `a` ve özgün değerini döndürür.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char _interlockedbittestandreset(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_acq(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_HLEAcquire(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_HLERelease(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_nf(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_rel(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset64(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_acq(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_nf(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_rel(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_HLERelease(
   __int64 *a,
   __int64 b
);
```

### <a name="parameters"></a>Parametreler

*a*\
'ndaki İncelenecek bellek işaretçisi.

*kenarı*\
'ndaki Sınanacak bit konumu.

## <a name="return-value"></a>Döndürülen değer

Tarafından belirtilen konumdaki bitin özgün değeri `b` .

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_interlockedbittestandreset`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM, ARM64|\<intrin.h>|
|`_interlockedbittestandreset64_acq`, `_interlockedbittestandreset64_nf`, `_interlockedbittestandreset64_rel`|ARM64|\<intrin.h>|
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86, x64|\<immintrin.h>|
|`_interlockedbittestandreset64`|x64, ARM64|\<intrin.h>|
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|x64|\<immintrin.h>|

## <a name="remarks"></a>Açıklamalar

X86 ve x64 işlemcilerde bu iç bilgiler, `lock btr` bir atomik işlemde belirtilen bit ' i okuyup ayarlayan yönergesini kullanır.

ARM işlemcilerde, `_acq` `_rel` önemli bir bölümün başındaki ve sonundaki gibi alma ve bırakma semantiği için iç bilgileri ve sonekleri kullanın. `_nf`("Sınır yok") son ek olan ARM iç bilgileri bellek engeli olarak davranmaz.

Donanım kilidi (HLE) talimatlarını destekleyen Intel işlemcilerde, `_HLEAcquire` ve `_HLERelease` son ekler, donanımda bir kilit yazma adımını ortadan kaldırarak işlemciyi hızlandıran bir ipucu içerir. Bu iç bilgiler HLE 'yı desteklemeyen işlemcilerde çağrılırsa, ipucu yok sayılır.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
