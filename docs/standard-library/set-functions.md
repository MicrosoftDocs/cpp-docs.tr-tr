---
title: '&lt;ayarlama&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: a3a63fb86caa3485b1ee14538c3eb1f1ff72923e
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68246407"
---
# <a name="ltsetgt-functions"></a>&lt;ayarlama&gt; işlevleri

## <a name="swap"></a> Swap (map)

İki kümenin öğelerini birbiriyle değiştirir.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Değiştirilecek öğeleri sağlayan kümesi veya öğeleri kümesi öğelerle ilişkili kümesi *sol*.

*Sol*\
Öğeleri kümesi öğelerle ilişkili kümesi *doğru*.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevini yürütmek için ayarlanan kapsayıcı sınıf üzerinde bir algoritma şablon işlevi olan `left.` [takas](../standard-library/set-class.md#swap)(`right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Genel bir sürümü olan şablon işlevi

`template` \< **classT**> **void takas**( **T &** , **T &** )

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [set::swap](../standard-library/set-class.md#swap) şablon sürümünü kullanımına ilişkin bir örnek `swap`.

## <a name="swap_multiset"></a> Swap (multiset)

İki multisets öğelerini birbiriyle değiştirir.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Değiştirilecek öğeleri sağlayan multiset veya öğeleri olan çoklu olanlar değiştirilecek multiset *sol*.

*Sol*\
Öğeleri olan çoklu olanlar değiştirilecek multiset *doğru*.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevini yürütmek için kapsayıcı sınıfı multiset bir algoritma şablon işlevi olan `left.` [takas](../standard-library/multiset-class.md#swap)(`right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Genel bir sürümü olan şablon işlevi

`template` \< **classT**> **void takas**( **T &** , **T &** )

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [multiset::swap](../standard-library/multiset-class.md#swap)şablon sürümünü kullanımına ilişkin bir örnek `swap`.
