---
title: _Noreturn anahtar sözcüğü ve noreturn makrosu (C11)
description: '`_Noreturn`Anahtar sözcüğü ve `noreturn` makroları açıklar.'
ms.date: 10/16/2020
f1_keywords:
- _Noreturn_c
- noreturn
helpviewer_keywords:
- keywords [C]
ms.openlocfilehash: f876485b5be497688c5cf1dd8fca206d08560de0
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/19/2020
ms.locfileid: "92182818"
---
# <a name="_noreturn-keyword-and-noreturn-macro-c11"></a>`_Noreturn` anahtar sözcük ve `noreturn` makro (C11)

`_Noreturn`Anahtar sözcüğü C11 içinde tanıtılmıştır. Derleyiciye uyguladığı işlevin dönmediğini söyler. Derleyici, bir işleve yapılan çağrıyı izleyen kodun ulaşılamaz olduğunu bilir `_Noreturn` .

`noreturn`<stdnoreturn. h> içinde belirtilen kullanışlı bir makro, `_Noreturn` anahtar sözcüğüyle eşlenir.

`_Noreturn`(Veya eşdeğeri) kullanmanın birincil avantajları, `noreturn` gelecekteki okuyucular için koddaki işlevin açık olmasını ve istem dışı erişilemeyen kodu algılamaktır.

## <a name="example-using-noreturn-macro-and-_noreturn-keyword"></a>`noreturn`Makro ve `_Noreturn ` anahtar sözcüğü kullanan örnek

Aşağıdaki örnek, `_Noreturn` anahtar sözcüğünü ve eşdeğer makroyu gösterir `noreturn` .

IntelliSense, yoksayabilirsiniz bir hata oluşturabilir, bu, `E0065` `noreturn` yoksayabileceğiniz makroyu kullanıyorsanız. Bu, örneği çalıştırmayı engellemez.

```C
// Compile with Warning Level4 (/W4) and /std:c11
#include <stdio.h>
#include <stdlib.h>
#include <stdnoreturn.h>

noreturn void fatal_error(void)
{
    exit(3);
}

_Noreturn void not_coming_back(void)
{
    puts("There's no coming back");
    fatal_error();
    return; // warning C4645 - function declared with noreturn has a return statement
}

void done(void)
{
    puts("We'll never get here");
}

int main(void)
{
    not_coming_back();
    done(); // warning c4702 - unreachable code

    return 0;
}
```

## <a name="requirements"></a>Gereksinimler

|Makroya|Gerekli başlık|
|-------------|---------------------|
|**`noreturn`**|\<stdnoreturn.h>|

## <a name="see-also"></a>Ayrıca bkz.

[/STD (dil standart sürümünü belirt)](../build/reference/std-specify-language-standard-version.md)\
[/W4 (uyarı düzeyini belirtin)](../build/reference/compiler-option-warning-level.md) 
 [C4702 uyarısı](../error-messages\compiler-warnings\compiler-warning-level-4-c4702.md)