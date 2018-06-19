---
title: _HAS_ITERATOR_DEBUGGING | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ab2de61df8c4e22b1955e9fd4798b5128a3e12be
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845901"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Yerine geçen [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), bu makrosu özelliği hata ayıklama yineleyici hata ayıklama derlemede etkin olup olmadığını tanımlar. Varsayılan olarak, hata ayıklama yineleyici hata ayıklama derlemelerinde etkin ve perakende yapılarında devre dışı. Daha fazla bilgi için bkz: [hata ayıklama yineleyici desteği](../standard-library/debug-iterator-support.md).

> [!IMPORTANT]
> Doğrudan kullanımını `_HAS_ITERATOR_DEBUGGING` makrosu kullanım dışıdır. Bunun yerine, kullanın `_ITERATOR_DEBUG_LEVEL` denetlemek için yineleyici hata ayıklama, ayarları. Daha fazla bilgi için bkz: [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Yineleyici hata ayıklama derlemelerinde hata ayıklamayı etkinleştirmek için ayarlanmış `_ITERATOR_DEBUG_LEVEL` 2. Bu eşdeğer olan bir `_HAS_ITERATOR_DEBUGGING` ayar 1 ya da etkin:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

`_ITERATOR_DEBUG_LEVEL` 2 olarak ayarlanmış (ve `_HAS_ITERATOR_DEBUGGING` 1 olarak ayarlayın) perakende oluşturur.

Hata ayıklama yineleyiciler hata ayıklama derlemelerinde devre dışı bırakmak için ayarlanmış `_ITERATOR_DEBUG_LEVEL` için 0 veya 1. Bu eşdeğer olan bir `_HAS_ITERATOR_DEBUGGING` 0 ya da devre dışı ayarlama:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>Ayrıca bkz.

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)<br/>
[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)<br/>
[Güvenli Kitaplıklar: C++ Standart Kitaplık](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
