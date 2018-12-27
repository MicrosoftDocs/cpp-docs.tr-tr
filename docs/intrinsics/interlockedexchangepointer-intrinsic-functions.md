---
title: _Interlockedexchangepointer iç işlevleri
ms.date: 12/17/2018
f1_keywords:
- _InterlockedExchangePointer_cpp
- _InterlockedExchangePointer_rel
- _InterlockedExchangePointer_nf
- _InterlockedExchangePointer_HLERelease
- _InterlockedExchangePointer_acq
- _InterlockedExchangePointer
- _InterlockedExchangePointer_acq_cpp
- _InterlockedExchangePointer_HLEAcquire
helpviewer_keywords:
- _InterlockedExchangePointer_rel intrinsic
- _InterlockedExchangePointer_HLERelease intrinsic
- _InterlockedExchangePointer intrinsic
- _InterlockedExchangePointer_nf intrinsic
- _InterlockedExchangePointer_acq intrinsic
- _InterlockedExchangePointer_HLEAcquire intrinsic
- InterlockedExchangePointer_acq intrinsic
- InterlockedExchangePointer intrinsic
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
ms.openlocfilehash: 021c754436d6abe877e6b7dd372ba235869d8975
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627499"
---
# <a name="interlockedexchangepointer-intrinsic-functions"></a>_Interlockedexchangepointer iç işlevleri

**Microsoft'a özgü**

İkinci bağımsız değişken olarak geçirilen ilk adresi kopyalar ve ilk özgün adresini döndüren bir atomik değiştirme işlemi gerçekleştirin.

## <a name="syntax"></a>Sözdizimi

```
void * _InterlockedExchangePointer(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_acq(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_rel(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_nf(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_HLEAcquire(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_HLERelease(
   void * volatile * Target,
   void * Value
);
```

#### <a name="parameters"></a>Parametreler

*Hedef*<br/>
[out içinde] Exchange değere işaretçi işaretçisi. İşlev bir değer ayarlar `Value` ve önceki değerini döndürür.

*Değer*<br/>
[in] Değeri ile değiştirilecek değeri tarafından işaret edilen `Target`.

## <a name="return-value"></a>Dönüş Değeri

İşlevi tarafından işaret ilk değerini döndürür `Target`.

## <a name="requirements"></a>Gereksinimler

|İç|Mimari|Üstbilgi|
|---------------|------------------|------------|
|`_InterlockedExchangePointer`|x86, ARM, x64|\<intrin.h >|
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM|\<intrin.h >|
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|x64 HLE desteği|\<immintrin.h >|

X86 mimari `_InterlockedExchangePointer` çağıran bir makro `_InterlockedExchange`.

## <a name="remarks"></a>Açıklamalar

Bir 64-bit sistemde parametreleri 64 bit ve 64-bit sınırlardaki hizalanması gerekir; Aksi takdirde işlev başarısız olur. Bir 32-bit sistemde parametreleri 32 bit ve 32-bit sınırlardaki hizalanması gerekir. Daha fazla bilgi için [hizalama](../cpp/align-cpp.md).

ARM platformlarında, yapı içleri ile kullanmak `_acq` ve `_rel` almak ve yayın semantiğini gibi kritik bir bölüm başında ve sonunda sonekleri. İç bir `_nf` ("hiçbir sınır") soneki bellek önünde bir engel davranmaz.

Donanım kilit eleme (HLE) yönergeleri yapı içleri ile destekleyen Intel platformlarında `_HLEAcquire` ve `_HLERelease` sonekleri kapsayacak performans donanım kilit yazma adımda ortadan kaldırarak hızlandırabilir işlemci bir ipucu verir. Bu iç HLE desteklemeyen platformları üzerinde çağrılırsa ipucu yoksayıldı.

Bu yordamlar, yalnızca iç öğe olarak kullanılabilir.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)<br/>
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)