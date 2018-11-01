---
title: '&lt;ayarlama&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
ms.openlocfilehash: 3873a85218c738b3a9693926e064a10b82a553c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50467346"
---
# <a name="ltsetgt-functions"></a>&lt;ayarlama&gt; işlevleri

|||
|-|-|
|[Swap (map)](#swap)|[Swap (multiset)](#swap_multiset)|

## <a name="swap"></a>  Swap (map)

İki kümenin öğelerini birbiriyle değiştirir.

```cpp
template <class Key, class Traits, class Allocator>
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Değiştirilecek öğeleri sağlayan kümesi veya öğeleri kümesi öğelerle ilişkili kümesi *sol*.

*Sol*<br/>
Öğeleri kümesi öğelerle ilişkili kümesi *doğru*.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevini yürütmek için ayarlanan kapsayıcı sınıf üzerinde bir algoritma şablon işlevi olan `left.` [takas](../standard-library/set-class.md#swap)(`right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Genel bir sürümü olan şablon işlevi

`template` \< **classT**> **void takas**( **T &**, **T &**)

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [set::swap](../standard-library/set-class.md#swap) şablon sürümünü kullanımına ilişkin bir örnek `swap`.

## <a name="swap_multiset"></a>  Swap (multiset)

İki multisets öğelerini birbiriyle değiştirir.

```cpp
template <class Key, class Traits, class Allocator>
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Değiştirilecek öğeleri sağlayan multiset veya öğeleri olan çoklu olanlar değiştirilecek multiset *sol*.

*Sol*<br/>
Öğeleri olan çoklu olanlar değiştirilecek multiset *doğru*.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevini yürütmek için kapsayıcı sınıfı multiset bir algoritma şablon işlevi olan `left.` [takas](../standard-library/multiset-class.md#swap)(`right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Genel bir sürümü olan şablon işlevi

`template` \< **classT**> **void takas**( **T &**, **T &**)

algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye sınıfı kod örneğine bakın [multiset::swap](../standard-library/multiset-class.md#swap)şablon sürümünü kullanımına ilişkin bir örnek `swap`.

## <a name="see-also"></a>Ayrıca bkz.

[\<kümesi >](../standard-library/set.md)<br/>
