---
title: '&lt;hash_map&gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: dae2c47ef3b84247ab1747e37719a23b220b5d08
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627428"
---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt; işlevleri

|||
|-|-|
|[değiştirme](#swap)|[Swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a>  Swap (hash_map)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini birbiriyle değiştirir.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Öğeleri harita öğelerle ilişkili hash_map *sol*.

*Sol*<br/>
Öğeleri harita öğelerle ilişkili hash_map *doğru*.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevini yürütmek için kapsayıcı sınıfı hash_map bir algoritma şablon işlevi olan `left.` [takas](../standard-library/basic-ios-class.md#swap)*(doğru*). İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Şablon işlevinin genel sürüm **şablon \<sınıfı T > void takas (T &, T &)**, algoritma üstbilgi dosyası tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

## <a name="swap"></a>  değiştirme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini birbiriyle değiştirir.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Öğeleri harita öğelerle ilişkili hash_multimap *sol*.

*Sol*<br/>
Öğeleri harita öğelerle ilişkili hash_multimap *doğru*.

### <a name="remarks"></a>Açıklamalar

Özel üye işlevini yürütmek için kapsayıcı sınıfı hash_multimap bir algoritma şablon işlevi olan `left.` [takas](../standard-library/hash-multimap-class.md#swap)*(doğru*`)`. İşlev şablonlarının kısmi derleyici tarafından sıralanması bir örneğini budur. Şablon işlevleri şablonu işlev çağrısı ile eşleşen benzersiz değil bir şekilde aşırı yüklendiğinde, derleyici en özel şablon işlevi sürümü seçin. Şablon işlevinin genel sürüm **şablon \<sınıfı T > void takas (T &, T &)**, algoritma üstbilgi dosyası tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özelleştirilmiş bir sürüm olarak kapsayıcı sınıfı iç gösterimine ile çalışabilir daha hızlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_map>](../standard-library/hash-map.md)<br/>
