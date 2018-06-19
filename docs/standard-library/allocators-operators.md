---
title: '&lt;allocators&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
ms.openlocfilehash: 25e40157c1872df3e970bb234accab5c487c6287
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33841134"
---
# <a name="ltallocatorsgt-operators"></a>&lt;allocators&gt; işleçleri

Tanımlanan genel şablon işleci işlevleri bunlar &lt;allocators&gt;. Sınıf üyesi işleci işlevler için sınıf belgelerine bakın.

|||
|-|-|
|[operator!=](#op_neq)|[operator==](#op_eq_eq)|

## <a name="op_neq"></a>  operator! =

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
|`left`|Eşitsizlik için sınanacak ayırıcısı nesnelerinden biri.|
|`right`|Eşitsizlik için sınanacak ayırıcısı nesnelerinden biri.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** ayırıcı nesneleri eşit; değilse **false** ayırıcı nesneleri eşit olması durumunda.

### <a name="remarks"></a>Açıklamalar

Şablon işleci döndürür `!(left == right)`.

## <a name="op_eq_eq"></a>  operator ==

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
|`left`|Bir ayırıcı nesnenin eşitlik için test edilmelidir.|
|`right`|Bir ayırıcı nesnenin eşitlik için test edilmelidir.|

### <a name="return-value"></a>Dönüş Değeri

**doğru** ayırıcı nesneleri eşitse; **false** ayırıcı nesneleri eşit değilse.

### <a name="remarks"></a>Açıklamalar

Bu şablon işleci döndürür `left.equals(right)`.

## <a name="see-also"></a>Ayrıca bkz.

[\<allocators >](../standard-library/allocators-header.md)
