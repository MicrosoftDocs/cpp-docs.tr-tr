---
description: 'Hakkında daha fazla bilgi edinin: _interlockedbittestandset iç işlevler'
title: _interlockedbittestandset iç işlevler
ms.date: 09/02/2019
f1_keywords:
- _interlockedbittestandset_cpp
- _interlockedbittestandset_HLEAcquire
- _interlockedbittestandset64
- _interlockedbittestandset64_acq
- _interlockedbittestandset64_nf
- _interlockedbittestandset64_rel
- _interlockedbittestandset
- _interlockedbittestandset_rel
- _interlockedbittestandset64_HLEAcquire
- _interlockedbittestandset_HLERelease
- _interlockedbittestandset_acq
- _interlockedbittestandset_nf
- _interlockedbittestandset64_cpp
- _interlockedbittestandset64_HLERelease
helpviewer_keywords:
- _interlockedbittestandset intrinsic
- _interlockedbittestandset64 intrinsic
- lock_bts instruction
ms.assetid: b1b7e334-53ea-48cf-ba60-5fa3ef51a1fc
ms.openlocfilehash: bc1ee5e70c5b892b7c98bb9cb03f75b3baeda268
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168208"
---
# <a name="_interlockedbittestandset-intrinsic-functions"></a>_interlockedbittestandset iç işlevler

**Microsoft'a Özgü**

Adresin bitini incelemek için bir yönerge oluşturun `b` `a` ve 1 olarak ayarlamadan önce geçerli değerini döndürün.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char _interlockedbittestandset(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_acq(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_HLEAcquire(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_HLERelease(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_nf(
   long *a,
   long b
);
unsigned char _interlockedbittestandset_rel(
   long *a,
   long b
);
unsigned char _interlockedbittestandset64(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_acq(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_nf(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_rel(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_HLERelease(
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

`b`Ayarlanmadan önceki konumdaki bit değeri.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_interlockedbittestandset`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_interlockedbittestandset_acq`, `_interlockedbittestandset_nf`, `_interlockedbittestandset_rel`|ARM, ARM64|\<intrin.h>|
|`_interlockedbittestandset64_acq`, `_interlockedbittestandset64_nf`, `_interlockedbittestandset64_rel`|ARM64|\<intrin.h>|
|`_interlockedbittestandset_HLEAcquire`, `_interlockedbittestandset_HLERelease`|x86, x64|\<immintrin.h>|
|`_interlockedbittestandset64`|x64, ARM64|\<intrin.h>|
|`_interlockedbittestandset64_HLEAcquire`, `_interlockedbittestandset64_HLERelease`|x64|\<immintrin.h>|

## <a name="remarks"></a>Açıklamalar

X86 ve x64 işlemcilerde bu iç bilgiler, `lock bts` belirtilen biti okumak ve 1 olarak ayarlamak için yönergesini kullanır. İşlem atomik.

ARM ve ARM64 işlemcilerde, `_acq` `_rel` önemli bir bölümün başındaki ve sonundaki gibi alma ve bırakma semantiğinin ve son eklerini kullanın. `_nf`("Sınır yok") son ek olan ARM iç bilgileri bellek engeli olarak davranmaz.

Donanım kilidi (HLE) talimatlarını destekleyen Intel işlemcilerde, `_HLEAcquire` ve `_HLERelease` son ekler, donanımda bir kilit yazma adımını ortadan kaldırarak işlemciyi hızlandıran bir ipucu içerir. Bu iç bilgiler HLE 'yı desteklemeyen işlemcilerde çağrılırsa, ipucu yok sayılır.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
