---
title: '&lt;hash_map&gt; fonksiyonları'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: 7cb2e46f19bd30e3eb313cde867c6a055cb8bca5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370612"
---
# <a name="lthash_mapgt-functions"></a>&lt;hash_map&gt; fonksiyonları

|||
|-|-|
|[Takas](#swap)|[takas (hash_map)](#swap_hash_map)|

## <a name="swap-hash_map"></a><a name="swap_hash_map"></a>takas (hash_map)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map Sınıf](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini değiştirir.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Elemanları *kalan*haritanın ki ile değiş tokuş edilecek olan hash_map.

*Sol*\
Elemanları *haritanın sağdakilerle*değiş tokuş edilecek olan hash_map.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, üye işlev `left.` [değiştirme](../standard-library/basic-ios-class.md#swap)*(sağda)* yürütmek için hash_map kapsayıcı sınıfı üzerinde uzmanlaşmış bir algoritmadır. Bu, işlev şablonlarının derleyici tarafından kısmi sıralanmasının bir örneğidir. Şablon işlevleri, şablonun işlev çağrısıyla eşleşmesi benzersiz olmayacak şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özel sürümünü seçer. Şablon işlevinin genel sürümü, **şablon \<sınıfı T> boşluk takas (T&, T&)**, algoritma üstbilgi dosyasında atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç gösterimi ile çalışabilir gibi her kapsayıcıda özelleştirilmiş sürümü çok daha hızlıdır.

## <a name="swap"></a><a name="swap"></a>Takas

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap Sınıf](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini değiştirir.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Elemanları *kalan*haritanın ki ile değiş tokuş edilecek olan hash_multimap.

*Sol*\
Elemanları *haritanın sağdakilerle*değiş tokuş edilecek olan hash_multimap.

### <a name="remarks"></a>Açıklamalar

Şablon hash_multimap işlevi, üye `left.`işlev [değiştirme](../standard-library/hash-multimap-class.md#swap)*(sağ*`)`. Bu, işlev şablonlarının derleyici tarafından kısmi sıralanmasının bir örneğidir. Şablon işlevleri, şablonun işlev çağrısıyla eşleşmesi benzersiz olmayacak şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özel sürümünü seçer. Şablon işlevinin genel sürümü, **şablon \<sınıfı T> boşluk takas (T&, T&)**, algoritma üstbilgi dosyasında atama ile çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç gösterimi ile çalışabilir gibi her kapsayıcıda özelleştirilmiş sürümü çok daha hızlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_map>](../standard-library/hash-map.md)
