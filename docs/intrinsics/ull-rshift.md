---
title: __ull_rshift | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: __ull_rshift
dev_langs: C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0d1519ead8d57e350ca0de95ab5db0c9fae14f05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ullrshift"></a>__ull_rshift
**Microsoft özel**  
  
 x64 üzerinde sağındaki ilk parametresi tarafından belirtilen bir 64-bit değeri ikinci parametresi tarafından belirtilen bit sayısı tarafından kaydırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 __ull_rshift(   
   unsigned __int64 mask,    
   int nBit   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`mask`  
 Sağa kaydırma için 64-bit tamsayı değeri.  
  
 [in]`nBit`  
 BITS, 32 x86 üzerinde modulo ve x64 64 modulo kaydırma sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Maske gölgeye tarafından `nBit` BITS.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__ull_rshift`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 İkinci parametre 31 x86 (63 x64 üzerinde) üzerinde daha büyükse, numara 32 (x64 64) modulo kaydırılacak bit sayısını belirlemek için alınır. `ull` Adlarında gösterir `unsigned long long (unsigned __int64)`.  
  
## <a name="example"></a>Örnek  
  
```  
// ull_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ull_rshift)  
  
int main()  
{  
   unsigned __int64 mask = 0x100;  
   int nBit = 8;  
   mask = __ull_rshift(mask, nBit);  
   cout << hex << mask << endl;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
1  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)