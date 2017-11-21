---
title: "&lt;hash_set&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- hash_set/std::swap
- hash_set/std::swap (hash_multiset)
ms.assetid: 557a0162-3728-4537-97dc-f9f6cc7ece94
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 4fcd6f0d72d31823a0d35108f087f2ad680e2f48
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="lthashsetgt-functions"></a>&lt;hash_set&gt; işlevleri
|||  
|-|-|  
|[değiştirme](#swap)|[Swap (hash_multiset)](#swap_hash_multiset)|  
  
##  <a name="swap"></a>değiştirme  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).  
  
 İki hash_sets öğelerini değiş tokuş eder.  
  
```
void swap(
    hash_set <Key, Traits, Allocator>& left,
    hash_set <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama hash_set veya öğeleri olan hash_set olanlar değiştirilmek üzere hash_set `left`.  
  
 `left`  
 Öğeleri olan hash_set olanlar değiştirilmek üzere hash_set `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 `swap` Şablon işlevi olan bir algoritma özelleştirilmiş üye işlevini yürütmek için kapsayıcı sınıfı hash_set `left.` [takas](../standard-library/hash-set-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir sürümü olan şablon işlevi  
  
 **Şablon \<sınıfı T > void takas (T & T &),**  
  
 algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
   
  
### <a name="example"></a>Örnek  
  Üye sınıfı kod örneğine bakın [hash_set::swap](../standard-library/hash-set-class.md#swap) şablonu sürümünü kullanan bir örnek `swap`.  
  
##  <a name="swap_hash_multiset"></a>Swap (hash_multiset)  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_set sınıfı](../standard-library/unordered-set-class.md).  
  
 İki hash_multisets öğelerini değiş tokuş eder.  
  
```
void swap(hash_multiset <Key, Traits, Allocator>& left, hash_multiset <Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama hash_multiset veya öğeleri olan hash_multiset olanlar değiştirilmek üzere hash_multiset `left`.  
  
 `left`  
 Öğeleri olan hash_multiset olanlar değiştirilmek üzere hash_multiset `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 `swap` Şablon işlevi olan bir algoritma özelleştirilmiş üye işlevini yürütmek için kapsayıcı sınıfı hash_multiset `left.` [takas](../standard-library/hash-multiset-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir sürümü olan şablon işlevi  
  
 **Şablon \<sınıfı T > void takas (T & T &),**  
  
 algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
   
  
### <a name="example"></a>Örnek  
  Üye sınıfı kod örneğine bakın [hash_multiset::swap](../standard-library/hash-multiset-class.md#swap) şablonu sürümünü kullanan bir örnek `swap`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [< hash_set >](../standard-library/hash-set.md)



