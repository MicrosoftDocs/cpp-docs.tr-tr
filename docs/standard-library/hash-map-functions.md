---
description: 'Hakkında daha fazla bilgi edinin: &lt; hash_map &gt; işlevleri'
title: '&lt;hash_map &gt; işlevleri'
ms.date: 11/04/2016
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
ms.openlocfilehash: 50f9150bc79a3ffdc586ba420d6e3dc280784767
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231907"
---
# <a name="lthash_mapgt-functions"></a>&lt;hash_map &gt; işlevleri

[Kur](#swap)\
[takas (hash_map)](#swap_hash_map)

## <a name="swap-hash_map"></a><a name="swap_hash_map"></a> takas (hash_map)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfıdır](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Öğeleri *, eşlemedeki* haritalarla birlikte değiş tokuş edilecek hash_map.

*tarafta*\
Öğeleri haritanın *sağına* göre değiştirilecek olan hash_map.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, `left.` [takas](../standard-library/basic-ios-class.md#swap)*(right*) üye işlevini yürütmek için hash_map kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır. Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Algoritma üstbilgi dosyasında şablon işlevinin genel sürümü, **şablon \<class T> void swap (t&, t&)**, atama tarafından çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

## <a name="swap"></a><a name="swap"></a> Kur

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfıdır](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

*Right*\
Öğeleri *, eşlemedeki* haritalarla birlikte değiş tokuş edilecek hash_multimap.

*tarafta*\
Öğeleri haritanın *sağına* göre değiştirilecek olan hash_multimap.

### <a name="remarks"></a>Açıklamalar

Şablon işlevi, değiştirme üye işlevini yürütmek için hash_multimap kapsayıcı sınıfı üzerinde özelleştirilmiş bir algoritmadır `left.` [](../standard-library/hash-multimap-class.md#swap)*(sağ* `)` . Bu, derleyici tarafından işlev şablonlarının kısmi sıralaması örneğidir. Şablon işlevleri, işlev çağrısı ile şablonla eşleşen bir şekilde aşırı yüklendiğinde, derleyici şablon işlevinin en özelleştirilmiş sürümünü seçer. Algoritma üstbilgi dosyasında şablon işlevinin genel sürümü, **şablon \<class T> void swap (t&, t&)**, atama tarafından çalışır ve yavaş bir işlemdir. Kapsayıcı sınıfının iç temsili ile çalışabildiğinden, her kapsayıcıda özelleştirilmiş sürüm çok daha hızlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_map>](../standard-library/hash-map.md)
