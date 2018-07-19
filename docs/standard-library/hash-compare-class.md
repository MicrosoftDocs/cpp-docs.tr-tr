---
title: hash_compare sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- hash_set/stdext::hash_compare
dev_langs:
- C++
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 92dce97754eccc8cd4f618db3ac3e23574fb54ae
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956588"
---
# <a name="hashcompare-class"></a>hash_compare Sınıfı

Şablon sınıfı herhangi bir karma ilişkilendirilebilir kapsayıcılar tarafından kullanılabilen bir nesne tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak **nitelikler** sipariş ve içerdikleri öğelerin karma parametre nesnesi .

## <a name="syntax"></a>Sözdizimi

hash_compare sınıfı {nitelikler comp; ortak: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare() hash_compare (nitelikler pred); size_t operator() (const anahtar & anahtarı) const; bool operator() (const anahtar & key1, key2 & const anahtarını) const;};

## <a name="remarks"></a>Açıklamalar

Bir karma özellikleri nesnesinin türü her karma seçimin ilişkili kapsayıcısı depolar `Traits` (şablon parametresi). Hash_compare seçerek belirli işlevler ve nesneler geçersiz kılmak için bir alt uzmanlaşması bir sınıf türetebilirsiniz veya belirli en düşük gereksinimleri karşılıyorsa bu sınıfın kendi sürümü sağlayabilirsiniz. Özellikle, bir nesne hash_comp türü için `hash_compare<Key, Traits>`, aşağıdaki davranış göre yukarıdaki kapsayıcı gereklidir:

- Tüm değerler için `key` türü `Key`, çağrı **hash_comp**(`key`) türünde bir değerler dağıtımı verir ve karma işlevi olarak görev yapar `size_t`. Hash_compare tarafından sağlanan işlevi döndürür `key`.

- Herhangi bir değer için `key1` türü `Key` metninden önce `key2` sırayla ve aynı karma değeri (karma işlev tarafından döndürülen değer), **hash_comp**(`key2`, `key1`) yanlış. İşlev türünün değerleri üzerinde sıralama toplam zorunlu tuttukları `Key`. Hash_compare tarafından sağlanan işlevi döndürür *comp*(`key2`, `key1`) `,` burada *comp* depolanan bir nesne türünün `Traits` ne zaman belirtin, Nesne hash_comp oluşturun. Varsayılan `Traits` parametre türü `less<Key>`, sıralama anahtarı değeri hiçbir zaman azaltabilirsiniz.

- Tamsayı sabiti `bucket_size` ", kapsayıcı aşmayan denemelisiniz demet başına" (karma tablo girişi) öğelerin ortalama sayısını belirtir. Sıfırdan büyük olmalıdır. Hash_compare tarafından sağlanan değer 4'tür.

- Tamsayı sabiti `min_buckets` karma tablosundan korumak için demet en az sayısını belirtir. Bir güç iki ve sıfırdan büyük olmalıdır. Hash_compare tarafından sağlanan değer 8'dir.

## <a name="example"></a>Örnek

Örnekler için bkz: [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set), ve [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset), bildirmek ve hash_compare kullanma örnekleri için.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<hash_map >

**Namespace:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)<br/>
