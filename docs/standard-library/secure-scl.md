---
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: dcfaee2906136dffbe79a49f089a079104112e78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295753"
---
# <a name="securescl"></a>_SECURE_SCL

Yerine geçen [_ıterator_debug_level](../standard-library/iterator-debug-level.md), bu makroyu tanımlar olup olmadığını [Checked Iterators](../standard-library/checked-iterators.md) etkinleştirilir. Varsayılan olarak işaretli yineleyiciler hata ayıklama yapılarında etkinleştirildiğinden ve perakende sürümlerde devre dışı.

> [!IMPORTANT]
> Doğrudan kullanımını _SECURE_SCL makrosu kullanım dışıdır. Bunun yerine, yineleyici ayarlarını kullanıma denetlemek _ıterator_debug_level kullanın. Daha fazla bilgi için [_ıterator_debug_level](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Açıklamalar

İşaretli yineleyiciler etkinleştirilirse, güvenli olmayan yineleyici kullanımı bir çalışma zamanı hatasına neden olur ve program sonlandırılır. İşaretli yineleyiciler etkinleştirmek için 1 veya 2'ye _ıterator_debug_level ayarlayın. _SECURE_SCL 1 ayarı için eşdeğer olan veya etkin:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

İşaretli yineleyiciler devre dışı bırakmak için _ıterator_debug_level 0 olarak ayarlayın. 0 _SECURE_SCL ayarı için eşdeğerdir veya devre dışı:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Denetlenen yineleyiciler hakkında uyarılar devre dışı bırakma hakkında daha fazla bilgi için bkz: [_scl_secure_no_warnıngs](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>Ayrıca bkz.

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Denetlenmiş Yineleyiciler](../standard-library/checked-iterators.md)<br/>
[Hata Ayıklama Yineleyici Desteği](../standard-library/debug-iterator-support.md)<br/>
[Güvenli Kitaplıklar: C++ Standart Kitaplığı](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
