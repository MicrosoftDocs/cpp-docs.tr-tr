---
description: 'Hakkında daha fazla bilgi edinin: _InterlockedCompareExchangePointer iç işlevler'
title: _InterlockedCompareExchangePointer iç işlevler
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
ms.openlocfilehash: cd8d42c6a7036a6c779af6fc32a7176b7e48a73c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168065"
---
# <a name="_interlockedcompareexchangepointer-intrinsic-functions"></a>_InterlockedCompareExchangePointer iç işlevler

**Microsoft'a Özgü**

`Exchange` `Destination` `Comparand` Ve adresi eşitse adresi adresini depolayan atomik bir işlem gerçekleştirir `Destination` .

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

*Exchange*\
'ndaki Exchange işaretçisi. İşaret yok sayılır.

*Karşılaştırılanı desteklemiyor*\
'ndaki Hedefle Karşılaştırılacak işaretçi. İşaret yok sayılır.

## <a name="return-value"></a>Döndürülen değer

Dönüş değeri, hedefin ilk değeridir.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_InterlockedCompareExchangePointer`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM, ARM64|\<iiintrin.h>|
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, x64|\<immintrin.h>|

## <a name="remarks"></a>Açıklamalar

`_InterlockedCompareExchangePointer` adresle ilgili atomik bir karşılaştırma gerçekleştirir `Destination` `Comparand` . `Destination`Adres `Comparand` adrese eşitse, `Exchange` Adres tarafından belirtilen adreste saklanır `Destination` . Aksi takdirde, işlem yapılmaz.

`_InterlockedCompareExchangePointer` Win32 Windows SDK [ınterlockedcompareexchangepointer](/windows-hardware/drivers/ddi/content/wdm/nf-wdm-interlockedcompareexchangepointer) işlevi için derleyicinin iç desteğini sağlar.

Öğesinin nasıl kullanılacağına ilişkin bir örnek için `_InterlockedCompareExchangePointer` bkz. [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

ARM platformlarında, `_acq` `_rel` önemli bir bölümün başındaki ve sonundaki gibi alma ve bırakma semantiklerine ihtiyacınız varsa, iç bilgileri ve son eklerini kullanın. `_nf`("Sınır olmayan") son ek olan ARM iç öğeleri bellek engeli olarak davranmaz.

`_np`("Önceden getirme yok") sonekine sahip iç bilgiler, olası bir önceden getirme işleminin derleyici tarafından eklenmesini engeller.

Donanım kilidi (HLE) yönergelerini destekleyen Intel platformlarında, `_HLEAcquire` ve `_HLERelease` son ekler, donanımda bir kilit yazma adımını ortadan kaldırarak işlemciyi hızlandıran bir ipucu içerir. Bu iç bilgiler HLE 'yı desteklemeyen platformlarda çağrılırsa, ipucu yok sayılır.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[Anahtar sözcükler](../cpp/keywords-cpp.md)
