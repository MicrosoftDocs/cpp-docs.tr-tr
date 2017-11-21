---
title: _mm_stream_sd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _mm_stream_sd
dev_langs: C++
helpviewer_keywords:
- _mm_stream_sd intrinsic
- movntsd instruction
ms.assetid: 2b4bea5e-e64e-45fa-9afc-88a2e4b82cfc
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b5489fc1503a57011560a679d5e4f226279e4aa0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="mmstreamsd"></a>_mm_stream_sd
**Microsoft özel**  
  
 64-bit veri önbellekleri kirletmesini olmadan bir bellek konumuna yazar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
void _mm_stream_sd(  
   double * Dest,  
   __m128d Source  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [out]`Dest`  
 Veri kaynağını yazılacağı konuma bir işaretçi.  
  
 [in]`Source`  
 128-bit değerini içeren `double` 64 bit kendi alt yazılacak değer...  
  
## <a name="return-value"></a>Dönüş Değeri  
 Yok.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_stream_sd`|SSE4a|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Bu iç oluşturur `movntsd` yönergesi. Bu yönerge donanım desteğini belirlemek için arama `__cpuid` ile iç `InfoType=0x80000001` ve bit 6 denetleyin `CPUInfo[2] (ECX)`. Bu yönerge ve 0 donanım aksi destekliyorsa, bu biti 1'dir.  
  
 Kullanan kodu çalıştırırsanız `_mm_stream_sd` desteklemediği donanımda iç `movntsd` yönerge, sonuçlar tahmin edilemez.  
  
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
  
**SON Microsoft özel**  
 Gelişmiş Mikro Aygıtlar, Inc. Telif Hakkı 2007 Tüm hakları saklıdır. Gelişmiş Mikro Aygıtlar, Inc. izinle çoğaltılamaz  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [_mm_stream_ss](../intrinsics/mm-stream-ss.md)   
 [_mm_store_sd](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_store_sd)   
 [_mm_sfence](https://software.intel.com/sites/landingpage/IntrinsicsGuide/#text=_mm_sfence)   
 [Derleyici iç bilgileri](../intrinsics/compiler-intrinsics.md)