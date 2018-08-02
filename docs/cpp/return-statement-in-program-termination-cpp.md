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
ms.openlocfilehash: 6c08edff8237462cbc2c55dc5541e3da663ed0a3
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461119"
---
# <a name="return-statement-in-program-termination-c"></a>Program Sonlandırmada return Deyimi (C++)
Veren bir **dönüş** deyimden `main` çağırmakla işlevsel olarak eşdeğerdir `exit` işlevi. Aşağıdaki örnek göz önünde bulundurun:  
  
```cpp 
// return_statement.cpp  
#include <stdlib.h>  
int main()  
{  
    exit( 3 );  
    return 3;  
}  
```  
  
 `exit` Ve **dönüş** önceki örnekte deyimleri aynı işleve sahiptir. Ancak, C++ işlevleri farklı dönüş türlerine, gerektirir **void** bir değer döndürür. **Dönüş** ifadesi bir değer döndürmek verir `main`.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Program Sonlandırma](../cpp/program-termination.md)