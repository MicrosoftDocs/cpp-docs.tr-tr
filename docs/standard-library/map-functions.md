---
title: '&lt;Harita&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
caps.latest.revision: 6
manager: ghogen
ms.openlocfilehash: 6a83feab5c477f222dc192c1c916e5cbb93e637d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltmapgt-functions"></a>&lt;Harita&gt; işlevleri

|||
|-|-|
|[Swap (map)](#swap)|[Swap (multimap)](#swap_multimap)|

## <a name="swap_multimap"></a>  Swap (map)

İki eşlemin öğelerini birbiriyle değiştirir.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parametreler

`right` Öğeleri takas için sağlama harita veya öğeleri olan eşleme olanlar değiştirilebilmesi için harita `left`.

`left` Öğeleri olan eşleme olanlar değiştirilebilmesi için harita `right`.

### <a name="remarks"></a>Açıklamalar

Bir algoritma özelleştirilmiş üye işlevini yürütmek için kapsayıcı sınıfı haritada şablon işlevi olan `left`.[ takas](../standard-library/map-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu** \< **sınıfı T**> **void takas**( **T &**, **T &**), algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.

### <a name="example"></a>Örnek

Üye işlevini kod örneğine bakın [map::swap](../standard-library/map-class.md#swap) şablonu sürümünü kullanan bir örnek `swap`.

## <a name="swap"></a>  Swap (multimap)

İki multimaps öğelerini değiş tokuş eder.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parametreler

`right` Öğeleri takas için sağlama multimap veya öğeleri olan multimap olanlar değiştirilmek üzere multimap `left`.

`left` Öğeleri olan multimap olanlar değiştirilmek üzere multimap `right`.

### <a name="remarks"></a>Açıklamalar

Bir algoritma özelleştirilmiş üye işlevini yürütmek için kapsayıcı sınıfı multimap yürütmek için kapsayıcı sınıfı harita üzerinde şablon işlevi olan `left`.[ takas](../standard-library/multimap-class.md#swap) ( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu** \< **sınıfı T**> **void takas**( **T &**, **T &**), algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.

### <a name="example"></a>Örnek

Üye işlevini kod örneğine bakın [multimap::swap](../standard-library/multimap-class.md#swap) şablonu sürümünü kullanan bir örnek `swap`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Harita >](../standard-library/map.md)<br/>
