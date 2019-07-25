---
title: '&lt;hash_map&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: efaa960d91c69d2157896adb4612c5dd36f00cff
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448741"
---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt; işlevleri

|||
|-|-|
|[Kur](#swap)|[swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a>swap (hash_map)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Öğeleri *, eşlemedeki*haritalarla birlikte değiş tokuş edilecek hash_map.

*tarafta*\
Öğeleri haritanın *sağına*göre değiş tokuş edilecek hash_map.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left.` [değiştirme](../standard-library/basic-ios-class.md#swap) *(sağ*) üye işlevini yürütmek için hash_map kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır. Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Bu şablon işlevinin genel sürümü, algoritma üstbilgi **dosyasındaki \<t > void swap (t &, t &) şablon sınıfı**atama tarafından çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

## <a name="swap"></a>Kur

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif, [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Öğeleri *, eşlemedeki*haritalarla birlikte değiş tokuş edilecek hash_multimap.

*tarafta*\
Öğeleri haritanın *sağına*göre değiş tokuş edilecek hash_multimap.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi `left.`, [değiştirme](../standard-library/hash-multimap-class.md#swap)üye işlevi için hash_multimap kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır *(sağ*`)`. Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Bu şablon işlevinin genel sürümü, algoritma üstbilgi **dosyasındaki \<t > void swap (t &, t &) şablon sınıfı**atama tarafından çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_map>](../standard-library/hash-map.md)
