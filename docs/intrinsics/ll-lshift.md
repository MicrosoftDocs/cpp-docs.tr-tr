---
title: __ll_lshift | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4bfb567774191edb86a9eb34a38be69344f19575
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45702084"
---
# <a name="lllshift"></a>__ll_lshift
**Microsoft'a özgü**  
  
 Sağlanan 64-bit değeri belirtilen bit sayısı kadar sola kaydırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
unsigned __int64 __ll_lshift(  
   unsigned __int64 Mask,  
   int nBit  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Maskesi*<br/>
[in] Sola kaydırılacak 64-bit tamsayı değeri.  
  
*nBit*<br/>
[in] Kaydırılacak bit sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Maskesi tarafından sola kaydırılacak `nBit` bitleri.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`__ll_lshift`|x86, x64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 64 bit mimari kullanarak programınızı derlerseniz ve `nBit` 63 büyük kaydırılacak bit sayıdır `nBit` 64 modül. 32 bit mimari kullanarak programınızı derlerseniz ve `nBit` 31'den büyük kaydırılacak bit sayıdır `nBit` 32 modül.  
  
 `ll` Adlarında bunun üzerinde bir işlem olduğunu gösteren `long long` (`__int64`).  
  
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
  
 **Not** sola kaydırma işleminin işaretsiz sürümü yoktur. Bunun nedeni, `__ll_lshift` işaretsiz bir giriş parametresi zaten kullanıyor. Sağa kaydırma yoktur hiçbir oturum bağımlılığı sola kaydırma için en az önemli bit sonuçta her zaman kaydırılacağı uzaklık değeri ne olursa olsun işaretini sıfır olarak ayarlanmış olduğundan.  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__ll_rshift](../intrinsics/ll-rshift.md)   
 [__ull_rshift](../intrinsics/ull-rshift.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)