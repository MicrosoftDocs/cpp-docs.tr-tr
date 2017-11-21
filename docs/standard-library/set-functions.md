---
title: "&lt;ayarlama&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- set/std::swap (map)
- set/std::swap (multiset)
ms.assetid: d1277d14-8502-46c0-b820-bcda820f9406
caps.latest.revision: "7"
manager: ghogen
ms.openlocfilehash: 5580030a16953fbfb3759c955555b646ff1cb15d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltsetgt-functions"></a>&lt;ayarlama&gt; işlevleri
|||  
|-|-|  
|[Swap (map)](#swap)|[Swap (multiset)](#swap_multiset)|  
  
##  <a name="swap"></a>Swap (map)
 İki kümenin öğelerini birbiriyle değiştirir.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(set<Key, Traits, Allocator>& left, set<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama kümesi veya öğeleri olan kümesinin olanlar değiştirilmek üzere kümesi `left`.  
  
 `left`  
 Öğeleri olan kümesinin olanlar değiştirilmek üzere kümesi `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yürütmek için ayarlanan kapsayıcı sınıf özelleştirilmiş bir algoritma şablon işlevi olan `left.` [takas](../standard-library/set-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir sürümü olan şablon işlevi  
  
 `template`\< **classT**> **void takas**( **T &**, **T &**)  
  
 algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
### <a name="example"></a>Örnek  
  Üye sınıfı kod örneğine bakın [set::swap](../standard-library/set-class.md#swap) şablon sürümü kullanımına ilişkin bir örnek `swap`.  
  
##  <a name="swap_multiset"></a>Swap (multiset)
 İki multisets öğelerini değiş tokuş eder.  
  
```
template <class Key, class Traits, class Allocator>  
void swap(multiset<Key, Traits, Allocator>& left, multiset<Key, Traits, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama multiset veya öğeleri olan multiset olanlar değiştirilmek üzere multiset `left`.  
  
 `left`  
 Öğeleri olan multiset olanlar değiştirilmek üzere multiset `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yürütmek için kapsayıcı sınıfı multiset özelleştirilmiş bir algoritma şablon işlevi olan `left.` [takas](../standard-library/multiset-class.md#swap)( `right`). İşlev şablonlarının kısmi derleyici tarafından sıralaması bir örneğini budur. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir sürümü olan şablon işlevi  
  
 `template`\< **classT**> **void takas**( **T &**, **T &**)  
  
 algoritma sınıfı tarafından ataması çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
### <a name="example"></a>Örnek  
  Üye sınıfı kod örneğine bakın [multiset::swap](../standard-library/multiset-class.md#swap)şablon sürümü kullanımına ilişkin bir örnek `swap`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<Ayarlama >](../standard-library/set.md)



