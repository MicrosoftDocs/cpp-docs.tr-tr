---
title: float_control | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs: C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 821890c7fdb719b5ab320588476bd1ebb73793ea
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="floatcontrol"></a>float_control
Bir işlev için kayan nokta davranışını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>Bayraklar  
 `value`, `setting` **[itme]**  
 Kayan nokta davranışını belirtir. `value`olabilir **kesin** veya **dışında**. Daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../build/reference/fp-specify-floating-point-behavior.md). `setting`ya da olabilir **üzerinde** veya **devre dışı**.  
  
 Varsa `value` olan **kesin**, ayarlarını **kesin** ve **dışında** belirtilir. **dışında** yalnızca ayarlanabilir **üzerinde** zaman **kesin** de ayarlamak **üzerinde**.  
  
 Varsa isteğe bağlı **anında iletme** belirteci eklenir, geçerli ayarını `value` derleyici iç yığına gönderilir.  
  
 **push**  
 Geçerli anında `float_control` açın iç derleyici yığını ayarlama  
  
 **POP**  
 Kaldırır `float_control` iç derleyici yığını üstten ayarlama ve yapıyorsa yeni `float_control` ayarı.  
  
## <a name="remarks"></a>Açıklamalar  
 Dışı bırakamazsınız `float_control precise` kapalı olduğunda **dışında** açıktır. Benzer şekilde, **kesin** devre dışı açılamaz `fenv_access` açıktır. Hızlı bir modelle katı modelden gitmek `float_control` pragma, aşağıdaki kodu kullanın:  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
// The following line is needed on Itanium processors  
#pragma fp_contract(on)  
```  
  
 Hızlı modelden ile sıkı bir model gitmek için `float_control` pragma, aşağıdaki kodu kullanın:  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
// The following line is needed on Itanium processors.  
#pragma fp_contract(off)  
```  
  
 Diğer kayan nokta pragmaları şunlardır:  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek pragma kullanarak taşma kayan nokta özel durumu yakalayın gösterilmektedir `float_control`.  
  
```  
// pragma_directive_float_control.cpp  
// compile with: /EHa  
#include <stdio.h>  
#include <float.h>  
  
double func( ) {  
   return 1.1e75;  
}  
  
#pragma float_control (except,on)  
  
int main( ) {  
   float u[1];  
   unsigned int currentControl;  
   errno_t err;  
  
   err = _controlfp_s(&currentControl, ~_EM_OVERFLOW, _MCW_EM);  
   if (err != 0)  
      printf_s("_controlfp_s failed!\n");  
  
   try  {  
      u[0] = func();  
      printf_s ("Fail");     
      return(1);  
   }   
  
   catch (...)  {  
      printf_s ("Pass");  
      return(0);  
   }  
}  
```  
  
```Output  
Pass  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)