---
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1af084363fc0d6d1723a9af7b633779f92ed2b38
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450535"
---
# <a name="securescl"></a>_SECURE_SCL

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)yerine geçilen bu makro, [işaretlenmiş yineleyicilerin](../standard-library/checked-iterators.md) etkinleştirilip etkinleştirilmeyeceğini tanımlar. Varsayılan olarak, denetlenen yineleyiciler hata ayıklama yapılarında etkinleştirilir ve perakende yapılarda devre dışıdır.

> [!IMPORTANT]
> _SECURE_SCL makrosunu doğrudan kullanımı kullanım dışıdır. Bunun yerine, denetlenen Yineleyici ayarlarını denetlemek için _ıTERATOR_DEBUG_LEVEL kullanın. Daha fazla bilgi için bkz. [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

Denetlenen yineleyiciler etkinleştirildiğinde, güvenli olmayan Yineleyici kullanımı bir çalışma zamanı hatasına neden olur ve program sonlandırılır. Denetlenen yineleyiciler etkinleştirmek için _ıTERATOR_DEBUG_LEVEL öğesini 1 veya 2 olarak ayarlayın. Bu, bir _SECURE_SCL ayarı olan 1 veya etkin olarak eşdeğerdir:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Denetlenen yineleyiciler devre dışı bırakmak için _ıTERATOR_DEBUG_LEVEL ' ı 0 olarak ayarlayın. Bu 0 ' ın _SECURE_SCL ayarına eşdeğerdir veya devre dışı bırakılır:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Denetlenen yineleyiciler hakkında uyarıların devre dışı bırakılması hakkında daha fazla bilgi için, bkz. [_Scl_secure_no_uyarılar](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>Ayrıca bkz.

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[İşaretli yineleyiciler](../standard-library/checked-iterators.md)\
[Hata ayıklama Yineleyici desteği](../standard-library/debug-iterator-support.md)\
[Güvenli Kitaplıklar: C++ Standart Kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)
