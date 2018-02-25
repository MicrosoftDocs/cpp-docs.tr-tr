---
title: __ll_lshift | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- __ll_lshift_cpp
- __ll_lshift
dev_langs:
- C++
helpviewer_keywords:
- ll_lshift intrinsic
- __ll_lshift intrinsic
ms.assetid: fe98f733-426d-44b3-8f24-5d0d6d44bd94
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: df8aed34d31fe1675dc13d0c040c1a9f0b1f208e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="lllshift"></a>__ll_lshift
**Microsoft Specific**  
  
 Sağlanan 64-bit değer belirtilen bit sayısı kadar sola kaydırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `Mask`  
 Sola kaydırma için 64-bit tamsayı değeri.  
  
 [in] `nBit`  
 Kaydırılacak bit sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Maske gölgeye sol tarafından `nBit` BITS.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__ll_lshift`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 64 bitlik bir mimari kullanarak programınızı derleme varsa ve `nBit` 63 büyük bitler kaydırılacak sayısı `nBit` 64 modül. 32 bitlik bir mimari kullanarak programınızı derleme varsa ve `nBit` 31'den büyük bitler kaydırılacak sayısı `nBit` 32 modül.  
  
 `ll` Adlarında bunun üzerinde bir işlem olduğunu gösterir `long long` (`__int64`).  
  
## <a name="example"></a>Örnek  
  
```  
// ll_lshift.cpp  
// compile with: /EHsc  
// processor: x86, x64  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(__ll_lshift)  
  
int main()  
{  
   unsigned __int64 Mask = 0x100;  
   int nBit = 8;  
   Mask = __ll_lshift(Mask, nBit);  
   cout << hex << Mask << endl;  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
10000  
```  
  
 **Not** sola kaydırma işlemi imzasız hiçbir sürümü yok. Bunun nedeni, `__ll_lshift` imzasız bir giriş parametresi zaten kullanıyor. Sağa kaydırma var. hiçbir oturum bağımlılığı sola kaydırma için en az önemli bit sonuç her zaman gölgeye değeri oturum bağımsız olarak sıfır olarak ayarlanmış olduğundan  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)