---
title: Karakterleştirme işleci (#@) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '#@'
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d86c49c8d7d0cda91ba2415167cc79c810a96b3d
ms.sourcegitcommit: d10a2382832373b900b1780e1190ab104175397f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/06/2018
ms.locfileid: "43895311"
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