---
title: _InterlockedCompareExchange128 iç işlevleri
ms.date: 09/02/2019
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
- _InterlockedCompareExchange128_acq
- _InterlockedCompareExchange128_nf
- _InterlockedCompareExchange128_np
- _InterlockedCompareExchange128_rel
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
ms.openlocfilehash: 525b0fd77323789eed05c47c944794ff389bfac5
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70217694"
---
# <a name="_interlockedcompareexchange128-intrinsic-functions"></a>_InterlockedCompareExchange128 iç işlevleri

**Microsoft 'a özgü**

128 bit bir karşılıklı kilitli karşılaştırma ve değişim gerçekleştirir.

## <a name="syntax"></a>Sözdizimi

```C
unsigned char _InterlockedCompareExchange128(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_acq(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_nf(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_np(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
unsigned char _InterlockedCompareExchange128_rel(
   __int64 volatile * Destination,
   __int64 ExchangeHigh,
   __int64 ExchangeLow,
   __int64 * ComparandResult
);
```

### <a name="parameters"></a>Parametreler

*Hedefine*\
[in, out] 128 bit alan olarak kabul edilen 2 64 bitlik tamsayılar dizisi olan hedefe yönelik işaretçi. Genel koruma hatasının oluşmaması için hedef veriler 16 baytlık hizalı olmalıdır.

*ExchangeHigh*\
'ndaki Hedefin yüksek bölümüyle değiş tokuş edilen 64 bitlik bir tamsayı.

*ExchangeLow*\
'ndaki Hedefin düşük bölümüyle değiş tokuş edilen 64 bitlik bir tamsayı.

*ComparandResult*\
[in, out] Hedefle karşılaştırmak için 2 64 bitlik tamsayılar dizisi işaretçisi (128 bit alan olarak kabul edilir).  Çıkışta, hedefin orijinal değeri ile bu dizinin üzerine yazılır.

## <a name="return-value"></a>Dönüş değeri

128 bit karşılaştırıya ve hedefin orijinal değerine eşitse 1. `ExchangeHigh`ve `ExchangeLow` 128 bitlik hedefin üzerine yazın.

karşılaştırılan, hedefin orijinal değerine eşit değilse 0. Hedefin değeri değiştirilmez ve karşılaştırın değeri hedef değeri ile üzerine yazılır.

## <a name="requirements"></a>Gereksinimler

|Alanlarla|Mimari|
|---------------|------------------|
|`_InterlockedCompareExchange128`|x64, ARM64|
|`_InterlockedCompareExchange128_acq`, `_InterlockedCompareExchange128_nf`, `_InterlockedCompareExchange128_rel`|ARM64|
|`_InterlockedCompareExchange128_np`|X64|

**Üst bilgi dosyası** \<Intrin. h >

## <a name="remarks"></a>Açıklamalar

İç `_InterlockedCompareExchange128` , 128 bitlik `cmpxchg16b` bir kilitli karşılaştırma ve `lock` değişim gerçekleştirmek için yönergeyi (önekiyle birlikte) oluşturur. AMD 64 bit donanımlarının erken sürümleri bu yönergeyi desteklemez. `cmpxchg16b` Yönergeyle ilgili donanım desteğini denetlemek için, ile `__cpuid` `InfoType=0x00000001 (standard function 1)`iç öğesini çağırın. Yönerge destekleniyorsa, `CPUInfo[2]` bit 13/(ecx) 1 ' dir.

> [!NOTE]
> Değerinin `ComparandResult` her zaman üzerine yazılır. Yönergeden sonra bu iç, ' ın `Destination` başlangıç değerini hemen olarak `ComparandResult`kopyalar. `lock` Bu nedenle, `ComparandResult` `Destination` beklenmeyen davranışları önlemek için ayrı bellek konumlarına işaret etmelidir.

Alt düzey iş parçacığı `_InterlockedCompareExchange128` eşitlemesi için kullanabilirsiniz, ancak bunun yerine daha küçük eşitleme işlevleri (diğer `_InterlockedCompareExchange` iç bilgiler gibi) kullanacaksanız, 128 bit üzerinden eşitleme yapmanız gerekmez. Bellekte `_InterlockedCompareExchange128` 128 bitlik bir değere atomik erişim istiyorsanız kullanın.

`cmpxchg16b` Yönergeyi desteklemeyen bir donanım kullanan kodu çalıştırırsanız, sonuçlar tahmin edilemez olur.

ARM platformlarında, önemli bir bölümün başındaki ve `_acq` sonundaki `_rel` gibi alma ve bırakma semantiği için iç bilgileri ve sonekleri kullanın. `_nf` ("Sınır yok") son ek olan ARM iç bilgileri bellek engeli olarak davranmaz.

`_np` ("Önceden getirme yok") sonekine sahip iç bilgiler, olası bir önceden getirme işleminin derleyici tarafından eklenmesini engeller.

Bu yordam yalnızca bir iç öğe olarak kullanılabilir.

## <a name="example"></a>Örnek

Bu örnek, `_InterlockedCompareExchange128` 2 64 bitlik tamsayıların bir dizisinin yüksek sözcüğünü yüksek ve düşük sözcüklerin toplamına ve düşük kelimeyi artırmak için kullanır. `BigInt.Int` Diziye erişim atomik bir örnektir, ancak bu örnek tek bir iş parçacığı kullanır ve basitlik için kilitlemeyi yoksayar.

```cpp
// cmpxchg16b.c
// processor: x64
// compile with: /EHsc /O2
#include <stdio.h>
#include <intrin.h>

typedef struct _LARGE_INTEGER_128 {
    __int64 Int[2];
} LARGE_INTEGER_128, *PLARGE_INTEGER_128;

volatile LARGE_INTEGER_128 BigInt;

// This AtomicOp() function atomically performs:
//   BigInt.Int[1] += BigInt.Int[0]
//   BigInt.Int[0] += 1
void AtomicOp ()
{
    LARGE_INTEGER_128 Comparand;
    Comparand.Int[0] = BigInt.Int[0];
    Comparand.Int[1] = BigInt.Int[1];
    do {
        ; // nothing
    } while (_InterlockedCompareExchange128(BigInt.Int,
                                            Comparand.Int[0] + Comparand.Int[1],
                                            Comparand.Int[0] + 1,
                                            Comparand.Int) == 0);
}

// In a real application, several threads contend for the value
// of BigInt.
// Here we focus on the compare and exchange for simplicity.
int main(void)
{
   BigInt.Int[1] = 23;
   BigInt.Int[0] = 11;
   AtomicOp();
   printf("BigInt.Int[1] = %d, BigInt.Int[0] = %d\n",
      BigInt.Int[1],BigInt.Int[0]);
}
```

```Output
BigInt.Int[1] = 34, BigInt.Int[0] = 12
```

**SON Microsoft 'a özgü**


## <a name="see-also"></a>Ayrıca bkz.

[Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)\
[_InterlockedCompareExchange iç işlevleri](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)\
[x86 Derleyicisi ile Çakışma](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
