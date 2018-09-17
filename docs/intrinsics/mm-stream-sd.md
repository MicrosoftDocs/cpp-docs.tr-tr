---
title: _mm_stream_sd | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_stream_sd
dev_langs:
- C++
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2fb8608e03a514228ecdbaf321124c17a00aeb5c
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700173"
---
# <a name="mmstreamsd"></a>_mm_stream_sd

**Microsoft'a özgü**  
  
 64-bit veri önbelleklerinin kirletmesini olmadan bir bellek konumuna yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*Hedef*<br/>
[out] Kaynak verilerin yazılacağı konum için bir işaretçi.  
  
*Kaynak*<br/>
[in] 128-bit değeri içeren bir `double` 64 bit kendi alt yazılacak değer...  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yok.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç oluşturur `movntsd` yönergesi. Bu yönerge için donanım desteği belirlemek için çağrı `__cpuid` ile iç `InfoType=0x80000001` ve 6 bit `CPUInfo[2] (ECX)`. Aksi takdirde bu yönerge ve 0 donanım destekliyorsa, bu bit 1'dir.  
  
 Kullanan kodu çalıştırırsanız `_mm_stream_sd` desteği olmayan donanımda iç `movntsd` yönergesi, sonuçların tahmin edilemeyeceğine.  
  
## <a name="example"></a>Örnek  
  
```  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128d vals;  
    double d[2];  
  
    d[0] = -1.;  
    d[1] = -2.;  
    vals.m128d_f64[0] = 0.;  
    vals.m128d_f64[1] = 1.;  
    _mm_stream_sd(&d[1], vals);  
    cout << "d[0] = " << d[0] << ", d[1] = " << d[1] << endl;  
}  
  
```  
  
```Output  
d[0] = -1, d[1] = 1  
```  
  
**END Microsoft özgü**  

Telif Hakkı 2007 Gelişmiş Micro cihazlar, Inc. Tüm hakları saklıdır. Gelişmiş Micro cihazlar, Inc. izniyle üretilemez  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_mm_stream_ss](../intrinsics/mm-stream-ss.md)   
 [_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)