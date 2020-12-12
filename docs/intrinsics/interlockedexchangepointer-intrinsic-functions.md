---
description: 'Hakkında daha fazla bilgi edinin: _InterlockedExchangePointer iç işlevler'
title: _InterlockedExchangePointer iç işlevler
ms.date: 09/02/2019
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
ms.openlocfilehash: 0bb6080b9bca38c67b12b28976b49eb84f74e6c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97168000"
---
# <a name="_interlockedexchangepointer-intrinsic-functions"></a>_InterlockedExchangePointer iç işlevler

**Microsoft'a Özgü**

İkinci bağımsız değişken olarak geçirilen adresi ilk bağımsız değişkene kopyalayan ve ilk adresinin özgün adresini döndüren atomik bir Exchange işlemi gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```C
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

### <a name="parameters"></a>Parametreler

*Hedef*\
[in, out] Exchange 'e değer işaretçisinin işaretçisi. İşlevi değeri *Value* olarak ayarlar ve önceki değerini döndürür.

*Deeri*\
'ndaki *Hedefe* göre işaret edilen değerle değiştirilen değer.

## <a name="return-value"></a>Döndürülen değer

İşlev, *hedefe* göre işaret edilen ilk değeri döndürür.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|Üst bilgi|
|---------------|------------------|------------|
|`_InterlockedExchangePointer`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM, ARM64|\<intrin.h>|
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|x64|\<immintrin.h>|

X86 mimarisinde, `_InterlockedExchangePointer` çağıran bir makrodur `_InterlockedExchange` .

## <a name="remarks"></a>Açıklamalar

64 bitlik bir sistemde parametreler 64 bittir ve 64-bit sınırlarında hizalanmalıdır. Aksi takdirde, işlev başarısız olur. 32 bitlik bir sistemde parametreler 32 bittir ve 32-bit sınırlarında hizalanmalıdır. Daha fazla bilgi için bkz. [ALIGN](../cpp/align-cpp.md).

ARM platformlarında, `_acq` `_rel` önemli bir bölümün başındaki ve sonundaki gibi alma ve bırakma semantiklerine ihtiyacınız varsa, iç bilgileri ve son eklerini kullanın. `_nf`("Sınır olmayan") son eki olan iç öğe, bellek engeli olarak hareket etmez.

Donanım kilidi (HLE) yönergelerini destekleyen Intel platformlarında, `_HLEAcquire` ve `_HLERelease` son ekler, donanımda bir kilit yazma adımını ortadan kaldırarak işlemciyi hızlandıran bir ipucu içerir. Bu iç bilgiler HLE 'yı desteklemeyen platformlarda çağrılırsa, ipucu yok sayılır.

Bu yordamlar yalnızca iç bilgiler olarak kullanılabilir.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
