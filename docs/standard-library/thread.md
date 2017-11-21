---
title: "&lt;iş parçacığı&gt; | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <thread>
dev_langs: C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7685bd1c112651b07540fefd2a28be91c9671706
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltthreadgt"></a>&lt;iş parçacığı&gt;
Standart üstbilgisini \<iş parçacığı > sınıfı tanımlamak için `thread` ve çeşitli destekleyici işlevler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Kullanarak derlenmiş kod **/CLR**, bu başlığı engellenir.  
  
 `__STDCPP_THREADS__` Makrosu iş parçacıklarını bu üstbilgisi tarafından desteklendiğini belirtmek için sıfır olmayan bir değer olarak tanımlanır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-classes"></a>Genel sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[iş parçacığı sınıfı](../standard-library/thread-class.md)|İnceleyin ve bir iş parçacığı bir uygulamada yürütme yönetmek için kullanılan nesneyi tanımlar.|  
  
### <a name="public-structures"></a>Genel yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[hash yapısı (Standart C++ Kitaplığı)](../standard-library/hash-structure-stl.md)|Benzersiz olarak tarafından belirlenen bir değer döndüren bir üye işlevi tanımlayan bir `thread::id`. Üye işlevini tanımlayan bir [karma](../standard-library/hash-class.md) eşleme türü değerleri için uygun işlevi `thread::id` dizin değerlerin bir dağıtım.|  
  
### <a name="public-functions"></a>Genel işlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_ıd](../standard-library/thread-functions.md#get_id)|Geçerli yürütme iş parçacığı benzersiz olarak tanımlar.|  
|[sleep_for](../standard-library/thread-functions.md#sleep_for)|Çağıran iş parçacığı engeller.|  
|[sleep_until](../standard-library/thread-functions.md#sleep_until)|Çağıran iş parçacığı en az belirtilen zamana kadar engeller.|  
|[değiştirme](../standard-library/thread-functions.md#swap)|İki durumlarını alış verişleri `thread` nesneleri.|  
|[uyarı simgesi](../standard-library/thread-functions.md#yield)|Geçerli iş parçacığının normal şekilde çalışmaya devam eder olsa bile diğer iş parçacıklarını çalıştırmak için işletim sistemi işaret eder.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator > = işleci](../standard-library/thread-operators.md#op_gt_eq)|Bir olup olmadığını belirleyen `thread::id` nesnesidir başka eşit veya daha büyük.|  
|[operator > işleci](../standard-library/thread-operators.md#op_gt)|Bir olup olmadığını belirleyen `thread::id` nesnesidir diğerinden daha büyük.|  
|[operator < = işleci](../standard-library/thread-operators.md#op_lt_eq)|Bir olup olmadığını belirleyen `thread::id` nesnesidir değerinden küçük veya eşit başka.|  
|[operator < işleci](../standard-library/thread-operators.md#op_lt)|Bir olup olmadığını belirleyen `thread::id` nesnesi, başka değerinden.|  
|[operator! = işleci](../standard-library/thread-operators.md#op_neq)|İki karşılaştırır `thread::id` eşitsizlik nesneleri.|  
|[operator == işleci](../standard-library/thread-operators.md#op_eq_eq)|İki karşılaştırır `thread::id` nesneleri eşitlik için.|  
|[işleç << işleci](../standard-library/thread-operators.md#op_lt_lt)|Bir metin gösterimini ekler bir `thread::id` bir akış nesnesine.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)   
 [C++ Standart kitaplığında iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)

