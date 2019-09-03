---
title: _InterlockedIncrement iç işlevleri
ms.date: 09/02/2019
f1_keywords:
- _InterlockedIncrement_acq
- _InterlockedIncrement16_rel_cpp
- _InterlockedIncrement16_cpp
- _InterlockedIncrement64_rel
- _InterlockedIncrement_rel
- _InterlockedIncrement64_nf
- _InterlockedIncrement16_acq_cpp
- _InterlockedIncrement_rel_cpp
- _InterlockedIncrement64
- _InterlockedIncrement64_rel_cpp
- _InterlockedIncrement16_nf
- _InterlockedIncrement16_rel
- _InterlockedIncrement16_acq
- _InterlockedIncrement_nf
- _InterlockedIncrement_acq_cpp
- _InterlockedIncrement64_cpp
- _InterlockedIncrement64_acq_cpp
- _InterlockedIncrement
- _InterlockedIncrement_cpp
- _InterlockedIncrement64_acq
- _InterlockedIncrement16
helpviewer_keywords:
- _InterlockedIncrement64_rel intrinsic
- _InterlockedIncrement16_rel intrinsic
- InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16 intrinsic
- _InterlockedIncrement16_acq intrinsic
- _InterlockedIncrement_nf intrinsic
- _InterlockedIncrement_rel intrinsic
- _InterlockedIncrement64_nf intrinsic
- InterlockedIncrement_rel intrinsic
- InterlockedIncrement_acq intrinsic
- _InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16_nf intrinsic
- _InterlockedIncrement intrinsic
- _InterlockedIncrement64 intrinsic
- InterlockedIncrement64_rel intrinsic
- InterlockedIncrement64 intrinsic
- InterlockedIncrement16 intrinsic
- _InterlockedIncrement_acq intrinsic
- InterlockedIncrement intrinsic
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
ms.openlocfilehash: 4dd9ae9ba5454b0afefa332689d94fa3619a07a6
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221987"
---
# <a name="_interlockedincrement-intrinsic-functions"></a>_InterlockedIncrement iç işlevleri

**Microsoft 'a özgü**

Win32 Windows SDK [InterlockedIncrement](/windows/win32/api/winnt/nf-winnt-interlockedincrement) işlevi için derleyicinin iç desteğini sağlayın.

## <a name="syntax"></a>Sözdizimi

```C
long _InterlockedIncrement(
   long * lpAddend
);
long _InterlockedIncrement_acq(
   long * lpAddend
);
long _InterlockedIncrement_rel(
   long * lpAddend
);
long _InterlockedIncrement_nf(
   long * lpAddend
);
short _InterlockedIncrement16(
   short * lpAddend
);
short _InterlockedIncrement16_acq(
   short * lpAddend
);
short _InterlockedIncrement16_rel(
   short * lpAddend
);
short _InterlockedIncrement16_nf (
   short * lpAddend
);
__int64 _InterlockedIncrement64(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_acq(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_rel(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_nf(
   __int64 * lpAddend
);
```

### <a name="parameters"></a>Parametreler

*lpAddend*\
[in, out] Arttırılacak değişken işaretçisi.

## <a name="return-value"></a>Dönüş değeri

Dönüş değeri, elde edilen artılan değerdir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_InterlockedIncrement`, `_InterlockedIncrement16`|x86, ARM, x64, ARM64|\<Intrin. h >|
|`_InterlockedIncrement64`|ARM, x64, ARM64|\<Intrin. h >|
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM, ARM64|\<Intrin. h >|

## <a name="remarks"></a>Açıklamalar

Üzerinde bulunan `_InterlockedIncrement` veri türlerine göre farklılık gösteren çeşitli çeşitlemeler vardır ve işlemciye özgü alma veya yayınlama semantiği kullanılıp kullanılmayacağını belirtir.

İşlev 32 bitlik tamsayı değerlerinde çalışırken, `_InterlockedIncrement16` 16 bit tamsayı değerlerinde çalışır ve `_InterlockedIncrement64` 64 bit tamsayı değerlerinde çalışır. `_InterlockedIncrement`

ARM platformlarında, önemli bir bölümün başındaki ve `_acq` sonundaki `_rel` gibi alma ve bırakma semantiklerine ihtiyacınız varsa, iç bilgileri ve son eklerini kullanın. `_nf` ("Sınır olmayan") son eki olan iç öğe, bellek engeli olarak hareket etmez.

`lpAddend` Parametresi tarafından işaret edilen değişken 32 bitlik bir sınıra hizalanmalıdır; Aksi takdirde, bu işlev çok işlemcili x86 sistemlerinde ve x86 olmayan sistemlerde başarısız olur. Daha fazla bilgi için bkz. [ALIGN](../cpp/align-cpp.md).

Win32 işlevi veya `Wdm.h` `Ntddk.h`içinde bildirilmiştir.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

## <a name="example"></a>Örnek

Öğesinin nasıl kullanılacağına `_InterlockedIncrement`ilişkin bir örnek için bkz. [_ınterlockedazaltma](../intrinsics/interlockeddecrement-intrinsic-functions.md).

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Lerimi](../cpp/keywords-cpp.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
