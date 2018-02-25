---
title: _InterlockedCompareExchange128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _InterlockedCompareExchange128_cpp
- _InterlockedCompareExchange128
dev_langs:
- C++
helpviewer_keywords:
- cmpxchg16b instruction
- _InterlockedCompareExchange128 intrinsic
ms.assetid: f05918fc-716a-4f6d-b746-1456d6b96c56
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2850be4b93738c61e22c5ca841e07f1901ec01e2
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128
**Microsoft Specific**  
  
 Exchange ve 128-bit ınterlocked karşılaştırmak gerçekleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned char _InterlockedCompareExchange128(  
   __int64 volatile * Destination,  
   __int64 ExchangeHigh,  
   __int64 ExchangeLow,  
   __int64 * ComparandResult  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [içinde out] `Destination`  
 İşaretçi iki 64 bit tam sayı dizisidir hedef için 128-bit alan olarak kabul edilir. Hedef veri genel koruma hatası önlemek için hizalı 16 bayt olmalıdır.  
  
 [in] `ExchangeHigh`  
 Hedef yüksek bölümüyle değiştirilen bir 64-bit tamsayı.  
  
 [in] `ExchangeLow`  
 Hedef düşük bölümüyle değiştirilen bir 64-bit tamsayı.  
  
 [içinde out] `ComparandResult`  
 İki 64-bit tamsayı (128-bit alan olarak kabul) dizisi işaretçisine hedef karşılaştırmak için.  Çıkışta bu hedef özgün değerle üzerine yazılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 128-bit karşılaştırılan hedef özgün değeri eşitse 1. `ExchangeHigh` ve `ExchangeLow` 128-bit hedef üzerine yazın.  
  
 0 karşılaştırılan hedef özgün değeri eşit değil. Hedef değer değişmeden ve hedef değeri ile karşılaştırılan değerinin üzerine yazılır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_InterlockedCompareExchange128`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç oluşturur `cmpxchg16b` yönergesi (ile `lock` önek) 128-bit kilitli Karşılaştır ve exchange gerçekleştirmek için. Bu yönerge AMD 64 bit donanım'ın önceki sürümlerinde desteklenmez. Donanım desteği olup olmadığını denetlemek için `cmpxchg16b` yönerge, çağrı `__cpuid` ile iç `InfoType=0x00000001 (standard function 1)`. Bit 13 `CPUInfo[2]` (ECX) ise 1 yönerge desteklenir.  
  
> [!NOTE]
>  Değeri `ComparandResult` her zaman üzerine yazılır. Sonra `lock` yönerge, bu iç hemen ilk değeri kopyalar `Destination` için `ComparandResult`. Bu nedenle, `ComparandResult` ve `Destination` beklenmeyen davranışları önlemek için ayrı bir bellek konumlara işaret etmelidir.  
  
 Kullanabilirsiniz ancak `_InterlockedCompareExchange128` alt düzey iş parçacığı eşitleme için daha küçük bir eşitleme işlevi kullanırsanız üzerinde 128 bit eşitleme gerekmez (diğer gibi `_InterlockedCompareExchange` iç bilgileri) yerine. Kullanım `_InterlockedCompareExchange128` bellek 128-bit değerinde atomik erişmek istiyorsanız.  
  
 Kullanan kodu bu iç desteklemediği donanımda çalıştırırsanız `cmpxchg16b` yönerge, sonuçlar tahmin edilemez.  
  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `_InterlockedCompareExchange128` yüksek ve düşük sözcükler toplamını iki 64-bit dizisi üst sınırı değiştirmek için ve Düşük word arttırmak için. BigInt.Int dizi erişimi atomik, ancak bu örnek, tek bir iş parçacığı kullanır ve kolaylık sağlamak için kilitleme yok sayar.  
  
```  
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
  
**SON Microsoft özel**  
 Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [_InterlockedCompareExchange iç işlevler](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)