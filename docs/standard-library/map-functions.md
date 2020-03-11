---
title: '&lt;eşleme&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- map/std::swap (map)
- map/std::swap (multimap)
ms.assetid: 7cb3d1a5-7add-4726-a73f-61927eafd466
ms.openlocfilehash: e7876b37bfc006eaecf2f1e36273c5ae8689dad4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78883972"
---
# <a name="ltmapgt-functions"></a>&lt;eşleme&gt; işlevleri

## <a name="swap_multimap"></a>swap (eşleme)

İki eşlemin öğelerini birbiriyle değiştirir.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    map<Key, Traits, Compare, Alloctor>& left,
    map<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Değiştirilecek öğeleri sağlayan harita veya öğeleri *sol*eşlemle değiştirilecek olan harita.

*sol*\
Öğeleri haritanın *sağına*göre değiş tokuş edilecek harita.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left`üye işlevini yürütmek için kapsayıcı sınıfı eşlemesinde özelleştirilmiş bir algoritmadır. [takas](../standard-library/map-class.md#swap)(`right`). Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü, **şablon** \< **sınıf t**> **void takas**( **t &** , **t &** ), atama tarafından çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

`swap`şablon sürümünü kullanan bir örnek için bkz. Member Function [map:: Swap](../standard-library/map-class.md#swap) için kod örneği.

## <a name="swap"></a>takas (multimap)

İki multimaps öğesinin öğelerini değiş tokuş eder.

```cpp
template <class key, class T, class _Pr, class _Alloc>
void swap(
    multimap<Key, Traits, Compare, Alloctor>& left,
    multimap<Key, Traits, Compare, Alloctor>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*\
Takas edilecek öğeleri sağlayan multimap veya öğeleri multimap 'in *sol*tarafında değiş tokuş edilecek multimap.

*sol*\
Öğeleri multimap ile birlikte değiş tokuş edilecek multimap *.*

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left`üye işlevini yürütmek üzere multimap kapsayıcı sınıfı üzerinde yürütülecek kapsayıcı sınıfı eşlemesinde özelleştirilmiş bir algoritmadır. [takas](../standard-library/multimap-class.md#swap) (`right`). Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Şablon işlevinin genel sürümü, **şablon** \< **sınıf t**> **void takas**( **t &** , **t &** ), atama tarafından çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

### <a name="example"></a>Örnek

`swap`şablon sürümünü kullanan bir örnek için, [multimap:: Swap](../standard-library/multimap-class.md#swap) üye işlevi için kod örneğine bakın.
