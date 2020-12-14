---
description: 'Hakkında daha fazla bilgi edinin: _HAS_ITERATOR_DEBUGGING'
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: ee1765739624fe7c6fccd41ff84f455d5f90cc42
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231998"
---
# <a name="_has_iterator_debugging"></a>_HAS_ITERATOR_DEBUGGING

Yerine [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), bu makro Yineleyici hata ayıklama özelliğinin bir hata ayıklama derlemesinde etkinleştirilip etkinleştirilmeyeceğini tanımlar. Varsayılan olarak, Yineleyici hata ayıklama, Retail derlemelerde hata ayıklama yapılarında etkinleştirilir ve devre dışı bırakılır. Daha fazla bilgi için bkz. [hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> _HAS_ITERATOR_DEBUGGING makrosunun doğrudan kullanımı kullanım dışıdır. Bunun yerine, Yineleyici hata ayıklama ayarlarını denetlemek için _ITERATOR_DEBUG_LEVEL kullanın. Daha fazla bilgi için bkz. [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında Yineleyici hata ayıklamayı etkinleştirmek için, _ITERATOR_DEBUG_LEVEL 2 olarak ayarlayın. Bu, 1 _HAS_ITERATOR_DEBUGGING ayarına eşittir veya etkinleştirilir:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL, perakende yapılarında 2 ' ye (ve _HAS_ITERATOR_DEBUGGING 1 ' e ayarlanamaz) ayarlanamaz.

Hata ayıklama derlemelerde hata ayıklama yineleyiciler devre dışı bırakmak için _ITERATOR_DEBUG_LEVEL 0 veya 1 olarak ayarlayın. Bu, 0 veya devre dışı _HAS_ITERATOR_DEBUGGING ayarına eşdeğerdir:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Ayrıca bkz.

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md)\
[İşaretli yineleyiciler](../standard-library/checked-iterators.md)\
[Güvenli Kitaplıklar: C++ standart kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)
