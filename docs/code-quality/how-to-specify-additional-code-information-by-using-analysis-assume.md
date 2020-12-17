---
description: _Analysis_assume_ kullanarak ek kod bilgileri belirtme hakkında daha fazla bilgi edinin.
title: Kod Analizi ipuçları için _Analysis_assume_ kullanma
ms.date: 12/16/2020
ms.topic: conceptual
f1_keywords:
- _Analysis_assume_
helpviewer_keywords:
- _Analysis_assume_
ms.openlocfilehash: f4244a896d4334cb6c5e857e63b39be0cd53b08b
ms.sourcegitcommit: 387ce22a3b0137f99cbb856a772b5a910c9eba99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97645130"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume_"></a>Kullanarak ek kod bilgileri belirtme `_Analysis_assume_`

Analiz işleminin ve uyarıların azaltılmasına yardımcı olacak C/C++ kodu için kod analizi aracına yönelik ipuçları sağlayabilirsiniz. Ek bilgi sağlamak için aşağıdaki işlev makrosunu kullanın:

`_Analysis_assume( expr )`

*`expr`* -true olarak değerlendirilme kabul edilen herhangi bir ifade.

Kod Analizi Aracı, ifadenin gösterdiği koşulun *`expr`* işlevin göründüğü noktada doğru olduğunu varsayar. Ve, *`expr`* Örneğin bir değişkene atama ile değiştirilene kadar doğru kalır.

> [!NOTE]
> `_Analysis_assume_` kod iyileştirmesini etkilemez. Kod Analizi aracının dışında, `_Analysis_assume_` bir op olarak tanımlanır.

## <a name="example"></a>Örnek

Aşağıdaki kod, `_Analysis_assume_` Kod Analizi uyarı [C6388](../code-quality/c6388.md)düzeltmek için kullanır:

```cpp
#include <windows.h>
#include <codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume_(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [__assume](../intrinsics/assume.md)
