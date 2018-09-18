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
ms.openlocfilehash: cfcf65258767178c0f74f63ca6e938e1d940e3be
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46061142"
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