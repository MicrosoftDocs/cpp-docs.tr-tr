---
title: '&lt;Ayırıcılar&gt; işleçleri'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: b7429e298cdf14d727fc481db6c4a3bf8574b5e7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62377905"
---
# <a name="ltallocatorsgt-operators"></a>&lt;Ayırıcılar&gt; işleçleri

Tanımlanan genel şablon işlecini işlevleri bunlar &lt;ayırıcılar&gt;. Sınıf üye işleci işlevleri için sınıf belgelerine bakın.

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  işleç! =

Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitsizliği sınar.

```cpp
template <class Type, class Sync>
bool operator!=(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Eşitsizlik için test edilecek ayırıcı nesneleri biri.|
|*sağ*|Eşitsizlik için test edilecek ayırıcı nesneleri biri.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** ayırıcı nesneleri eşit; değilse, **false** ayırıcı nesnenin eşit olup olmadığını.

### <a name="remarks"></a>Açıklamalar

Şablon işlecini verir `!(left == right)`.

## <a name="op_eq_eq"></a>  işleç ==

Belirtilen sınıfın ayırıcı nesneleri arasındaki eşitliği sınar.

```cpp
template <class Type, class Sync>
bool operator==(
    const allocator_base<Type, Sync>& left,
    const allocator_base<Type, Sync>& right);
```

### <a name="parameters"></a>Parametreler

|Parametre|Açıklama|
|---------------|-----------------|
|*Sol*|Eşitlik için test edilecek ayırıcı nesneleri biri.|
|*sağ*|Eşitlik için test edilecek ayırıcı nesneleri biri.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** ayırıcı nesneleri eşitse; **false** ayırıcı nesneleri eşit değilse.

### <a name="remarks"></a>Açıklamalar

Bu şablon işlecini verir `left.equals(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Ayırıcılar >](../standard-library/allocators-header.md)
