---
title: __ull_rshift | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __ull_rshift
dev_langs:
- C++
helpviewer_keywords:
- ull_rshift intrinsic
- __ull_rshift intrinsic
ms.assetid: b7ff5254-3540-4e6e-b57c-a6c4beb7dca2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5248792d04efca518fc425a144c692cd88cf8d1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333124"
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
 [in] `mask`  
 Sağa kaydırma için 64-bit tamsayı değeri.  
  
 [in] `nBit`  
 BITS, 32 x86 üzerinde modulo ve x64 64 modulo kaydırma sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Maske gölgeye tarafından `nBit` BITS.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__ull_rshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
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
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)