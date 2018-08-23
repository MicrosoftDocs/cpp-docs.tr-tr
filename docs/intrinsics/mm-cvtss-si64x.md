---
title: _mm_cvtss_si64x | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _mm_cvtss_si64x
dev_langs:
- C++
helpviewer_keywords:
- cvtss2si intrinsic
- _mm_cvtss_si64x intrinsic
ms.assetid: c279aff2-ee29-4271-8829-3ec691bf7718
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 947c9bf0892da52b44a99486b3ff0f1d59bc6fee
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/14/2018
ms.locfileid: "42464673"
---
# <a name="mmcvtsssi64x"></a>_mm_cvtss_si64x
**Microsoft'a özgü**  
  
 Genişletilmiş x64 oluşturur Dönüştür skaler tek duyarlıklı kayan nokta sayısı 64-bit tamsayıya sürümünü (`cvtss2si`) yönerge.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
__int64 _mm_cvtss_si64x(   
   __m128 value   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 [in] `value`  
 Bir `__m128` kayan nokta değerleri içeren yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bir 64-bit tamsayı, ilk kayan nokta değeri bir tamsayıya dönüştürme işleminin sonucu.  
  
## <a name="requirements"></a>Gereksinimler  
  
|İç|Mimari|  
|---------------|------------------|  
|`_mm_cvtss_si64x`|X64|  
  
 **Üst bilgi dosyası** \<intrin.h >  
  
## <a name="remarks"></a>Açıklamalar  
 Yapı değerinin ilk öğe bir tamsayıya dönüştürülüp ve döndürdü. MXCSR yuvarlama denetimi bitler, yuvarlama davranışlarını belirlemek için kullanılır. Yuvarlama modu için çift sayı ondalık 0,5 parçasıysa yuvarlama en yakın, yuvarlak varsayılandır. Çünkü `__m128` yapısı bir XMM kaydı, bu iç alır, XMM kasadan bir değeri temsil eder ve sistem belleği yazar.  
  
 Bu yordam yalnızca bir iç öğe olarak kullanılabilir.  
  
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
  
**END Microsoft özgü**  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [__m128d](../cpp/m128d.md)   
 [Derleyici İç Bilgileri](../intrinsics/compiler-intrinsics.md)