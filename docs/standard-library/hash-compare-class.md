---
title: hash_compare Sınıfı
ms.date: 11/04/2016
f1_keywords:
- hash_set/stdext::hash_compare
helpviewer_keywords:
- hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
ms.openlocfilehash: 4fb44a371630a66275f6ef59a0bf66b4cb73a71f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689554"
---
# <a name="hash_compare-class"></a>hash_compare Sınıfı

Sınıf şablonu, içerdikleri öğeleri sıralamak ve karma hale getirmek için varsayılan **nitelikler** parametre nesnesi olarak, karma ilişkilendirilebilir kapsayıcılar (hash_map, hash_multimap, hash_set veya hash_multiset) tarafından kullanılabilen bir nesneyi tanımlar.

## <a name="syntax"></a>Sözdizimi

Class hash_compare {nitelikler comp; public: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare (); hash_compare (nitelikler Pred); size_t işleci () (const Key & Key) const; bool işleci () (const Key & KEY1, const Key & key2) const;};

## <a name="remarks"></a>Açıklamalar

Her karma ilişkilendirilebilir kapsayıcı, `Traits` türünde bir karma nitelikleri nesnesi depolar (bir şablon parametresi). Belirli işlevleri ve nesneleri seçmeli olarak geçersiz kılmak için bir hash_compare uzmanından bir sınıf türetebilirsiniz veya belirli minimum gereksinimleri karşıladıysanız bu sınıfın kendi sürümünü sağlayabilirsiniz. Özellikle, `hash_compare<Key, Traits>` türünde bir nesne hash_comp için yukarıdaki kapsayıcılar için aşağıdaki davranış gereklidir:

- @No__t_1 türü `key` tüm değerler için, Call **hash_comp**(`key`), `size_t` türünde bir değer dağılımı veren bir karma işlev işlevi görür. Hash_compare tarafından sağlanan işlev `key` döndürür.

- Dizide `key2` önce gelen ve aynı karma değerine (karma işlevi tarafından döndürülen değer) sahip olan `Key` türündeki `key1` herhangi bir değer için, **hash_comp**(`key2`, `key1`) false olur. İşlev, `Key` türündeki değerlere toplam bir sıralama getirmelidir. Hash_compare tarafından sağlanan işlev, hash_comp nesnesini oluştururken belirtebileceğiniz, `Traits` türünde depolanan *bir nesne olan* *comp*(`key2` `key1`) `,` döndürür. Varsayılan `Traits` parametre türü `less<Key>` için sıralama anahtarları değerde hiçbir şekilde azalmayın.

- Tamsayı sabiti `bucket_size`, kapsayıcının aşmamak için gereken "demet" (karma tablo girişi) başına öğelerin ortalama sayısını belirtir. Sıfırdan büyük olmalıdır. Hash_compare tarafından sağlanan değer 4 ' dir.

- Tamsayı sabiti `min_buckets`, Karma tabloda korunacak en düşük demet sayısını belirtir. İki ve sıfırdan büyük bir üssü olmalıdır. Hash_compare tarafından sağlanan değer 8 ' dir.

## <a name="example"></a>Örnek

Hash_set bildirme ve kullanma örnekleri için bkz. [hash_map:: hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap:: hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set:: hash_multiset](../standard-library/hash-set-class.md#hash_set)ve hash_multiset [:: hash_compare](../standard-library/hash-multiset-class.md#hash_multiset)örnekleri.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<hash_map >

**Ad alanı:** stdext

## <a name="see-also"></a>Ayrıca bkz.

[Standart kitaplıkta Iş parçacığı güvenliği \ C++ ](../standard-library/thread-safety-in-the-cpp-standard-library.md)
[C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)
