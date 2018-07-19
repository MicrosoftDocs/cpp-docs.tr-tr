---
title: '&lt;Harita&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: 3c6cb7d0308e4bafc531fe0baf0c5d666228c3ec
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38966374"
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

*doğru* değiştirilecek öğeleri sağlayan eşlemesi veya öğeleri harita öğelerle ilişkili harita *sol*.

*Sol* öğeleri harita öğelerle ilişkili harita *doğru*.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevini yürütmek için kapsayıcı sınıfı harita üzerinde bir algoritma şablon işlevi olan `left`.[ takas](../standard-library/map-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Şablon işlevinin genel sürüm **şablon** \< **sınıfı T**> **void takas**( **T &**, **T &**), algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye işlevi kod örneğine bakın [map::swap](../standard-library/map-class.md#swap) şablon sürümünü kullanan bir örnek için `swap`.

## <a name="swap"></a>  Swap (multimap)

İki multimaps öğelerini birbiriyle değiştirir.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parametreler

*doğru* değiştirilecek öğeleri sağlayan multimap veya öğeleri olan çoklu eşlem olanlar değiştirilecek multimap *sol*.

*Sol* öğeleri olan çoklu eşlem olanlar değiştirilecek multimap *doğru*.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi bir algoritma özel üye işlevini yürütmek için kapsayıcı sınıfı multimap yürütmek için kapsayıcı sınıfı harita üzerinde olan `left`.[ takas](../standard-library/multimap-class.md#swap) (`right`). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Şablon işlevinin genel sürüm **şablon** \< **sınıfı T**> **void takas**( **T &**, **T &**), algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

### <a name="example"></a>Örnek

Üye işlevi kod örneğine bakın [multimap::swap](../standard-library/multimap-class.md#swap) şablon sürümünü kullanan bir örnek için `swap`.

## <a name="see-also"></a>Ayrıca bkz.

[\<Harita >](../standard-library/map.md)<br/>
