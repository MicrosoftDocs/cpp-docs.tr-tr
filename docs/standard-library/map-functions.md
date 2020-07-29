---
title: '&lt;eşleme &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: 8cc4a82e08963902f9ba5c21ace759c47bdd0014
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228225"
---
# <a name="ltmapgt-functions"></a>&lt;eşleme &gt; işlevleri

## <a name="swap-map"></a><a name="swap_multimap"></a>swap (eşleme)

İki eşlemin öğelerini birbiriyle değiştirir.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Değiştirilecek öğeleri sağlayan harita veya öğeleri *sol*eşlemle değiştirilecek olan harita.

*tarafta*\
Öğeleri haritanın *sağına*göre değiş tokuş edilecek harita.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, üye işlevini yürütmek için kapsayıcı sınıfı eşlemesinde özelleştirilmiş bir algoritmadır `left` .[ Swap](../standard-library/map-class.md#swap)( `right` ). Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. **`template`** \< **class T**> Algoritma sınıfında, **void Swap**( **t&**, **t&**) şablon işlevinin genel sürümü atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünü kullanan bir örnek için bkz. Member Function [map:: Swap](../standard-library/map-class.md#swap) için kod örneği `swap` .

## <a name="swap-multimap"></a><a name="swap"></a>takas (multimap)

İki multimaps öğesinin öğelerini değiş tokuş eder.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Takas edilecek öğeleri sağlayan multimap veya öğeleri multimap 'in *sol*tarafında değiş tokuş edilecek multimap.

*tarafta*\
Öğeleri multimap ile birlikte değiş tokuş edilecek multimap *.*

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, üye işlevini yürütmek üzere multimap kapsayıcı sınıfında yürütülecek kapsayıcı sınıfı eşlemesinde özelleştirilmiş bir algoritmadır `left` .[ Swap](../standard-library/multimap-class.md#swap) ( `right` ). Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. **`template`** \< **class T**> Algoritma sınıfında, **void Swap**( **t&**, **t&**) şablon işlevinin genel sürümü atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

Şablon sürümünü kullanan bir örnek için, [multimap:: Swap](../standard-library/multimap-class.md#swap) üye işlevine yönelik kod örneğine bakın `swap` .
