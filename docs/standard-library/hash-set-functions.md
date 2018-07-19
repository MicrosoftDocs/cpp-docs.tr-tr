---
title: '&lt;hash_set&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: ad8041ff6a4abab84272d2bbbdee290bfce4eff6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961883"
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; işlevleri

|||
|-|-|
|[değiştirme](#swap)|[Swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a>  değiştirme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini birbiriyle değiştirir.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*doğru* değiştirilecek öğeleri sağlayan hash_set veya öğeleri olan hash_set olanlar değiştirilecek hash_set *sol*.

*Sol* öğeleri olan hash_set olanlar değiştirilecek hash_set *doğru*.

### <a name="remarks"></a>Açıklamalar

`swap` Şablonu işlev, bir algoritma özel üye işlevini yürütmek için kapsayıcı sınıfı hash_set `left.` [takas](../standard-library/hash-set-class.md#swap)(`right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Genel bir sürümü olan şablon işlevi

**Şablon \<sınıfı T > void takas (T &, T &),**

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [hash_set::swap](../standard-library/hash-set-class.md#swap) şablon sürümünü kullanan bir örnek için `swap`.

## <a name="swap_hash_multiset"></a>  Swap (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İki hash_multisets öğelerini birbiriyle değiştirir.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*doğru* değiştirilecek öğeleri sağlayan hash_multiset veya öğeleri olan hash_multiset olanlar değiştirilecek hash_multiset *sol*.

*Sol* öğeleri olan hash_multiset olanlar değiştirilecek hash_multiset *doğru*.

### <a name="remarks"></a>Açıklamalar

`swap` Şablonu işlev, bir algoritma özel üye işlevini yürütmek için kapsayıcı sınıfı hash_multiset `left.` [takas](../standard-library/hash-multiset-class.md#swap)(`right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Genel bir sürümü olan şablon işlevi

**Şablon \<sınıfı T > void takas (T &, T &),**

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) şablon sürümünü kullanan bir örnek için `swap`.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_set>](../standard-library/hash-set.md)<br/>
