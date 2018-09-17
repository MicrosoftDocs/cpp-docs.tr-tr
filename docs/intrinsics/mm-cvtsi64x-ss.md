---
title: _mm_cvtsi64x_ss | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvtsi64x_ss
dev_langs:
- C++
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eb253ab776565339aeaeade26d6d355b4f6a742b
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45700008"
---
# <a name="mmcvtsi64xss"></a>_mm_cvtsi64x_ss
**Microsoft'a özgü**  
  
 Genişletilmiş x64 oluşturur sürüm skaler tek duyarlık Floating-Point değerine dönüştürme 64-Bit tamsayı (`cvtsi2ss`) yönerge.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__m128 _mm_cvtsi64x_ss(   
   __m128 a,   
   __int64 b   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
*a*<br/>
[in] Bir `__m128` dört tek duyarlıklı kayan nokta değerleri içeren yapısı.  
  
*b*<br/>
[in] Bir kayan nokta değerine dönüştürülmesi 64-bit tamsayı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir `__m128` yapısı ilk kayan nokta değeri olan dönüştürme işleminin sonucu. Diğer üç değerden gelen değişmeden kopyalanır `a`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_cvtsi64x_ss`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 `__m128` Yapısını temsil eden bir XMM kaydı, bu nedenle bu iç değer verir `b` bir XMM taşınacak sistem belleğinden kaydedin.  
  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// _mm_cvtsi64x_ss.cpp  
// processor: x64  
  
#include <intrin.h>  
#include <stdio.h>  
  
#pragma intrinsic(_mm_cvtsi64x_ss)  
  
int main()  
{  
    __m128 a;  
    __int64 b = 54;  
  
    a.m128_f32[0] = 0;  
    a.m128_f32[1] = 0;  
    a.m128_f32[2] = 0;  
    a.m128_f32[3] = 0;  
    a = _mm_cvtsi64x_ss(a, b);  
  
    printf_s( "%lf %lf %lf %lf\n",  
              a.m128_f32[0], a.m128_f32[1],   
              a.m128_f32[2], a.m128_f32[3] );  
}  
```  
  
```Output  
54.000000 0.000000 0.000000 0.000000  
```  
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__m128](../cpp/m128.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)