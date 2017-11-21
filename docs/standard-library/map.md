---
title: '&lt;Harita&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <map>
dev_langs: C++
helpviewer_keywords: map header
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7079794aed6140dd4d21a7bf5bc7576363811b5b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltmapgt"></a>&lt;eşleme&gt;
Kapsayıcı şablon sınıfları harita ve multimap ve bunların destekleyen şablonları tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <map>  
  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="operators"></a>İşleçler  
  
|Harita sürümü|Multimap sürüm|Açıklama|  
|-----------------|----------------------|-----------------|  
|[operator! = (map)](../standard-library/map-operators.md#op_neq)|[operator! = (multimap)](../standard-library/map-operators.md#op_neq)|Testleri işlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesine eşit değil.|  
|[operator < (map)](../standard-library/map-operators.md#op_eq_eq)|[operator < (multimap)](../standard-library/map-operators.md#op_eq_eq)|Testleri işlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesi'dan küçük.|  
|[operator < = (map)](../standard-library/map-operators.md#op_lt)|[İşleç\<= (multimap)](../standard-library/map-operators.md#op_lt)|Harita veya multimap nesne işlecinin sol tarafındaki harita veya sağ tarafında multimap nesneye eşit veya daha az ise testleri.|  
|[operator == (map)](../standard-library/map-operators.md#op_eq_eq)|[operator == (multimap)](../standard-library/map-operators.md#op_eq_eq_multimap)|İşlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesine eşitse testleri.|  
|[operator > (map)](../standard-library/map-operators.md#op_gt)|[operator > (multimap)](../standard-library/map-operators.md#op_gt_multimap)|Testleri işlecinin sol tarafındaki harita veya birden çok eşleme nesnesi sağ tarafında harita veya birden çok eşleme nesnesi değerinden daha büyük.|  
|[operator > = (map)](../standard-library/map-operators.md#op_gt_eq)|[operator > = (multimap)](../standard-library/map-operators.md#op_gt_eq_multimap)|Harita veya multimap nesne işlecinin sol tarafındaki sağ tarafında harita veya birden çok eşleme nesnesine eşit veya daha büyük ise testleri.|  
  
### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri  
  
|Harita sürümü|Multimap sürüm|Açıklama|  
|-----------------|----------------------|-----------------|  
|[Swap (map)](../standard-library/map-functions.md#swap)|[Swap (multimap)](../standard-library/map-functions.md#swap_multimap)|İki eşlemeleri veya multimaps öğelerini değiş tokuş eder.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[value_compare sınıfı](../standard-library/value-compare-class-map.md)|Bir harita öğelerini göreli sıralarına eşlemesindeki belirlemek için kendi anahtarları değerleri karşılaştırarak karşılaştırabilirsiniz bir işlev nesnesi sağlar.|  
|[map sınıfı](../standard-library/map-class.md)|Depolama ve alma verilerini öğelerin her biri benzersiz bir anahtar ile veriler otomatik olarak sıralanır sahip bir koleksiyon için kullanılır.|  
|[multimap sınıfı](../standard-library/multimap-class.md)|Depolama ve alma verilerini öğelerin her biri hangi verileri otomatik olarak sıralanır ve anahtarları, benzersiz değerlere sahip olması gerekmez. bir anahtarı olan bir koleksiyon için kullanılır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



