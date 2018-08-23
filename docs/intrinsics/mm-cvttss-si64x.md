---
title: _mm_cvttss_si64x | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvttss_si64x
dev_langs:
- C++
helpviewer_keywords:
- _mm_cvttss_si64x intrinsic
- cvttss2si instruction
ms.assetid: f9a3fd07-5bd8-4758-8744-6315c082cf87
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3f70588ca17a2bde34de6a16b62b18fa6125b08c
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464508"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x
**Microsoft'a özgü**  
  
 Genişletilmiş x64 yayan kesilmesi tek duyarlıklı Floating-Point numarası 64-Bit tamsayıya dönüştürme sürümünü (`cvttss2si`) yönerge.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `value`  
 Bir `__m128` tek duyarlıklı kayan nokta değerleri içeren yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Dönüştürme ilk kayan nokta değeri bir 64-bit tamsayı sonucu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_cvttss_si64x`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 İç farklıdır `_mm_cvtss_si64x` içeren filtresinin dönüştürmeler sıfıra yakınsayarak yalnızca kesilir. Çünkü `__m128` yapısını temsil eden bir XMM kaydı, oluşturulan yönerge verileri bir XMM yazmacından sistem belleğine taşır.  
  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// _mm_cvttss_si64x.cpp  
// processor: x64  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvttss_si64x)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    // _mm_load_ps requires an aligned buffer.  
    __declspec(align(16)) float af[4] = { 101.5, 200.75,  
                                          300.5, 400.5 };  
  
    // Load a with the floating point values.  
    // The values will be copied to the XMM registers.  
    a = _mm_load_ps(af);  
  
    // Extract the first element of a and convert to an integer  
    b = _mm_cvttss_si64x(a);  
  
    printf_s("%I64d\n", b);  
}  
```  
  
```Output  
101  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__m128](../cpp/m128.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)