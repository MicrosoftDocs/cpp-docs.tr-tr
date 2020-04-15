---
title: '&lt;hash_set&gt; fonksiyonları'
ms.date: 11/04/2016
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
ms.openlocfilehash: d7df6b3c5dc0d0d493d17b3e9995bc4758ffd6d4
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370593"
---
# <a name="lthash_setgt-functions"></a>&lt;hash_set&gt; fonksiyonları

|||
|-|-|
|[Takas](#swap)|[takas (hash_multiset)](#swap_hash_multiset)|

## <a name="swap"></a><a name="swap"></a>Takas

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

İki hash_sets öğelerini değiştirir.

```cpp
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değiştirilecek öğeleri sağlayan hash_set veya elemanları *hash_set kalanlarla*değiştirilecek olan hash_set.

*Sol*\
Elemanları hash_set *hakkın*ki ile değiş tokuş edilecek olan hash_set.

### <a name="remarks"></a>Açıklamalar

Şablon `swap` işlevi, üye işlev `left.` [değiştirme](../standard-library/hash-set-class.md#swap)`right`() yürütmek için hash_set kapsayıcı sınıfı üzerinde uzmanlaşmış bir algoritmadır. Bu, işlev şablonlarının derleyici tarafından kısmi sıralanmasının bir örneğidir. Şablon işlevleri, şablonun işlev çağrısıyla eşleşmesi benzersiz olmayacak şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özel sürümünü seçer. Şablon işlevinin genel sürümü

**şablon \<sınıf T> void swap(T&, T&),**

algoritma sınıfında atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç gösterimi ile çalışabilir gibi her kapsayıcıda özelleştirilmiş sürümü çok daha hızlıdır.

### <a name="example"></a>Örnek

üye sınıfı hash_set için kod örneğine [bakın::şablon](../standard-library/hash-set-class.md#swap) sürümünü `swap`kullanan bir örnek için takas.

## <a name="swap-hash_multiset"></a><a name="swap_hash_multiset"></a>takas (hash_multiset)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_set Sınıf](../standard-library/unordered-set-class.md).

İki hash_multisets öğelerini değiştirir.

```cpp
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Değiştirilecek öğeleri sağlayan hash_multiset veya elemanları *sol*hash_multiset dakilerle değiş tokuş edilecek hash_multiset.

*Sol*\
Elemanları hash_multiset *sağ*olanlar ile değiş tokuş edilecek olan hash_multiset.

### <a name="remarks"></a>Açıklamalar

Şablon `swap` işlevi, üye işlev `left.` [değiştirme](../standard-library/hash-multiset-class.md#swap)() yürütmek için hash_multiset`right`kapsayıcı sınıfı üzerinde uzmanlaşmış bir algoritmadır. Bu, işlev şablonlarının derleyici tarafından kısmi sıralanmasının bir örneğidir. Şablon işlevleri, şablonun işlev çağrısıyla eşleşmesi benzersiz olmayacak şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özel sürümünü seçer. Şablon işlevinin genel sürümü

**şablon \<sınıf T> void swap(T&, T&),**

algoritma sınıfında atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç gösterimi ile çalışabilir gibi her kapsayıcıda özelleştirilmiş sürümü çok daha hızlıdır.

### <a name="example"></a>Örnek

üye sınıfı hash_multiset için kod örneğine [bakın::şablon](../standard-library/hash-multiset-class.md#swap) sürümünü `swap`kullanan bir örnek için takas.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_set>](../standard-library/hash-set.md)
