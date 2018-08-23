---
title: _InterlockedCompareExchange128 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3e5433e2d1ddf94f23a3f483a8857e3032c27be3
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42465631"
---
# <a name="interlockedcompareexchange128"></a>_InterlockedCompareExchange128
**Microsoft'a özgü**  
  
 128-bit birbirine kenetlenmiş karşılaştırma ve değişim gerçekleştirir.  
  
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
 [out içinde] `Destination`  
 İki 64-bit tamsayı dizisi hedef işaretçisine 128-bit alanı olarak kabul edilir. Hedef veri 16 baytlık genel koruma hatası kaçınmak için hizalı olmalıdır.  
  
 [in] `ExchangeHigh`  
 Hedef yüksek bölümüyle değiştirilen 64-bit bir tamsayı.  
  
 [in] `ExchangeLow`  
 Hedef düşük bölümüyle değiştirilen 64-bit bir tamsayı.  
  
 [out içinde] `ComparandResult`  
 İşaretçi (128-bit alanı olarak kabul) iki 64-bit tamsayı dizisi hedef karşılaştırmak için.  Çıkışta, bu hedef özgün değeri ile yazılır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 128-bit karşılaştırılan hedef özgün değeri eşitse 1. `ExchangeHigh` ve `ExchangeLow` 128-bit hedef üzerine yazın.  
  
 0 karşılaştırılan hedef özgün değerine eşit değil. Hedef değer değiştirilmez ve hedef değeri ile karşılaştırılan değerinin üzerine yazılır.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_InterlockedCompareExchange128`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç oluşturur `cmpxchg16b` yönergesi (ile `lock` önek) 128 bit kilitli karşılaştırma ve değişim gerçekleştirilecek. Bu yönerge erken AMD 64 bit donanım sürümlerini desteklemez. İçin donanım desteği olup olmadığını denetlemek için `cmpxchg16b` yönerge, çağrı `__cpuid` ile iç `InfoType=0x00000001 (standard function 1)`. Bit 13 `CPUInfo[2]` (ECX) ise 1 yönerge olarak desteklenir.  
  
> [!NOTE]
>  Değerini `ComparandResult` her zaman üzerine yazılır. Sonra `lock` yönergesi, bu iç hemen başlangıç değeri oluşan kopyalar `Destination` için `ComparandResult`. Bu nedenle, `ComparandResult` ve `Destination` beklenmeyen davranışları önlemek için ayrı bellek konumları işaret etmelidir.  
  
 Kullanabilirsiniz, ancak `_InterlockedCompareExchange128` alt düzey bir iş parçacığı eşitleme için daha küçük bir eşitleme işlevi kullanırsanız üzerinde 128 bit eşitleme gerekmez (gibi diğer `_InterlockedCompareExchange` yapı içleri) bunun yerine. Kullanım `_InterlockedCompareExchange128` bellekte 128-bit bir değer atomik erişmek istiyorsanız.  
  
 Kullanan kodu bu iç desteği olmayan donanım üzerinde çalıştırdığınız varsa `cmpxchg16b` yönergesi, sonuçların tahmin edilemeyeceğine.  
  
 Bu yordam yalnızca bir iç öğe kullanılabilir.  
  
## <a name="example"></a>Örnek  
 Bu örnekte `_InterlockedCompareExchange128` , yüksek ve düşük sözcükleri toplamıyla iki 64-bit tamsayı dizisi üst sınırı değiştirin ve alt sözcük artırın. Erişim izni BigInt.Int dizi atomik olması, ancak bu örnek, tek bir iş parçacığı kullanır ve kolaylık olması için kilitleme yok sayar.  
  
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
  
**END Microsoft özgü**  
 Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [_Interlockedcompareexchange iç işlevleri](../intrinsics/interlockedcompareexchange-intrinsic-functions.md)   
 [x86 Derleyicisi ile Çakışma](../build/conflicts-with-the-x86-compiler.md)