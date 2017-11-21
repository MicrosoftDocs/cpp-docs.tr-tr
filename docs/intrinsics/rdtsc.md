---
title: __rdtsc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __rdtsc
dev_langs: C++
helpviewer_keywords:
- __rdtsc intrinsic
- rdtsc instruction
- Read Time Stamp Counter instruction
ms.assetid: e31d0e51-c9bb-42ca-bbe9-a81ffe662387
caps.latest.revision: "17"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fa161bcc1845ab058773ca8ebdecfb5233235e54
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
|`__rdtsc`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
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
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)