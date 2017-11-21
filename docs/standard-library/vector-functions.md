---
title: "&lt;vektör&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vector/std::swap
ms.assetid: 6cdcf043-eef6-4330-83f0-4596fb9f968a
helpviewer_keywords: std::swap [vector]
caps.latest.revision: "10"
manager: ghogen
ms.openlocfilehash: e031d39204dd019281b52fd8d3a0127ecbc0424e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltvectorgt-functions"></a>&lt;vektör&gt; işlevleri

  
##  <a name="swap"></a>değiştirme  
 İki vektör öğelerini değiş tokuş eder.  
  
```  
template <class Type, class Allocator>  
void swap(vector<Type, Allocator>& left, vector<Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Parametreler  
 `right`  
 Öğeleri takas için sağlama vektör veya öğeleri olan vektör olanlar değiştirilebilmesi için vektör `left`.  
  
 `left`  
 Öğeleri olan vektör olanlar değiştirilebilmesi için vektör `right`.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini yürütmek için kapsayıcı sınıfı vektör özelleştirilmiş bir algoritma şablon işlevi olan `left`. [Vector::Swap](../standard-library/vector-class.md) *(sağ*). İşlev şablonlarının kısmi derleyici tarafından sıralaması örneğine bunlar. Şablon işlevleri işlev çağrısı şablonla eşleşmesi benzersiz değil şekilde aşırı zaman derleyici şablon işlevi en özelleştirilmiş sürümünü seçin. Genel bir şablon işlevi sürümü **şablonu** \< **sınıfı T**> **void takas**( **T &**, **T &**), algoritma sınıfı tarafından atama çalışır ve yavaş bir işlemdir. Her bir kapsayıcıdaki özel sürüm kapsayıcı sınıfı iç gösterimi ile çalışabilirsiniz gibi daha hızlıdır.  
  
### <a name="example"></a>Örnek  
  Üye işlevini kod örneğine bakın [vector::swap](../standard-library/vector-class.md) şablonu sürümünü kullanan bir örnek `swap`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<vektör >](../standard-library/vector.md)

