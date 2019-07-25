---
title: '&lt;hash_set&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 2fbc05c16ba6629397bbb07bab30cb9315a16e1f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448601"
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; işlevleri

|||
|-|-|
|[Kur](#swap)|[swap (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a>Kur

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan hash_set veya öğeleri hash_set *Soldakilerle*değiş tokuş edilecek hash_set.

*tarafta*\
Öğeleri hash_set *Right*ile değiştirilecek olan hash_set.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left.` [Swap](../standard-library/hash-set-class.md#swap)(`right`) üye işlevini yürütmek için hash_set kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır. `swap` Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

**Şablon \<sınıfı T > void takas (t &, t &),**

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünü `swap`kullanan bir örnek için [hash_set:: Swap](../standard-library/hash-set-class.md#swap) üye sınıfının kod örneğine bakın.

## <a name="swap_hash_multiset"></a>swap (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki hash_multisets öğelerini değiş tokuş eder.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan hash_multiset veya öğeleri hash_multiset *Soldakilerle*değiş tokuş edilecek hash_multiset.

*tarafta*\
Öğeleri hash_multiset *Right*ile değiştirilecek olan hash_multiset.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left.` [Swap](../standard-library/hash-multiset-class.md#swap)(`right`) üye işlevini yürütmek için hash_multiset kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır. `swap` Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

**Şablon \<sınıfı T > void takas (t &, t &),**

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünü `swap`kullanan bir örnek için [hash_multiset:: Swap](../standard-library/hash-multiset-class.md#swap) üye sınıfının kod örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_set>](../standard-library/hash-set.md)
