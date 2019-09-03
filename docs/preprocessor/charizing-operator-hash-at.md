---
title: Karakterleştirme işleci (#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: cb2a4e07287edf5ed2d0850ec7d870c8ef307879
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/03/2019
ms.locfileid: "70218537"
---
# <a name="charizing-operator-"></a>Karakterleştirme işleci (#@)

**Microsoft 'a özgü**

Charize işleci yalnızca makro bağımsız değişkenleriyle kullanılabilir. Makro `#@` tanımındaki bir biçimsel parametreden önce geliyorsa, gerçek bağımsız değişken tek tırnak işaretleri içine alınır ve makro genişletildiğinde bir karakter olarak kabul edilir. Örneğin:

```cpp
#define makechar(x)  #@x
```

ifadeye neden olur

```cpp
a = makechar(b);
```

genişletilecek

```cpp
a = 'b';
```

Tek tırnak karakteri (`'`), charize işleci ile birlikte kullanılamaz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Önişlemci işleçleri](../preprocessor/preprocessor-operators.md)
