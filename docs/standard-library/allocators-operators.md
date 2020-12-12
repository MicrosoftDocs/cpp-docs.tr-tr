---
description: 'Daha fazla bilgi edinin: &lt; ayrıcılar &gt; işleçleri'
title: '&lt;ayrıcılar &gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: a0289ca7b76aaddb2e6c8ed20a58a61d1be40998
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163476"
---
# <a name="ltallocatorsgt-operators"></a>&lt;ayrıcılar &gt; işleçleri

Bunlar, ayrıcılar içinde tanımlanan genel şablon işleci işlevleridir &lt; &gt; . Sınıf üyesi işleç işlevleri için sınıf belgelerine bakın.

[işleç! =](#op_neq)\
[işleç = =](#op_eq_eq)

## <a name="operator"></a><a name="op_neq"></a> işleç! =

Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Eşitsizlik için test edilecek ayırıcı nesnelerinden biri.

*Right*\
Eşitsizlik için test edilecek ayırıcı nesnelerinden biri.

### <a name="return-value"></a>Dönüş Değeri

**`true`** ayırıcı nesneleri eşitse; **`false`** ayırıcı nesneleri eşitse.

### <a name="remarks"></a>Açıklamalar

Şablon işleci döndürülür `!(left == right)` .

## <a name="operator"></a><a name="op_eq_eq"></a> işleç = =

Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Eşitlik için test edilecek ayırıcı nesnelerinden biri.

*Right*\
Eşitlik için test edilecek ayırıcı nesnelerinden biri.

### <a name="return-value"></a>Dönüş Değeri

**`true`** ayırıcı nesneler eşitse; **`false`** ayırıcı nesneleri eşitse.

### <a name="remarks"></a>Açıklamalar

Bu şablon işleci döndürür `left.equals(right)` .

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators>](allocators-header.md)
