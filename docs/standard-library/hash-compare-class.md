---
title: "hash_compare sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: hash_set/stdext::hash_compare
dev_langs: C++
helpviewer_keywords: hash_compare class
ms.assetid: d502bb59-de57-4585-beb9-00e3a998c0af
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a04dd9a2c18357260a4543f7117955cc611fa001
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="hashcompare-class"></a>hash_compare Sınıfı
Herhangi bir karma ilişkilendirilebilir kapsayıcıları tarafından kullanılabilen bir nesne şablonu sınıf tanımlar — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak **nitelikler** sıralamak ve içerdikleri öğeleri karma parametre nesnesi .  
  
## <a name="syntax"></a>Sözdizimi  
  
sınıf hash_compare {nitelikler bilgisyar; ortak: const size_t bucket_size = 4; const size_t min_buckets = 8; hash_compare(); hash_compare (nitelikler pred); size_t operator() (const anahtar & anahtar) const; bool operator() (const anahtar & key1, const anahtar & key2) const;};  
  
## <a name="remarks"></a>Açıklamalar  
 Karma nitelikler nesne türü her karma ilişkilendirilebilir kapsayıcısı depolar **nitelikler** (bir şablon parametresi). Seçmeli olarak belirli işlevler ve nesneler geçersiz kılmak için hash_compare uzmanlaşması bir sınıf türetin veya belirli en düşük gereksinimleri karşılıyorsa, bu sınıfın kendi sürümü sağlayabilirsiniz. Özellikle, bir nesne hash_comp türü için **hash_compare\<anahtarı, nitelikler >**, aşağıdaki davranış yukarıdaki kapsayıcıları tarafından gereklidir:  
  
-   Tüm değerler için `key` türü **anahtar**, çağrı **hash_comp**( `key`) bir dağıtım türü değerleri verir ve karma işlevi olarak görev yapar **size_t**. Hash_compare tarafından sağlanan işlevi döndürür `key`.  
  
-   Herhangi bir değer için `key1` türü **anahtar** , önündeki `key2` sırayla ve aynı karma değeri (karma işlevi tarafından döndürülen değeri), **hash_comp**( `key2`, `key1`) false olur. İşlev türü değerlerine sıralama toplam zorunlu tuttukları **anahtar**. Hash_compare tarafından sağlanan işlevi döndürür *comp*( `key2`, `key1`) `,` nerede *comp* depolanan bir nesne türü **nitelikler** , Nesne hash_comp yapısı oluştururken belirtebilirsiniz. Varsayılan **nitelikler** parametre türü **daha az\<anahtar >**, sıralama anahtarları hiçbir zaman değerini azaltın.  
  
-   Tamsayı sabiti **bucket_size** "kapsayıcı aşmayan denemesi gerektiğini demet" (karma tablosu girişi) başına ortalama sayısını belirtir. Sıfırdan büyük olmalıdır. Hash_compare tarafından sağlanan değer 4'tür.  
  
-   Tamsayı sabiti **min_buckets** demet karma tablosunda korumak için en az sayısını belirtir. Bir güç iki ve sıfırdan büyük olmalıdır. Hash_compare tarafından sağlanan değer 8'dir.  
  
## <a name="example"></a>Örnek  
 Örnekler için bkz: [hash_map::hash_map](../standard-library/hash-map-class.md#hash_map), [hash_multimap::hash_multimap](../standard-library/hash-multimap-class.md#hash_multimap), [hash_set::hash_set](../standard-library/hash-set-class.md#hash_set), ve [hash_multiset::hash_multiset](../standard-library/hash-multiset-class.md#hash_multiset), bildirme ve hash_compare kullanma örnekleri için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<hash_map >  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



