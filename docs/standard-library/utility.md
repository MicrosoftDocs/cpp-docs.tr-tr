---
title: "&lt;yardımcı programı&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <utility>
dev_langs: C++
helpviewer_keywords: utility header
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4cbb348ec11c9c4f832c993ad1e4799c8a39aad2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ltutilitygt"></a>&lt;yardımcı programı&gt;
C++ Standart Kitaplığı türleri, İşlevler ve oluşturmak ve iki nesne bir oldukları gibi kabul gerektiğinde yararlı olan nesneleri çiftlerini yönetmek için yardımcı işleçler tanımlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
#include <utility>  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Çiftleri C++ Standart Kitaplığı'nda yaygın olarak kullanılır. Çeşitli işlevleri için dönüş değerlerini ve bağımsız değişkenler olarak hem olarak öğe türleri gibi kapsayıcıları için gereklidirler [eşleme sınıf](../standard-library/map-class.md) ve [multimap sınıfı](../standard-library/multimap-class.md). \<Yardımcı programı > üstbilgisi tarafından dahil otomatik olarak \<harita > kendi anahtar/değer yönetilmesine yardımcı olmak için çifti öğelerini yazın.  
  
### <a name="classes"></a>Sınıflar  
  
|||  
|-|-|  
|[tuple_element](../standard-library/tuple-element-class-tuple.md)|Türü saran bir sınıf bir `pair` öğesi.|  
|[tuple_size](../standard-library/tuple-size-class-tuple.md)|Saran bir sınıf `pair` öğe sayısı.|  
  
### <a name="functions"></a>İşlevler  
  
|||  
|-|-|  
|[İlet](../standard-library/utility-functions.md#forward)|Başvuru türü korur (ya da `lvalue` veya `rvalue`) tarafından kusursuz iletme getirilmemeli gelen bağımsız değişken.|  
|[get](../standard-library/utility-functions.md#get)|Bir öğeyi alır işlevi bir `pair` nesnesi.|  
|[make_pair](../standard-library/utility-functions.md#make_pair)|Türündeki nesneleri oluşturmak için kullanılan bir şablon yardımcı işlevini `pair`, bileşen türleri parametre olarak geçirilen veri türleri burada dayanır.|  
|[taşıma](../standard-library/utility-functions.md#move)|Bağımsız değişken olarak geçirilen döndürür bir `rvalue` başvuru.|  
|[değiştirme](../standard-library/utility-functions.md#swap)|İki öğelerini alış verişleri `pair` nesneleri.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[operator!=](../standard-library/utility-operators.md#op_neq)|Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi eşit değil.|  
|[operator ==](../standard-library/utility-operators.md#op_eq_eq)|Sağ taraftaki çifti nesnesi işlecinin sol tarafındaki çifti nesnesi eşitse testleri.|  
|[operator <](../standard-library/utility-operators.md#op_lt)|Çift işlecinin sol tarafında nesne sağlayıp sağlamadığını test azdır sağ tarafında çifti nesnesi.|  
|[işleci\<=](../standard-library/utility-operators.md#op_gt_eq)|Çift işlecinin sol tarafında nesne sağlayıp sağlamadığını test sağ tarafında çifti nesnesi eşit veya daha az olur.|  
|[operator >](../standard-library/utility-operators.md#op_gt)|Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi değerinden daha büyük.|  
|[operator>=](../standard-library/utility-operators.md#op_gt_eq)|Testleri işlecinin sol tarafındaki çifti nesnesi sağ tarafında çifti nesnesi eşit veya daha büyük.|  
  
### <a name="structs"></a>Yapılar  
  
|||  
|-|-|  
|[kimlik](../standard-library/identity-structure.md)||  
|[çifti](../standard-library/pair-structure.md)|İki nesne tek bir nesne olarak davran olanağı sağlayan bir türü.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



