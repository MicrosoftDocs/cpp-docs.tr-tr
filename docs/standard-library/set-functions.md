---
description: 'Daha fazla bilgi edinin: &lt; set &gt; Functions'
title: '&lt;&gt;işlevleri ayarla'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: 14f8eac3f725f88d98cdba133dace06993e5c089
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154142"
---
# <a name="ltsetgt-functions"></a>&lt;&gt;işlevleri ayarla

## <a name="swap-map"></a><a name="swap"></a> swap (eşleme)

İki kümenin öğelerini birbiriyle değiştirir.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan küme veya öğeleri, *sol* ayarlı olanlarla birlikte değiş tokuş edilecek olan küme.

*tarafta*\
Öğeleri ayarlanan *sağdan* birlikte değiş tokuş edilecek olan küme.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left.` [Swap](../standard-library/set-class.md#swap)() üye işlevini yürütmek üzere ayarlanmış kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır `right` . Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

`template`\< **classT**> **void değiştirme**( **t&**, **t&**)

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünün kullanımıyla ilgili bir örnek için bkz. Member Class [set:: Swap](../standard-library/set-class.md#swap) için kod örneği `swap` .

## <a name="swap-multiset"></a><a name="swap_multiset"></a> takas (çoklu küme)

İki multiset 'in öğelerini değiş tokuş eder.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan çoklu küme veya öğeleri, çok sayıda çoklu küme ile değiş tokuş *edilecek çoklu küme.*

*tarafta*\
Öğeleri çoklu küme *hakkı* ile değiş tokuş edilecek olan çok kümeli.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left.` [Swap](../standard-library/multiset-class.md#swap)() üye işlevini yürütmek üzere çok kümeli kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır `right` . Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

`template`\< **classT**> **void değiştirme**( **t&**, **t&**)

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünün kullanımına örnek olarak, [multıset:: Swap](../standard-library/multiset-class.md#swap)üye sınıfının kod örneğine bakın `swap` .
