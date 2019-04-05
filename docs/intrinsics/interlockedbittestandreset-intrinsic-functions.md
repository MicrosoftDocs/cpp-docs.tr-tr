---
title: _interlockedbittestandreset iç işlevleri
ms.date: 12/17/2018
f1_keywords:
- _interlockedbittestandreset_rel
- _interlockedbittestandreset64
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
ms.openlocfilehash: 54ea8b1ccac15eab600c91302969b606c188dc59
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/05/2019
ms.locfileid: "59040656"
---
# <a name="interlockedbittestandreset-intrinsic-functions"></a>_interlockedbittestandreset iç işlevleri

**Microsoft'a Özgü**

Bit ayarlayan bir yönerge oluşturur `b` adresinin `a` sıfır ve özgün değeri döndürür.

## <a name="syntax"></a>Sözdizimi

```
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
unsigned char _interlockedbittestandreset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_HLERelease(
   __int64 *a,
   __int64 b
);
```

#### <a name="parameters"></a>Parametreler

*a*<br/>
[in] İncelemek için bellek işaretçisi.

*b*<br/>
[in] Test etmek için bit konumu.

## <a name="return-value"></a>Dönüş Değeri

Özgün değeri tarafından belirtilen konumdaki bit `b`.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_interlockedbittestandreset`|x86, ARM, x64|\<intrin.h >|
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM|\<intrin.h >|
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86, x64|\<immintrin.h >|
|`_interlockedbittestandreset64`|X64|\<intrin.h >|
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|X64|\<immintrin.h >|

## <a name="remarks"></a>Açıklamalar

Bu iç x86 ve x64 işlemci üzerinde kullanan `lock btr` yönerge okuyan ve atomik işlem belirtilen bit sıfır olarak ayarlar.

ARM işlemci üzerinde yapı içleri ile kullanan `_acq` ve `_rel` sonekleri edinme ve sürüm semantiği gibi kritik bir bölüm başında ve sonunda. ARM iç bilgileri ile bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel hareket değil.

Donanım kilit eleme (HLE) yönergeleri yapı içleri ile destekleyen Intel işlemci üzerinde `_HLEAcquire` ve `_HLERelease` sonekleri kapsayacak performans donanım kilit yazma adımda ortadan kaldırarak hızlandırabilir işlemci bir ipucu verir. Bu iç HLE desteklemeyen işlemciler üzerinde çağrılırsa ipucu yoksayıldı.

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

**END Microsoft'a Özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)