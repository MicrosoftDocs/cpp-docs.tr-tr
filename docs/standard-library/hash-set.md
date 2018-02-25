---
title: '&lt;hash_set&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <hash_set>
- std::<hash_set>
dev_langs:
- C++
helpviewer_keywords:
- hash_set header
ms.assetid: 6b556967-c808-4869-9b4d-f9e030864435
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d9e439d2e87f6bf8b23aea09f1f3dd7781f2c7e1
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="lthashsetgt"></a>&lt;hash_set&gt;
> [!NOTE]
>  Bu üst kullanılmıyor. Alternatif [< unordered_set >](../standard-library/unordered-set.md).  
  
 Kapsayıcı şablon sınıfları hash_set ve hash_multiset ve bunların destekleyen şablonları tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <hash_set>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
### <a name="operators"></a>İşleçler  
  
|Hash_set sürüm|Hash_multiset sürüm|Açıklama|  
|-----------------------|----------------------------|-----------------|  
|[operator!= (hash_set)](../standard-library/hash-set-operators.md#op_neq)|[operator!= (hash_multiset)](../standard-library/hash-set-operators.md#op_neq)|Testleri işlecinin sol tarafındaki hash_set veya hash_multiset nesnesi sağ tarafında hash_set veya hash_multiset nesnesine eşit değil.|  
|[operator== (hash_set)](../standard-library/hash-set-operators.md#op_eq_eq)|[operator== (hash_multiset)](../standard-library/hash-set-operators.md#op_eq_eq)|Hash_set veya hash_multiset nesne işlecinin sol tarafındaki sağ tarafında hash_set veya hash_multiset nesnesine eşitse testleri.|  
  
### <a name="specialized-template-functions"></a>Özelleşmiş Şablon İşlevleri  
  
|Hash_set sürüm|Hash_multiset sürüm|Açıklama|  
|-----------------------|----------------------------|-----------------|  
|[swap (hash_set)](../standard-library/hash-set-functions.md#swap)|[swap (hash_multiset)](../standard-library/hash-set-functions.md#swap_hash_multiset)|İki hash_sets veya hash_multisets öğelerini değiş tokuş eder.|  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[hash_compare Sınıfı](../standard-library/hash-compare-class.md)|Herhangi bir karma ilişkilendirilebilir kapsayıcıları tarafından kullanılan bir nesneyi tanımlayan — hash_map, hash_multimap, hash_set, veya hash_multiset — varsayılan olarak **nitelikler** sıralamak ve içerdikleri öğeleri karma parametre nesnesi.|  
|[hash_set Sınıfı](../standard-library/hash-set-class.md)|Hızlı alınması bulunan öğeleri değerlerini benzersiz ve anahtar değerleri olarak hizmet veren bir koleksiyon verileri ve depolama için kullanılır.|  
|[hash_multiset Sınıfı](../standard-library/hash-multiset-class.md)|Hızlı alınması bulunan öğeleri değerlerini benzersiz ve anahtar değerleri olarak hizmet veren bir koleksiyon verileri ve depolama için kullanılır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [C++ Standart Kitaplığı Başvurusu](../standard-library/cpp-standard-library-reference.md)



