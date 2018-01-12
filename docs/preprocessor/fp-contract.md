---
title: fp_contract | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc-pragma.fp_contract
- fp_contract_CPP
dev_langs: C++
helpviewer_keywords:
- pragmas, fp_contract
- fp_contract pragma
ms.assetid: 15b97338-6680-4287-ba2a-2dccc5b2ccf5
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4feb098555168e07641db30401f23aba2291fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="fpcontract"></a>fp_contract
Kayan nokta kısaltmanın gerçekleşip gerçekleşmeyeceğini belirler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#pragma fp_contract [ON | OFF]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak `fp_contract` açıktır.  
  
 Kayan nokta davranışını hakkında daha fazla bilgi için bkz: [/fp (Floating-Point davranış belirtin)](../build/reference/fp-specify-floating-point-behavior.md).  
  
 Diğer kayan nokta pragmaları şunlardır:  
  
-   [fenv_access](../preprocessor/fenv-access.md)  
  
-   [float_control](../preprocessor/float-control.md)  
  
## <a name="example"></a>Örnek  
 Bu örnekten oluşturulan kodu Sigortalı Çarp ekleme kullanmayan (**fma**) Itanium işlemcilere yönerge. Çıkarırsanız `#pragma fp_contract (off)`, oluşturulan kod kullanacağı **fma** yönergesi.  
  
```  
// pragma_directive_fp_contract.cpp  
// compile with: /O2  
#include <stdio.h>  
#include <float.h>  
  
#pragma fp_contract (off)   
  
int main() {  
   double z, b, t;  
  
   for (int i = 0; i < 10; i++) {  
      b = i * 5.5;  
      t = i * 56.025;  
      _set_controlfp(_PC_24, _MCW_PC);  
  
      z = t * i + b;  
      printf_s ("out=%.15e\n", z);  
   }  
}  
```  
  
```Output  
out=0.000000000000000e+000  
out=6.152500152587891e+001  
out=2.351000061035156e+002  
out=5.207249755859375e+002  
out=9.184000244140625e+002  
out=1.428125000000000e+003  
out=2.049899902343750e+003  
out=2.783724853515625e+003  
out=3.629600097656250e+003  
out=4.587524902343750e+003  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)