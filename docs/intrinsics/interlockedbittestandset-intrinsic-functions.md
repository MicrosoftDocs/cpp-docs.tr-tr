---
title: _interlockedbittestandset iç işlevleri
ms.date: 12/17/2018
f1_keywords:
- _interlockedbittestandset_cpp
- _interlockedbittestandset_HLEAcquire
- _interlockedbittestandset64
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
ms.openlocfilehash: 2f7dc1cf6501f789d969143bc23469a6ecf7239c
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627221"
---
# <a name="interlockedbittestandset-intrinsic-functions"></a>_interlockedbittestandset iç işlevleri

**Microsoft'a özgü**

Bit arabirimini inceleyen bir yönerge oluşturur `b` adresinin `a` ve 1 olarak ayarlamadan önce geçerli değeri döndürür.

## <a name="syntax"></a>Sözdizimi

```
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
unsigned char _interlockedbittestandset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandset64_HLERelease(
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

Konumunda bit değeri `b` önce ayarlanır.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_interlockedbittestandset`|x86, ARM, x64|\<intrin.h >|
|`_interlockedbittestandset_acq`, `_interlockedbittestandset_nf`, `_interlockedbittestandset_rel`|ARM|\<intrin.h >|
|`_interlockedbittestandset_HLEAcquire`, `_interlockedbittestandset_HLERelease`|x86, x64|\<immintrin.h >|
|`_interlockedbittestandset64`|X64|\<intrin.h >|
|`_interlockedbittestandset64_HLEAcquire`, `_interlockedbittestandset64_HLERelease`|X64|\<immintrin.h >|

## <a name="remarks"></a>Açıklamalar

Bu iç x86 ve x64 işlemci üzerinde kullanan `lock bts` yönerge okuyup belirtilen bit 1 olarak ayarlayın. Atomik bir işlemdir.

ARM işlemci üzerinde yapı içleri ile kullanan `_acq` ve `_rel` sonekleri edinme ve sürüm semantiği gibi kritik bir bölüm başında ve sonunda. ARM iç bilgileri ile bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel hareket değil.

Donanım kilit eleme (HLE) yönergeleri yapı içleri ile destekleyen Intel işlemci üzerinde `_HLEAcquire` ve `_HLERelease` sonekleri kapsayacak performans donanım kilit yazma adımda ortadan kaldırarak hızlandırabilir işlemci bir ipucu verir. Bu iç HLE desteklemeyen işlemciler üzerinde çağrılırsa ipucu yoksayıldı.

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)