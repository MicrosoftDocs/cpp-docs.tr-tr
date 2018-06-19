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
ms.openlocfilehash: c4fd8aebb3f9a4f0078c8174aa25b9abb9378f1b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33333635"
---
# <a name="mmcvttsssi64x"></a>_mm_cvttss_si64x
**Microsoft özel**  
  
 Genişletilmiş x64 yayar sürüm numarasıyla kesilmesi tek duyarlıklı Floating-Point 64-Bit tamsayı Convert (`cvttss2si`) yönerge.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__int64 _mm_cvttss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `value`  
 Bir `__m128` tek duyarlıklı kayan nokta değerlerini içeren yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir 64-bit tamsayı ilk kayan nokta değeri dönüştürülmesi sonucu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_cvttss_si64x`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|  
  
 **Üstbilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 İç farklıdır `_mm_cvtss_si64x` içeren filtresinin dönüşümleri sıfır yalnızca kesilir. Çünkü `__m128` yapısını temsil eden bir XMM kaydı, oluşturulan yönerge verileri XMM kaydından sistem belleğe taşır.  
  
 Bu yordam yalnızca bir iç kullanılabilir.  
  
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
  
**SON Microsoft özel**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__m128](../cpp/m128.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)