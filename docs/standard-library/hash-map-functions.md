---
title: '&lt;hash_map&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
caps.latest.revision: 9
manager: ghogen
ms.openlocfilehash: d54cf0181a80ccb763cfe76f8eb89ade5a56b7d4
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt; işlevleri

|||
|-|-|
|[Değiştirme](#swap)|[Swap (hash_map)](#swap_hash_map)|

## <a name="swap_hash_map"></a>  Swap (hash_map)

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).

İki hash_maps öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`right` Öğeleri olan eşleme olanlar değiştirilmek üzere hash_map `left`.

`left` Öğeleri olan eşleme olanlar değiştirilmek üzere hash_map `right`.

### <a name="remarks"></a>Açıklamalar

Üye işlevini yürütmek için kapsayıcı sınıfı hash_map özelleştirilmiş bir algoritma şablon işlevi olan `left.` [takas](../standard-library/basic-ios-class.md#swap)*(sağ*). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu \<sınıfı T > void takas (T & T &)**, algoritma üstbilgi dosyası tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.

## <a name="swap"></a>  Değiştirme

> [!NOTE]
> Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).

İki hash_multimaps öğelerini değiş tokuş eder.

```cpp
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```

### <a name="parameters"></a>Parametreler

`right` Öğeleri olan eşleme olanlar değiştirilmek üzere hash_multimap `left`.

`left` Öğeleri olan eşleme olanlar değiştirilmek üzere hash_multimap `right`.

### <a name="remarks"></a>Açıklamalar

Üye işlevini yürütmek için kapsayıcı sınıfı hash_multimap özelleştirilmiş bir algoritma şablon işlevi olan `left.` [takas](../standard-library/hash-multimap-class.md#swap)*(sağ*`)`. İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu \<sınıfı T > void takas (T & T &)**, algoritma üstbilgi dosyası tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[<hash_map>](../standard-library/hash-map.md)<br/>
