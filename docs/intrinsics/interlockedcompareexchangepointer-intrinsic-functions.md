---
title: _Interlockedcompareexchangepointer iç işlevleri
ms.date: 09/02/2019
f1_keywords:
- _InterlockedCompareExchangePointer_HLERelease
- _InterlockedCompareExchangePointer_rel
- _InterlockedCompareExchangePointer_acq_cpp
- _InterlockedCompareExchangePointer
- _InterlockedCompareExchangePointer_cpp
- _InterlockedCompareExchangePointer_np
- _InterlockedCompareExchangePointer_rel_cpp
- _InterlockedCompareExchangePointer_HLEAcquire
- _InterlockedCompareExchangePointer_acq
- _InterlockedCompareExchangePointer_nf
helpviewer_keywords:
- InterlockedCompareExchangePointer_acq intrinsic
- _InterlockedCompareExchangePointer_rel intrinsic
- _InterlockedCompareExchangePointer_acq intrinsic
- InterlockedCompareExchangePointer_rel intrinsic
- InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_HLERelease intrinsic
- _InterlockedCompareExchangePointer_HLEAcquire intrinsic
- _InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_nf intrinsic
- _InterlockedCompareExchangePointer_np intrinsic
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
ms.openlocfilehash: c0a0083c19df51d2d2eccb7a7bbf6521303c1f85
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70222041"
---
# <a name="_interlockedcompareexchangepointer-intrinsic-functions"></a>_Interlockedcompareexchangepointer iç işlevleri

**Microsoft 'a özgü**

Ve adresi eşitse adresi `Destination` `Exchange` adresini`Destination` depolayan atomik bir işlem gerçekleştirir. `Comparand`

## <a name="syntax"></a>Sözdizimi

```C
void * _InterlockedCompareExchangePointer (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_acq (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLEAcquire (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLERelease (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_nf (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_np (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
long _InterlockedCompareExchangePointer_rel (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
[in, out] Hedef değer işaretçisinin işaretçisi. İşaret yok sayılır.

*Değişimi*\
'ndaki Exchange işaretçisi. İşaret yok sayılır.

*Karşılaştırılanı desteklemiyor*\
'ndaki Hedefle Karşılaştırılacak işaretçi. İşaret yok sayılır.

## <a name="return-value"></a>Dönüş değeri

Dönüş değeri, hedefin ilk değeridir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_InterlockedCompareExchangePointer`|x86, ARM, x64, ARM64|\<Intrin. h >|
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM, ARM64|\<iiıntrin. h >|
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, x64|\<ımintrin. h >|

## <a name="remarks"></a>Açıklamalar

`_InterlockedCompareExchangePointer``Destination` adresle`Comparand` ilgili atomik bir karşılaştırma gerçekleştirir. Adres adrese eşitse`Exchange` , adres tarafından`Destination`belirtilen adreste saklanır. `Comparand` `Destination` Aksi takdirde, işlem yapılmaz.

`_InterlockedCompareExchangePointer`Win32 Windows SDK [ınterlockedcompareexchangepointer](/windows-hardware/drivers/ddi/content/wdm/nf-wdm-interlockedcompareexchangepointer) işlevi için derleyicinin iç desteğini sağlar.

Öğesinin nasıl kullanılacağına `_InterlockedCompareExchangePointer`ilişkin bir örnek için bkz. [_ınterlockedazaltma](../intrinsics/interlockeddecrement-intrinsic-functions.md).

ARM platformlarında, önemli bir bölümün başındaki ve `_acq` sonundaki `_rel` gibi alma ve bırakma semantiklerine ihtiyacınız varsa, iç bilgileri ve son eklerini kullanın. `_nf` ("Sınır olmayan") son ek olan ARM iç öğeleri bellek engeli olarak davranmaz.

`_np` ("Önceden getirme yok") sonekine sahip iç bilgiler, olası bir önceden getirme işleminin derleyici tarafından eklenmesini engeller.

Donanım kilidi (HLE) yönergelerini destekleyen Intel platformlarında, `_HLEAcquire` ve `_HLERelease` son ekler, donanımda bir kilit yazma adımını ortadan kaldırarak işlemciyi hızlandıran bir ipucu içerir. Bu iç bilgiler HLE 'yı desteklemeyen platformlarda çağrılırsa, ipucu yok sayılır.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar Sözcükler](../cpp/keywords-cpp.md)
