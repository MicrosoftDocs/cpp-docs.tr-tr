---
title: '&lt;allocators&gt; işleçleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- allocators/std::operator!=
- allocators/std::operator==
dev_langs:
- C++
ms.assetid: b55d67cb-3c69-46bf-ad40-e845fb096c4e
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: d6d69d07c8b16d2749c7ac62eb290f180b1e1b09
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
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
