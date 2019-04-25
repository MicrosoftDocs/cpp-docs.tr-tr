---
title: Program Sonlandırmada return Deyimi (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- data types [C++], function return types
- function return types [C++], return statement
- return keyword [C++], syntax
ms.assetid: 66d002ab-5625-4b68-8446-71e1b8fcdbd8
ms.openlocfilehash: 9c7b6130ee1a0b49ab75a70d84764d3a1f8c5ef0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267619"
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