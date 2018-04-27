---
title: _HAS_ITERATOR_DEBUGGING | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
dev_langs:
- C++
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1e6cf83c0877c351a2bf247a557f3df53e9c1f22
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
