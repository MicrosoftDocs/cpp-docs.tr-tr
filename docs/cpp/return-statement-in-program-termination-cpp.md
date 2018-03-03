---
title: "Program sonlandırma (C++) return deyimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9a9e97c0ee52094cd3f0ccbb36c0da8b3b04c630
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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