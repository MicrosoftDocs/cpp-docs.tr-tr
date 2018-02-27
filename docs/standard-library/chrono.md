---
title: '&lt;chrono&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- chrono/std::chrono::nanoseconds
- chrono/std::chrono::minutes
- chrono/std::chrono::seconds
- <chrono>
- chrono/std::chrono::hours
- chrono/std::chrono::milliseconds
- chrono/std::chrono::microseconds
dev_langs:
- C++
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 255c70eeb29e8bedaeec43d9844ca41b42fb470a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltchronogt"></a>&lt;chrono&gt;
Standart üstbilgisini \<chrono > sınıfları ve temsil eder ve süreler ve zaman instants değiştirmek işlevleri tanımlamak için.  
  
 Visual Studio 2015'te, uygulanması başlayarak `steady_clock` steadiness ve monotonicity C++ Standart gereksinimlerini karşılamak üzere değişti. `steady_clock` artık QueryPerformanceCounter() üzerinde temel ve `high_resolution_clock` typedef için sunulmuştur `steady_clock`. Sonuç olarak, Visual C++'ta `steady_clock::time_point` typedef için sunulmuştur `chrono::time_point<steady_clock>`; ancak, bu mutlaka diğer uygulamaları için geçerli değildir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
#include <chrono>  
```  

### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[duration Sınıfı](../standard-library/duration-class.md)|Bir zaman aralığı tutan bir türünü tanımlar.|  
|[time_point Sınıfı](../standard-library/time-point-class.md)|Bir noktayı zamanında temsil eden bir tür açıklar.|  
  
### <a name="structs"></a>Yapılar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[common_type Yapısı](../standard-library/common-type-structure.md)|Şablon sınıfının özelleştirmeleri açıklar [common_type](../standard-library/common-type-class.md) işlemlerinden için `duration` ve `time_point`.|  
|[duration_values Yapısı](../standard-library/duration-values-structure.md)|Belirli değerleri sağlar `duration` şablon parametresi `Rep`.|  
|[steady_clock yapısı](../standard-library/steady-clock-struct.md)|Temsil eden bir `steady` saat.|  
|[system_clock Yapısı](../standard-library/system-clock-structure.md)|Temsil eden bir *saat türü* sistem gerçek zamanlı saati dayanır.|  
|[treat_as_floating_point Yapısı](../standard-library/treat-as-floating-point-structure.md)|Bir tür kayan noktalı bir tür olarak kabul olup olmadığını belirtir.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Atamalar bir `duration` nesne belirtilen türe.|  
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Atamalar bir `time_point` nesne belirtilen türe.|  
  
### <a name="operators"></a>İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator-](../standard-library/chrono-operators.md#operator-)|İşleç çıkarması veya değilleme işlemi için `duration` ve `time_point` nesneleri.|  
|[operator!=](../standard-library/chrono-operators.md#op_neq)|İle birlikte kullanılan eşitsizlik işleci `duration` veya `time_point` nesneleri.|  
|[mod işleci](../standard-library/chrono-operators.md#op_modulo)|İşlemler modulo işleci için `duration` nesneleri.|  
|[operator*](../standard-library/chrono-operators.md#op_star)|Çarpma işleci için `duration` nesneleri.|  
|[operator /](../standard-library/chrono-operators.md#op_div)|Bölme işleci için `duration` nesneleri.|  
|[operator+](../standard-library/chrono-operators.md#op_add)|Ekler `duration` ve `time_point` nesneleri.|  
|[işleci&lt;](../standard-library/chrono-operators.md#op_lt)|Bir olup olmadığını belirleyen `duration` veya `time_point` nesnesi, başka değerinden `duration` veya `time_point` nesnesi.|  
|[işleci&lt;=](../standard-library/chrono-operators.md#op_lt_eq)|Bir olup olmadığını belirleyen `duration` veya `time_point` nesnesidir değerinden küçük veya eşit başka `duration` veya `time_point` nesnesi.|  
|[operator==](../standard-library/chrono-operators.md#op_eq_eq)|İki olup olmadığını belirleyen `duration` nesneleri temsil aynı uzunlukta olan zaman aralıkları mı iki `time_point` nesneleri zamanında aynı noktasını temsil eder.|  
|[işleci&gt;](../standard-library/chrono-operators.md#op_gt)|Bir olup olmadığını belirleyen `duration` veya `time_point` nesnesidir diğerinden daha büyük `duration` veya `time_point` nesnesi.|  
|[işleci&gt;=](../standard-library/chrono-operators.md#op_gt_eq)|Bir olup olmadığını belirleyen `duration` veya `time_point` nesnesidir büyük veya ona eşit başka bir `duration` veya `time_point` nesnesi.|  
  
### <a name="predefined-duration-types"></a>Önceden tanımlı süre türleri  
 Aşağıdaki tür tanımları içinde kullanılan oranı türleri hakkında daha fazla bilgi için bkz: [ \<oranı >](../standard-library/ratio.md).  
  
|TypeDef|Açıklama|  
|-------------|-----------------|  
|`typedef duration<long long, nano> nanoseconds;`|İçin eş anlamlı bir `duration` bir nanosaniyelik bir onay işareti süre olan türü.|  
|`typedef duration<long long, micro> microseconds;`|İçin eş anlamlı bir `duration` bir milisaniyeye bir onay işareti süre olan türü.|  
|`typedef duration<long long, milli> milliseconds;`|İçin eş anlamlı bir `duration` bir milisaniyelik bir onay işareti süre olan türü.|  
|`typedef duration<long long> seconds;`|İçin eş anlamlı bir `duration` bir ikinci onay süreyi olan türü.|  
|`typedef duration<int, ratio<60> > minutes;`|İçin eş anlamlı bir `duration` bir dakika bir onay işareti süre olan türü.|  
|`typedef duration<int, ratio<3600> > hours;`|İçin eş anlamlı bir `duration` onay süresi bir saat olan türü.|  
  
### <a name="literals"></a>Sabit değerler  
 **(C ++ 11)**  \<Chrono > Üstbilgi tanımlar aşağıdaki [kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md) büyük kolaylık, tür güvenliği ve kodunuzu bakımı için kullanabilirsiniz. Bu değişmez değerleri tanımlanan `literals::chrono_literals` satır içi ad alanı ve yazılımında kapsam ne zaman std::chrono kapsamında değil.  
  
|Değişmez değer|Açıklama|  
|-------------|-----------------|  
|chrono::hours işleci "" h (imzasız uzun uzun Val)|Saat bir tam sayı değeri belirtir.|  
|chrono::Duration\<çift oranı\<3600 >> işleci "" h (uzun çift Val)|Saat kayan noktalı bir sayıyı belirtir.|  
|chrono::minutes (işleci "" min) (uzun uzun Val imzasız)|Dakika bir tam sayı değeri belirtir.|  
|chrono::Duration\<çift oranı\<60 >> (işleci "" min) (Val uzun çift)|Dakika kayan noktalı bir sayıyı belirtir.|  
|chrono::seconds işleci "" s (imzasız uzun uzun Val)|Dakika bir tam sayı değeri belirtir.|  
|chrono::Duration\<çift > işleci "" s (uzun çift Val)|Saniye kayan noktalı bir sayıyı belirtir.|  
|chrono::milliseconds işleci "" ms (imzasız uzun uzun Val)|Milisaniye bir tam sayı değeri belirtir.|  
|chrono::Duration\<çift, milisaniye > işleci "" ms (uzun çift Val)|Milisaniye kayan noktalı bir sayıyı belirtir.|  
|chrono::microseconds işleci "" bize (imzasız uzun uzun Val)|Mikrosaniye bir tam sayı değeri olarak belirtir.|  
|chrono::Duration\<çift, mikro > işleci "" bize (uzun çift Val)|Mikrosaniye bir kayan nokta değeri olarak belirtir.|  
|chrono::nanoseconds işleci "" ns (imzasız uzun uzun Val)|Nanosaniye bir tam sayı değeri olarak belirtir.|  
|chrono::Duration\<çift, nano > işleci "" ns (uzun çift Val)|Nanosaniye bir kayan nokta değeri olarak belirtir.|  
|||  
  
Aşağıdaki örnekler chrono değişmez değerleri kullanmayı gösterir.  
  
```  
constexpr auto day = 24h;  
constexpr auto week = 24h* 7;  
constexpr auto my_duration_unit = 108ms;  
```  
## <a name="remarks"></a>Açıklamalar  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)



