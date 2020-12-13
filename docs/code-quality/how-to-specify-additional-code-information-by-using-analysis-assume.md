---
description: 'Hakkında daha fazla bilgi edinin: nasıl yapılır: _Analysis_assume kullanarak ek kod bilgileri belirtme'
title: Kod Analizi ipuçları için _Analysis_assume kullanma
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
ms.openlocfilehash: 1960fae929f1bd0ffbac4979b76541fd0d396e42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97151560"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume"></a>Nasıl yapılır: _Analysis_assume kullanarak ek kod bilgileri belirtme

Analiz işleminin ve uyarıların azaltılmasına yardımcı olacak C/C++ kodu için kod analizi aracına yönelik ipuçları sağlayabilirsiniz. Ek bilgi sağlamak için aşağıdaki işlevi kullanın:

`_Analysis_assume(`  `expr`  `)`

`expr` -true olarak değerlendirilme kabul edilen herhangi bir ifade.

Kod Analizi Aracı, ifade tarafından temsil edilen koşulun işlevin göründüğü noktada doğru olduğunu varsayar ve örneğin bir değişkene atama yaparak ifade değiştirilene kadar doğru kalır.

> [!NOTE]
> `_Analysis_assume` kod iyileştirmesini etkilemez. Kod Analizi aracının dışında, `_Analysis_assume` bir op olarak tanımlanır.

## <a name="example"></a>Örnek

Aşağıdaki kod, `_Analysis_assume` Kod Analizi uyarı [C6388](../code-quality/c6388.md)düzeltmek için kullanır:

```cpp
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>Ayrıca bkz.

- [__assume](../intrinsics/assume.md)
