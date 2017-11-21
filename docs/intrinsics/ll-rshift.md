---
title: __ll_rshift | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- __ll_rshift_cpp
- __ll_rshift
dev_langs: C++
helpviewer_keywords:
- __ll_rshift intrinsic
- ll_rshift intrinsic
ms.assetid: ef13b732-d122-44a0-add9-f5544a2c4ab2
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b247be12c40746cb8662093518be1eb8eeff2fa1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="llrshift"></a>__ll_rshift
**Microsoft özel**  
  
 İkinci parametresi tarafından belirtilen bit sayısı tarafından sağındaki ilk parametresi tarafından belirtilen bir 64-bit değeri kaydırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__int64 __ll_rshift(  
   __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in]`Mask`  
 Sağa kaydırma için 64-bit tamsayı değeri.  
  
 [in]`nBit`  
 BITS, x64 64 modulo ve 32 x86 üzerinde modulo kaydırma sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Maske gölgeye tarafından `nBit` BITS.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__ll_rshift`|x86,[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 İkinci parametre x64 (32 x86 üzerinde) 64'den büyükse, bu numara 64 (32 x86 üzerinde) modulo kaydırılacak bit sayısını belirlemek için alınır. `ll` Önek bu üzerinde bir işlem olduğunu gösterir `long long`, başka bir adı `__int64`, 64-bit imzalı tam sayı türü.  
  
## <a name="example"></a>Örnek  
  
```  
// ll_rshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_rshift)  
  
int main()  
{  
   __int64 Mask = - 0x100;  
   int nBit = 4;  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
   Mask = __ll_rshift(Mask, nBit);  
   cout << hex << Mask << endl;  
   cout << " - " << (- Mask) << endl;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
ffffffffffffff00  
 - 100  
fffffffffffffff0  
 - 10  
```  
  
 **Not** varsa `_ull_rshift` bırakıldı istenen sonucu negatif bir değer olması durumunda alındıktan olmayan şekilde kullanılan, Tamamlama sağ gölgeye değerin sıfır olacaktı.  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)   
 [__ll_lshift](../intrinsics/ll-lshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)