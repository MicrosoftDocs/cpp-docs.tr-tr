---
title: _Interlockedcompareexchangepointer iç işlevleri
ms.date: 11/04/2016
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
ms.openlocfilehash: 2db18c73f7765454d29e2dfdbd9408f62c51d32a
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59024822"
---
# <a name="interlockedcompareexchangepointer-intrinsic-functions"></a>_Interlockedcompareexchangepointer iç işlevleri

**Microsoft'a özgü**

Depolayan atomik işlem gerçekleştirir `Exchange` içindeki adres `Destination` adres `Comparand` ve `Destination` adresi eşit.

## <a name="syntax"></a>Sözdizimi

```
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

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out içinde] Hedef değer için bir işaretçi işaretçisi. Oturum yok sayılır.

*Exchange*<br/>
[in] Exchange işaretçisi. Oturum yok sayılır.

*Karşılaştırılan*<br/>
[in] Hedefe karşılaştırmak için işaretçi. Oturum yok sayılır.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri hedef ilk değeridir.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_InterlockedCompareExchangePointer`|x86, ARM, x64|\<intrin.h >|
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h >|
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, x64|\<immintrin.h >|

## <a name="remarks"></a>Açıklamalar

`_InterlockedCompareExchangePointer` atomik bir karşılaştırma gerçekleştirir `Destination` ele `Comparand` adresi. Varsa `Destination` adresi eşittir `Comparand` adresi `Exchange` adresi tarafından belirtilen adresi depolanan `Destination`. Aksi takdirde, hiçbir işlem yapılmadı.

`_InterlockedCompareExchangePointer` Win32 Windows SDK'sı için derleyici iç desteği sağlayan [_ınterlockedcompareexchangepointer](https://msdn.microsoft.com/library/ff547863.aspx) işlevi.

Nasıl kullanılacağını gösteren bir örnek `_InterlockedCompareExchangePointer`, bkz: [_ınterlockeddecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

ARM platformlarında, yapı içleri ile kullanmak `_acq` ve `_rel` almak ve yayın semantiğini gibi kritik bir bölüm başında ve sonunda sonekleri. ARM iç bilgileri ile bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel hareket değil.

Yapı içleri ile bir `_np` ("hiçbir hazırlık") soneki, derleyici tarafından eklenen bir olası önceden getirme işleminin engelle.

Donanım kilit eleme (HLE) yönergeleri yapı içleri ile destekleyen Intel platformlarında `_HLEAcquire` ve `_HLERelease` sonekleri kapsayacak performans donanım kilit yazma adımda ortadan kaldırarak hızlandırabilir işlemci bir ipucu verir. Bu iç HLE desteklemeyen platformları üzerinde çağrılırsa ipucu yoksayıldı.

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[Anahtar Sözcükler](../cpp/keywords-cpp.md)