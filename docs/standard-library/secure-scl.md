---
description: 'Hakkında daha fazla bilgi edinin: _SECURE_SCL'
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1a0e32ada449709a60eb601138ce0bb8b7ae9123
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197107"
---
# <a name="_secure_scl"></a>_SECURE_SCL

Yerine [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), bu makro [denetlenmiş yineleyicilerin](../standard-library/checked-iterators.md) etkinleştirilip etkinleştirilmeyeceğini tanımlar. Varsayılan olarak, denetlenen yineleyiciler hata ayıklama yapılarında etkinleştirilir ve perakende yapılarda devre dışıdır.

> [!IMPORTANT]
> _SECURE_SCL makrosunun doğrudan kullanımı kullanım dışıdır. Bunun yerine, denetlenen Yineleyici ayarlarını denetlemek için _ITERATOR_DEBUG_LEVEL kullanın. Daha fazla bilgi için bkz. [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Denetlenen yineleyiciler etkinleştirildiğinde, güvenli olmayan Yineleyici kullanımı bir çalışma zamanı hatasına neden olur ve program sonlandırılır. Denetlenen yineleyiciler etkinleştirmek için _ITERATOR_DEBUG_LEVEL 1 veya 2 ' ye ayarlayın. Bu, 1 _SECURE_SCL ayarına eşittir veya etkinleştirilir:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Denetlenen yineleyiciler devre dışı bırakmak için _ITERATOR_DEBUG_LEVEL 0 olarak ayarlayın. Bu, 0 veya devre dışı _SECURE_SCL ayarına eşdeğerdir:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Denetlenen yineleyiciler hakkında uyarıların devre dışı bırakılması hakkında daha fazla bilgi için bkz. [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>Ayrıca bkz.

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[İşaretli yineleyiciler](../standard-library/checked-iterators.md)\
[Hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md)\
[Güvenli Kitaplıklar: C++ standart kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)
