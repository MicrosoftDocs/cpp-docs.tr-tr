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
ms.openlocfilehash: c9acc9b9872e096cd441b950632c341e975fecb8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62403535"
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

## <a name="see-also"></a>Ayrıca bkz.

[Ön İşlemci İşleçleri](../preprocessor/preprocessor-operators.md)