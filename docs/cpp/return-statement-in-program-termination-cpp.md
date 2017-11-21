---
title: "Program sonlandırma (C++) return deyimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb3555ecb80b2f6bc8663325b500ffb2eb317ce3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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
 [Program sonlandırma](../cpp/program-termination.md)