---
title: '&lt;ayrıcılar&gt; işleçler'
ms.date: 11/04/2016
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: b7429e298cdf14d727fc481db6c4a3bf8574b5e7
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78875964"
---
# <a name="ltallocatorsgt-operators"></a>&lt;ayrıcılar&gt; işleçler

Bunlar, &lt;ayırıcıları&gt;tanımlanan genel şablon işleci işlevleridir. Sınıf üyesi işleç işlevleri için sınıf belgelerine bakın.

|||
|-|-|
|[operator!=](#op_neq)|[işleç = =](#op_eq_eq)|

## <a name="op_neq"></a>işleç! =

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
|*tarafta*|Eşitsizlik için test edilecek ayırıcı nesnelerinden biri.|
|*Right*|Eşitsizlik için test edilecek ayırıcı nesnelerinden biri.|

### <a name="return-value"></a>Dönüş Değeri

ayırıcı nesneleri eşitse **true** ; ayırıcı nesneleri eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Şablon işleci `!(left == right)`döndürür.

## <a name="op_eq_eq"></a>işleç = =

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
|*tarafta*|Eşitlik için test edilecek ayırıcı nesnelerinden biri.|
|*Right*|Eşitlik için test edilecek ayırıcı nesnelerinden biri.|

### <a name="return-value"></a>Dönüş Değeri

ayırıcı nesneleri eşitse **true** ; ayırıcı nesneleri eşitse **false** .

### <a name="remarks"></a>Açıklamalar

Bu şablon işleci `left.equals(right)`döndürür.

## <a name="see-also"></a>Ayrıca bkz.

[\<ayrıcılar >](../standard-library/allocators-header.md)
