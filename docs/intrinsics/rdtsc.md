---
title: __rdtsc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __rdtsc
dev_langs:
- C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 81b47a76b3045465d8c3c5c21a87020ee1e74a69
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337086"
---
# <a name="rdtsc"></a>__rdtsc
**Microsoft özel**  
  
 Oluşturur `rdtsc` işlemci zaman damgasını döndürür yönerge. İşlemci zaman damgası, son sıfırlamadan sonraki saat döngüsü sayısını kaydeder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 __rdtsc();  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 Değer çizgisi sayısını temsil eden bir 64-bit işaretsiz tamsayı.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__rdtsc`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
 ' In önceki sürümlerinde TSC değeri yorumu donanım bu oluşturmada farklı [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]. Donanım kılavuzlarına daha fazla bilgi için bkz.  
  
## <a name="example"></a>Örnek  
  
```  
// rdtsc.cpp  
// processor: x86, x64  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(__rdtsc)  
  
int main()  
{  
    unsigned __int64 i;  
    i = __rdtsc();  
    printf_s("%I64d ticks\n", i);  
}  
```  
  
```Output  
3363423610155519 ticks  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)