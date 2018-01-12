---
title: fenv_access | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.fenv_access
- fenv_access_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, fenv_access
- fenv_access pragma
ms.assetid: 2ccea292-0ae4-42ce-9c67-cc189299857b
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 623c9cb9af1d7df137aa7ee92071e34ad99a6331
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fenvaccess"></a>fenv_access
(Açık) devre dışı bırakır veya bayrak testleri ve mod değişiklikleri değişebilir iyileştirmeler (Kapalı) etkinleştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma fenv_access [ON | OFF]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `fenv_access` Kapalı'dır.  
  
 Kayan nokta davranışını hakkında daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Tabi olan en iyi duruma getirme türlerini `fenv_access` şunlardır:  
  
-   Genel Genel alt ifade ortadan kaldırma  
  
-   Kod hareket  
  
-   Sabit Katlama  
  
 Diğer kayan nokta pragmaları şunlardır:  
  
-   [float_control](../preprocessor/float-control.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Örnek  
  
```  
// pragma_directive_fenv_access_x86.cpp  
// compile with: /O2  
// processor: x86  
#include <stdio.h>  
#include <float.h>   
#include <errno.h>  
#pragma fenv_access (on)  
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
```Output  
out=9.999999776482582e-003  
```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, Itanium işlemcilere için çıktı dosyaları oluşturan derleyici içindir. **/FP: kesin** el ile hesaplanıyorsa gerektiği gibi ara sonuçların nereye büyük değerler FLT_MAX (3.402823466e + 38F) hesaplanabilir daha ve toplamı sonucunda olacaktır 1.0 sonuç genişletilmiş kesinlik tutar. **/FP: katı** ilk Toplama ifadesi tutulur sonsuz üreten şekilde tutar Ara kendi kaynak duyarlık (kayan nokta) sonuçlanır.  
  
```  
// pragma_directive_fenv_access_IPF.cpp  
// compile with: /O2 /fp:precise  
// processor: IPF  
// compiling with /fp:precise prints 1.0F  
// compile with /fp:strict to print infinity  
  
#include <stdio.h>  
float arr[5] = {3.402823465e+38F,   
               3.402823462e+38F,  
               3.402823464e+38F,  
               3.402823463e+38F,  
               1.0F};  
  
int main() {  
   float sum = 0;  
   sum = arr[0] + arr[1] - arr[2] - arr[3] + arr[4];  
   printf_s("%f\n", sum);  
}  
```  
  
```Output  
1.000000  
```  
  
## <a name="example"></a>Örnek  
 Out yorum zaman `#pragma fenv_access (on)` önceki örnekten derleyici denetim modunu kullanmaz derleme zamanı değerlendirme yaptığından çıkış farklı olduğuna dikkat edin.  
  
```  
// pragma_directive_fenv_access_2.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>   
  
int main() {  
   double z, b = 0.1, t = 0.1;  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, _PC_24, _MCW_PC);  
   if (err != 0) {  
      printf_s("The function _controlfp_s failed!\n");  
      return -1;  
   }  
   z = b * t;  
   printf_s ("out=%.15e\n",z);  
}  
```  
  
```Output  
out=1.000000000000000e-002  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)