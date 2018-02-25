---
title: _mm_cvtss_si64x | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- _mm_cvtss_si64x
dev_langs:
- C++
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 247f7a452d350cc061f323b7889268e766288f4b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x
**Microsoft Specific**  
  
 Oluşturur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] genişletilmiş sürümü Dönüştür skaler tek duyarlıklı kayan nokta sayısı 64-bit tamsayı (`cvtss2si`) yönerge.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `value`  
 Bir `__m128` kayan nokta değerlerine içeren yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir 64-bit tamsayı, ilk kayan nokta değeri bir tamsayı değerine dönüştürme sonucu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_cvtss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 İlk öğe yapısı değeri bir tamsayıya dönüştürülüp ve döndürdü. MXCSR yuvarlama denetim bitleri yuvarlama davranışını belirlemek için kullanılır. Yuvarlama modu yuvarlak ondalık kısmı 0,5 ise bile sayıya yuvarlama en yakın, varsayılandır. Çünkü `__m128` yapısı bir XMM kaydı iç bu alır XMM kasadan bir değeri temsil eder ve sistem belleğinin yazar.  
  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// _mm_cvtss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] =  
                           { 101.25, 200.75, 300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvtss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__m128d](../cpp/m128d.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)