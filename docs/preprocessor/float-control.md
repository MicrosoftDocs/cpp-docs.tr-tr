---
title: float_control | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.float_control
- float_control_CPP
dev_langs:
- C++
helpviewer_keywords:
- float_control pragma
- pragmas, float_control
ms.assetid: 4f4ba5cf-3707-413e-927d-5ecdbc0a9a43
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b9b94e5b8eccdc63735c7cb25faa7eacb1e23670
ms.sourcegitcommit: d4c803bd3a684d7951bf88dcecf1f14af43ae411
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/10/2018
ms.locfileid: "42464761"
---
# <a name="floatcontrol"></a>float_control
Bir işlev için kayan nokta davranışını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
float_control( value,setting [push] | push | pop )  
```  
  
## <a name="flags"></a>Bayraklar  
 
*değer*, *ayarı* *[anında iletme]*  
Kayan nokta davranışını belirtir. *değer* olabilir `precise` veya `except`. Daha fazla bilgi için [FP (Floating-Point davranışını belirtin)](../build/reference/fp-specify-floating-point-behavior.md). *ayarı* olabilir `on` veya `off`.  
  
Varsa *değer* olduğu `precise`, ayarlarını `precise` ve `except` belirtilir. `except` yalnızca ayarlanabilir `on` olduğunda `precise` ayrıca ayarlanır `on`.  
  
İsteğe bağlı *anında iletme* belirteci eklenir, geçerli ayarını *değer* iç derleyici yığınına gönderilir.  
  
*push*  
Geçerli anında iletme **float_control** açın iç derleyici yığınındaki ayarlama  
  
*POP*  
Kaldırır **float_control** derleyici iç yığının en üstünden ayarlama ve ilgili yeni **float_control** ayarı.  
  
## <a name="remarks"></a>Açıklamalar  
 
Dışı bırakamazsınız `float_control precise` kapalı olduğunda `except` açıktır. Benzer şekilde, `precise` kapalı olduğunda açılamaz `fenv_access` açıktır. İle hızlı bir Modeli'ne katı modelden Git **float_control** pragması, aşağıdaki kodu kullanın:  
  
```  
#pragma float_control(except, off)  
#pragma fenv_access(off)  
#pragma float_control(precise, off)  
```  
  
Katı bir modeli hızlı modelden gitmek **float_control** pragması, aşağıdaki kodu kullanın:  
  
```  
#pragma float_control(precise, on)  
#pragma fenv_access(on)  
#pragma float_control(except, on)  
```  
  
Diğer kayan nokta pragmaları şunlardır:  
  
- [fenv_access](../preprocessor/fenv-access.md)  
  
- [fp_contract](../preprocessor/fp-contract.md)  
  
## <a name="example"></a>Örnek  
 
Aşağıdaki örnek, pragması kullanılarak taşma kayan nokta özel durumu yakalamak gösterilmektedir **float_control**.  
  
```cpp  
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
