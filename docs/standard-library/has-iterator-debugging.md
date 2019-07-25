---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: a1e3017ed7c6def18ce02d99dc8253b69c11ab58
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448829"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)yerine geçilen bu makro, bir hata ayıklama derlemesinde Yineleyici hata ayıklama özelliğinin etkinleştirilip etkinleştirilmeyeceğini tanımlar. Varsayılan olarak, Yineleyici hata ayıklama, Retail derlemelerde hata ayıklama yapılarında etkinleştirilir ve devre dışı bırakılır. Daha fazla bilgi için bkz. [hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> _HAS_ıTERATOR_DEBUGGING makrosunu doğrudan kullanmak kullanım dışıdır. Bunun yerine, Yineleyici hata ayıklama ayarlarını denetlemek için _ıTERATOR_DEBUG_LEVEL kullanın. Daha fazla bilgi için bkz. [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında Yineleyici hata ayıklamayı etkinleştirmek için _ıTERATOR_DEBUG_LEVEL öğesini 2 olarak ayarlayın. Bu, bir _HAS_ıTERATOR_DEBUGGING ayarı olan 1 veya etkin bir değer ile eşdeğerdir:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL, perakende yapılarında 2 ' ye (ve _HAS_ıTERATOR_DEBUGGING) 1 olarak ayarlanamaz) ayarlanamaz.

Hata ayıklama yapılarında hata ayıklamayı yineleyiciler devre dışı bırakmak için _ıTERATOR_DEBUG_LEVEL öğesini 0 veya 1 olarak ayarlayın. Bu, 0 veya devre dışı bırakılmış bir _HAS_ıTERATOR_DEBUGGING ayarına eşdeğerdir:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Ayrıca bkz.

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md)\
[İşaretli yineleyiciler](../standard-library/checked-iterators.md)\
[Güvenli Kitaplıklar: C++ Standart Kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)
