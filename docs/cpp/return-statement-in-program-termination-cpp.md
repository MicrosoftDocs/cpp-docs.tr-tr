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
ms.openlocfilehash: 61d09c1b3aaea799c227686436486efa48fc7857
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="return-statement-in-program-termination-c"></a>Program Sonlandırmada return Deyimi (C++)
Sertifika veren bir `return` from deyimi **ana** arama için işlevsel olarak eşdeğerdir **çıkmak** işlevi. Aşağıdaki örnek göz önünde bulundurun:  
  
```  
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 **Çıkmak** ve `return` deyimleri önceki örnekte işlevsel olarak aynıdır. Ancak C++, `void` türünden farklı dönüş türlerine sahip işlevlerin bir değer döndürmesini gerektirir. `return` Deyimi arasında bir değer döndürmek verir **ana**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Program Sonlandırma](../cpp/program-termination.md)