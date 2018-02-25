---
title: "&lt;hash_map&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- hash_map/std::swap
- hash_map/std::swap (hash_map)
ms.assetid: 28748cd0-71f7-41b9-b068-579183645fba
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 4240316aadf964b972c46a00c6ee4a09cc4626d6
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="lthashmapgt-functions"></a>&lt;hash_map&gt; işlevleri
|||  
|-|-|  
|[Değiştirme](#swap)|[swap (hash_map)](#swap_hash_map)|  
  
##  <a name="swap_hash_map"></a>  Swap (hash_map)  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_map sınıfı](../standard-library/unordered-map-class.md).  
  
 İki hash_maps öğelerini değiş tokuş eder.  
  
```
void swap(
    hash_map <Key, Type, Traits, Alloctor>& left,
    hash_map <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri olan eşleme olanlar değiştirilmek üzere hash_map `left`.  
  
 `left`  
 Öğeleri olan eşleme olanlar değiştirilmek üzere hash_map `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yürütmek için kapsayıcı sınıfı hash_map özelleştirilmiş bir algoritma şablon işlevi olan `left.` [takas](../standard-library/basic-ios-class.md#swap)*(sağ*). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu \<sınıfı T > void takas (T & T &)**, algoritma üstbilgi dosyası tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
##  <a name="swap">Değiştirme</a>  
  
> [!NOTE]
>  Bu, API artık kullanılmıyor. Alternatif [unordered_multimap sınıfı](../standard-library/unordered-multimap-class.md).  
  
 İki hash_multimaps öğelerini değiş tokuş eder.  
  
```
void swap(
    hash_multimap <Key, Type, Traits, Alloctor>& left,
    hash_multimap <Key, Type, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri olan eşleme olanlar değiştirilmek üzere hash_multimap `left`.  
  
 `left`  
 Öğeleri olan eşleme olanlar değiştirilmek üzere hash_multimap `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yürütmek için kapsayıcı sınıfı hash_multimap özelleştirilmiş bir algoritma şablon işlevi olan `left.` [takas](../standard-library/hash-multimap-class.md#swap)*(sağ*`)`. İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu \<sınıfı T > void takas (T & T &)**, algoritma üstbilgi dosyası tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [<hash_map>](../standard-library/hash-map.md)



