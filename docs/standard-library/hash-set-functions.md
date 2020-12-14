---
description: 'Hakkında daha fazla bilgi edinin: &lt; hash_set &gt; işlevleri'
title: '&lt;hash_set &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: 7040325f3af26052306b1ebd90f1919d96dcbf19
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231803"
---
# <a name="lthash_setgt-functions"></a>&lt;hash_set &gt; işlevleri

[Kur](#swap)\
[takas (hash_multiset)](#swap_hash_multiset)

## <a name="swap"></a><a name="swap"></a> Kur

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan hash_set veya öğeleri hash_set *kalan* değişikliklerle birlikte değiştirilecek olan hash_set.

*tarafta*\
Öğeleri hash_set *sağdakilerle* değiş tokuş edilecek hash_set.

### <a name="remarks"></a>Açıklamalar

`swap`Şablon işlevi, `left.` [Swap](../standard-library/hash-set-class.md#swap)() üye işlevini yürütmek için hash_set kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır `right` . Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

**Şablon \<class T> void takas (t&, t&),**

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünü kullanan bir örnek için [hash_set:: Swap](../standard-library/hash-set-class.md#swap) üye sınıfına ait kod örneğine bakın `swap` .

## <a name="swap-hash_multiset"></a><a name="swap_hash_multiset"></a> takas (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfıdır](../standard-library/unordered-set-class.md).

İki hash_multisets öğelerini değiş tokuş eder.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan hash_multiset veya öğeleri hash_multiset *kalan* değişikliklerle birlikte değiştirilecek olan hash_multiset.

*tarafta*\
Öğeleri hash_multiset *sağdakilerle* değiş tokuş edilecek hash_multiset.

### <a name="remarks"></a>Açıklamalar

`swap`Şablon işlevi, `left.` [Swap](../standard-library/hash-multiset-class.md#swap)() üye işlevini yürütmek için hash_multiset kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır `right` . Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

**Şablon \<class T> void takas (t&, t&),**

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünü kullanan bir örnek için [hash_multiset:: Swap](../standard-library/hash-multiset-class.md#swap) üye sınıfına ait kod örneğine bakın `swap` .

## <a name="see-also"></a>Ayrıca bkz.

[<hash_set>](../standard-library/hash-set.md)
