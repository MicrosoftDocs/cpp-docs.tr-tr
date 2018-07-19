---
title: Program sonlandırma (C++) return deyimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb594eb10e8068d5f5b3ed124d5e77b48ced728e
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37947998"
---
# <a name="return-statement-in-program-termination-c"></a>Program Sonlandırmada return Deyimi (C++)
Veren bir `return` deyimden **ana** çağırmakla işlevsel olarak eşdeğerdir **çıkmak** işlevi. Aşağıdaki örnek göz önünde bulundurun:  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 **Çıkmak** ve **dönüş** önceki örnekte deyimleri aynı işleve sahiptir. Ancak, C++ işlevleri farklı dönüş türlerine, gerektirir **void** bir değer döndürür. **Dönüş** ifadesi bir değer döndürmek verir `main`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Sonlandırma](../cpp/program-termination.md)