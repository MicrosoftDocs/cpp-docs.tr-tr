---
title: Karakterleştirme İşleci (#@)
ms.date: 11/04/2016
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 7259487a3289173bc77517c8c616638c370041c4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50568352"
---
# <a name="charizing-operator-"></a>Karakterleştirme İşleci (#@)
**Microsoft'a özgü**

Karakter haline getirme işleci yalnızca makrolar bağımsız değişkenlerle kullanılabilir. Varsa `#@` biçimsel parametre önündeki Makro tanımında gerçek bağımsız değişkeni tek tırnak işareti içine alınmış ve makro genişletildiğinde bir karakter olarak kabul edilir. Örneğin:

```
#define makechar(x)  #@x
```

deyim neden olur

```
a = makechar(b);
```

değerine genişletilmesi

```
a = 'b';
```

Tek tırnak karakteri karakter haline getirme işleci ile kullanılamaz.

**END Microsoft özgü**

## <a name="see-also"></a>Ayrıca Bkz.

[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)