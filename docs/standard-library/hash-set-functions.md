---
title: '&lt;hash_set&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 083d928198d8d83d8a56d8a74a6204e94c86aa67
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33846291"
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; işlevleri

|||
|-|-|
|[Değiştirme](#swap)|[Swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a>  Değiştirme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`right` Öğeleri takas için sağlama hash_set veya öğeleri olan hash_set olanlar değiştirilmek üzere hash_set `left`.

`left` Öğeleri olan hash_set olanlar değiştirilmek üzere hash_set `right`.

### <a name="remarks"></a>Açıklamalar

`swap` Şablon işlevi olan bir algoritma özelleştirilmiş üye işlevini yürütmek için kapsayıcı sınıfı hash_set `left.` [takas](../standard-library/hash-set-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir sürümü olan şablon işlevi

**Şablon \<sınıfı T > void takas (T & T &),**

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [hash_set::swap](../standard-library/hash-set-class.md#swap) şablonu sürümünü kullanan bir örnek `swap`.

## <a name="swap_hash_multiset"></a>  Swap (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).

İki hash_multisets öğelerini değiş tokuş eder.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`right` Öğeleri takas için sağlama hash_multiset veya öğeleri olan hash_multiset olanlar değiştirilmek üzere hash_multiset `left`.

`left` Öğeleri olan hash_multiset olanlar değiştirilmek üzere hash_multiset `right`.

### <a name="remarks"></a>Açıklamalar

`swap` Şablon işlevi olan bir algoritma özelleştirilmiş üye işlevini yürütmek için kapsayıcı sınıfı hash_multiset `left.` [takas](../standard-library/hash-multiset-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir sürümü olan şablon işlevi

**Şablon \<sınıfı T > void takas (T & T &),**

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) şablonu sürümünü kullanan bir örnek `swap`.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_set>](../standard-library/hash-set.md)<br/>
