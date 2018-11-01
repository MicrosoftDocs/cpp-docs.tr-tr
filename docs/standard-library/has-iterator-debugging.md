---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: 339c32f9b487db2e318f8763ac01a0d155fc1dc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50575883"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Yerine geçen [_ıterator_debug_level](../standard-library/iterator-debug-level.md), hata ayıklama derlemesinde hata ayıklama özelliği yineleyici etkinleştirilip etkinleştirilmeyeceğini Bu makroyu tanımlar. Varsayılan olarak, hata ayıklama yineleyici hata ayıklama yapılarında etkinleştirilir ve perakende sürümlerde devre dışı. Daha fazla bilgi için [Debug Iterator Support](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> Doğrudan kullanımını _HAS_ITERATOR_DEBUGGING makrosu kullanım dışıdır. Bunun yerine, yineleyici hata ayıklama ayarlarını denetlemek _ıterator_debug_level kullanın. Daha fazla bilgi için [_ıterator_debug_level](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında hata ayıklama yineleyici etkinleştirmek için _ıterator_debug_level 2 olarak ayarlayın. 1 _HAS_ITERATOR_DEBUGGING ayarı için eşdeğer olan veya etkin:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_Iterator_debug_level 2 ayarlanamaz (ve _HAS_ITERATOR_DEBUGGING 1 için ayarlanamaz) perakende oluşturur.

Hata ayıklama yapılarında hata ayıklama yineleyiciler devre dışı bırakmak için _ıterator_debug_level 0 veya 1 olarak ayarlayın. 0 _HAS_ITERATOR_DEBUGGING ayarı için eşdeğerdir veya devre dışı:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Ayrıca bkz.

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)<br/>
[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)<br/>
[Güvenli Kitaplıklar: C++ Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
