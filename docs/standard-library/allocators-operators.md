---
title: '&lt;tahsisat&gt; operatörleri'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 7bc37e98ed85582cac8fc7ae21e54a6d5da9e06f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364957"
---
# <a name="ltallocatorsgt-operators"></a>&lt;tahsisat&gt; operatörleri

Bunlar &lt;ayırıcılarda tanımlanan genel şablon&gt;işleci işlevleridir. Sınıf üye işleç işlevleri için sınıf belgelerine bakın.

|||
|-|-|
|[işleç!=](#op_neq)|[işleç==](#op_eq_eq)|

## <a name="operator"></a><a name="op_neq"></a>işleç!=

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
|*Sol*|Eşitsizlik için test edilecek ayırıcı nesnelerden biri.|
|*Doğru*|Eşitsizlik için test edilecek ayırıcı nesnelerden biri.|

### <a name="return-value"></a>Dönüş Değeri

ayırıcı nesneler eşit değilse **doğru;** allocator nesneleri **eşitse false.**

### <a name="remarks"></a>Açıklamalar

Şablon işleci `!(left == right)`döndürür.

## <a name="operator"></a><a name="op_eq_eq"></a>işleç==

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
|*Sol*|Eşitlik için test edilecek ayırıcı nesnelerden biri.|
|*Doğru*|Eşitlik için test edilecek ayırıcı nesnelerden biri.|

### <a name="return-value"></a>Dönüş Değeri

ayırıcı nesneler eşitse **doğrudur;** allocator nesneleri eşit değilse **false.**

### <a name="remarks"></a>Açıklamalar

Bu şablon `left.equals(right)`işleci döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<tahsisat>](../standard-library/allocators-header.md)
