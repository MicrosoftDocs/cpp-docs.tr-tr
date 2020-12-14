---
description: 'Hakkında daha fazla bilgi edinin: hash_compare sınıfı'
title: hash_compare Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 510de9901e58e130a53410b688c22324714b9962
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231946"
---
# <a name="hash_compare-class"></a>hash_compare Sınıfı

Sınıf şablonu, içerdikleri öğeleri sıralamak ve karma hale getirmek için bir varsayılan **nitelikler** parametre nesnesi olarak hash_map, hash_multimap, hash_set veya hash_multiset gibi karma ilişkilendirilebilir kapsayıcılardan herhangi biri tarafından kullanılabilecek bir nesneyi tanımlar.

## <a name="syntax"></a>Syntax

sınıf hash_compare {nitelikler comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare (); hash_compare (nitelikler Pred); size_t işleç () (const anahtar& anahtarı) const; bool işleci () (const Key& KEY1, const Key& key2) const;};

## <a name="remarks"></a>Açıklamalar

Her karma ilişkilendirilebilir kapsayıcı, türünde bir karma nitelikleri nesnesi depolar `Traits` (bir şablon parametresi). Belirli işlevleri ve nesneleri seçmeli olarak geçersiz kılmak için hash_compare özelleştirmede bir sınıf türetebilirsiniz veya belirli minimum gereksinimleri karşıladıysanız bu sınıfın kendi sürümünü sağlayabilirsiniz. Özellikle, türü hash_comp bir nesne için `hash_compare<Key, Traits>` Yukarıdaki kapsayıcılar için aşağıdaki davranış gereklidir:

- Türündeki tüm değerler için `key` `Key` , **hash_comp**( `key` ) çağrısı bir karma işlevi olarak işlev görür, bu da tür değerlerinin bir dağılımını verir `size_t` . Hash_compare tarafından sağlanan işlev döndürür `key` .

- `key1` `Key` `key2` Dizide yer alan ve aynı karma değerine (karma işlevi tarafından döndürülen değer) sahip olan herhangi bir değer için, **hash_comp**( `key2` , `key1` ) false olur. İşlev, türündeki değerlere toplam bir sıralama getirmelidir `Key` . Hash_compare tarafından sağlanan işlev,  `key2` `key1` `,` *comp* , `Traits` nesne hash_comp oluştururken belirtebileceğiniz, türünde depolanan bir nesne olan comp (,) öğesini döndürüyor. Varsayılan `Traits` parametre türü için `less<Key>` sıralama anahtarları değerde hiçbir şekilde azalmayın.

- Tamsayı sabiti, `bucket_size` kapsayıcının aşmamak için gereken ortalama öğe sayısını "demet" (karma tablo girişi) başına belirler. Sıfırdan büyük olmalıdır. Hash_compare tarafından sağlanan değer 4 ' dir.

- Tamsayı sabiti, `min_buckets` karma tablosunda korunacak en düşük demet sayısını belirtir. İki ve sıfırdan büyük bir üssü olmalıdır. Hash_compare tarafından sağlanan değer 8 ' dir.

## <a name="example"></a>Örnek

Hash_set bildirme ve kullanma örnekleri için [hash_map:: hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap:: hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set:: hash_multiset](../standard-library/hash-set-class.md#hash_set)ve hash_multiset [:: hash_compare](../standard-library/hash-multiset-class.md#hash_multiset)örneklerine bakın.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<hash_map>

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)\
[C++ standart kitaplığı başvurusu](../standard-library/cpp-standard-library-reference.md)
