---
title: _mm_stream_ss | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mm_stream_ss
dev_langs: C++
helpviewer_keywords:
- movntss instruction
- _mm_stream_ss intrinsic
ms.assetid: c53dffe9-0dfe-4063-85d3-e8987b870fce
caps.latest.revision: "13"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 17d20339a311b65aef6d15c32d7c0517b7dcd9df
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mmstreamss"></a>_mm_stream_ss  
  
**Microsoft özel**  
  
 32-bit veri önbellekleri kirletmesini olmadan bir bellek konumuna yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _mm_stream_ss(  
   float * Dest,  
   __m128 Source  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
  
 [out]`Dest`  
 Kaynak veri yazıldığı konuma bir işaretçi.  
  
 [in]`Source`  
 İçeren 128 bitlik bir sayı `float` 32 bit kendi alt yazılacak değer...  
  
## <a name="return-value"></a>Dönüş Değeri  
  
 Yok.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_stream_ss`|SSE4a|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
  
Bu iç oluşturur `movntss` yönergesi. Bu yönerge donanım desteğini belirlemek için arama `__cpuid` ile iç `InfoType=0x80000001` ve bit 6 denetleyin `CPUInfo[2] (ECX)`. Bu yönerge desteklendiğinde 1 ve 0 aksi bitidir.  
  
Kullanan kodu çalıştırırsanız `_mm_stream_ss` desteklemediği donanımda iç `movntss` yönerge, sonuçlar tahmin edilemez.  
  
## <a name="example"></a>Örnek  
  
```cpp  
// Compile this sample with: /EHsc  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
int main()  
{  
    __m128 vals;  
    float f[4];  
  
    f[0] = -1.;  
    f[1] = -2.;  
    f[2] = -3.;  
    f[3] = -4.;  
    vals.m128_f32[0] = 0.;  
    vals.m128_f32[1] = 1.;  
    vals.m128_f32[2] = 2.;  
    vals.m128_f32[3] = 3.;  
    _mm_stream_ss(&f[3], vals);  
    cout << "f[0] = " << f[0] << ", f[1] = " << f[1] << endl;  
    cout << "f[1] = " << f[1] << ", f[3] = " << f[3] << endl;  
}  
```  
  
```Output  
f[0] = -1, f[1] = -2  
f[2] = -3, f[3] = 3  
```  
  
**SON Microsoft özel**  

Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_mm_stream_sd](../intrinsics/mm-stream-sd.md)   
 [_mm_stream_ps](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_stream_ps)   
 [_mm_store_ss](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_ss)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)