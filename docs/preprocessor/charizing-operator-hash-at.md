---
description: 'Daha fazla bilgi için: Charize işleci (# @)'
title: Karakter haline getirme işleci (#@)
ms.date: 08/29/2019
f1_keywords:
- '#@'
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
ms.openlocfilehash: 6d04aa24c75153957bd6fd09824f4e94e36fd38f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300872"
---
# <a name="charizing-operator-"></a>Karakter haline getirme işleci (#@)

**Microsoft'a Özgü**

Charize işleci yalnızca makro bağımsız değişkenleriyle kullanılabilir. `#@`Makro tanımındaki bir biçimsel parametreden önce geliyorsa, gerçek bağımsız değişken tek tırnak işaretleri içine alınır ve makro genişletildiğinde bir karakter olarak kabul edilir. Örneğin:

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

Tek tırnak karakteri (), `'` charize işleci ile birlikte kullanılamaz.

**SON Microsoft 'a özgü**

## <a name="see-also"></a>Ayrıca bkz.

[Ön işlemci işleçleri](../preprocessor/preprocessor-operators.md)
