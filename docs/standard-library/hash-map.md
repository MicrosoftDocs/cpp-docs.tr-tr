---
title: '&lt;hash_map&gt; | Microsoft Docs'
ms.custom: 
ms.date: 09/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <hash_map>
- std::<hash_map>
dev_langs: C++
helpviewer_keywords: hash_map header
ms.assetid: 0765708a-a668-42a2-9800-654c857bdcc2
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e69496f3383233c45ba994305342c3340459a287
ms.sourcegitcommit: ca2f94dfd015e0098a6eaf5c793ec532f1c97de1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2017
---
# <a name="lthashmapgt"></a>&lt;hash_map&gt;
> [!NOTE]
>  Bu üst kullanılmıyor. Alternatif [ \<unordered_map >](unordered-map.md).  
  
 Kapsayıcı şablon sınıfları hash_map ve hash_multimap ve bunların destekleyen şablonları tanımlar.  
 
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <hash_map>  
  
```  
  
### <a name="operators"></a>İşleçler  
  
|Hash_map sürüm|Hash_multimap sürüm|Açıklama|  
|-----------------------|----------------------------|-----------------|  
|[operator! = (hash_map)](hash-map-operators.md#op_neq)|[operator!=(hash_multimap)](hash-map-operators.md#op_neq_mm)|Testleri işlecinin sol tarafındaki hash_map veya hash_multimap nesnesi sağ tarafında hash_map veya hash_multimap nesnesine eşit değil.|  
|[operator == (hash_map)](hash-map-operators.md#op_eq_eq)|[işleç == (hash_multimap)] ((karma harita operators.md #op_eq_eq_mm)|Hash_map veya hash_multimap nesne işlecinin sol tarafındaki sağ tarafında hash_map veya hash_multimap nesnesine eşitse testleri.|  
  
### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri  
  
|Hash_map sürüm|Hash_multimap sürüm|Açıklama|  
|-----------------------|----------------------------|-----------------|  
|[Swap (hash_map)](hash-map-class.md#swap)|[Swap (hash_multimap)](hash-multimap-class.md#swap)|İki hash_maps veya hash_multimaps öğelerini değiş tokuş eder.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[hash_compare sınıfı](hash-compare-class.md)|Herhangi bir karma ilişkilendirilebilir kapsayıcıları tarafından kullanılan bir nesneyi tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak **nitelikler** sıralamak ve içerdikleri öğeleri karma parametre nesnesi.|  
|[value_compare sınıfı](value-compare-class.md)|Hash_map içindeki göreli sıralarına belirlemek için kendi anahtarları değerlerinin karşılaştırılmasıyla bir hash_map öğelerini karşılaştırabilirsiniz bir işlev nesnesi sağlar.|  
|[hash_map sınıfı](hash-map-class.md)|Her öğe değeri benzersiz olan sıralama anahtarı olan bir çift olduğu bir koleksiyon ve ilişkili veriler bir değer verileri hızlı alınmasını ve depolama için kullanılır.|  
|[hash_multimap sınıfı](hash-multimap-class.md)|Her öğe değeri benzersiz olması gerekmez sıralama anahtarı olan bir çift olduğu bir koleksiyon ve ilişkili veriler bir değer verileri hızlı alınmasını ve depolama için kullanılır.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<hash_map >  
  
 **Namespace:** stdext  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](cpp-standard-library-reference.md)



