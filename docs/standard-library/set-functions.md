---
title: '&gt; işlevleri &lt;ayarla'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: a3a63fb86caa3485b1ee14538c3eb1f1ff72923e
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419555"
---
# <a name="ltsetgt-functions"></a>&gt; işlevleri &lt;ayarla

## <a name="swap"></a>swap (eşleme)

İki kümenin öğelerini birbiriyle değiştirir.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Değiştirilecek öğeleri sağlayan küme veya öğeleri, *sol*ayarlı olanlarla birlikte değiş tokuş edilecek olan küme.

*sol*\
Öğeleri ayarlanan *sağdan*birlikte değiş tokuş edilecek olan küme.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, [değiştirme](../standard-library/set-class.md#swap)(`right`) `left.`üye işlevini yürütmek üzere ayarlanmış kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır. Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

`template` \< **Classt**> **void takas**( **t &** , **t &** )

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

`swap`şablon sürümünün kullanımıyla ilgili bir örnek için bkz. Member Class [set:: Swap](../standard-library/set-class.md#swap) için kod örneği.

## <a name="swap_multiset"></a>takas (çoklu küme)

İki multiset 'in öğelerini değiş tokuş eder.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Değiştirilecek öğeleri sağlayan çoklu küme veya öğeleri, çok sayıda çoklu küme ile değiş tokuş *edilecek çoklu küme.*

*sol*\
Öğeleri çoklu küme *hakkı*ile değiş tokuş edilecek olan çok kümeli.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, [takas](../standard-library/multiset-class.md#swap)(`right`) `left.`üye işlevini yürütmek için çoklu kümeli kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır. Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü

`template` \< **Classt**> **void takas**( **t &** , **t &** )

algoritma sınıfında atama ile çalışıyor ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

`swap`şablon sürümünün kullanımı örneği için bkz. [multıset:: Swap](../standard-library/multiset-class.md#swap)üye sınıfı için kod örneği.
