---
title: '&lt;chrono&gt;'
ms.date: 05/07/2019
f1_keywords:
- chrono/std::chrono::nanoseconds
- chrono/std::chrono::minutes
- chrono/std::chrono::seconds
- <chrono>
- chrono/std::chrono::hours
- chrono/std::chrono::milliseconds
- chrono/std::chrono::microseconds
ms.assetid: 844de749-f306-482e-89bc-6f53c99c8324
ms.openlocfilehash: 44620b6ea6c970027a8e9a023c0972c6dec43ee0
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220250"
---
# <a name="ltchronogt"></a>&lt;chrono&gt;

Standart üst bilgiyi dahil \<chrono > sınıfları ve işlevleri temsil eder ve süre ve zaman instants tanımlamak için.

Visual Studio 2015'te uygulamasının başlangıç `steady_clock` steadiness ve monotonicity C++ Standart gereksinimlerini karşılayacak şekilde değişti. `steady_clock` artık üzerinde QueryPerformanceCounter() temel ve `high_resolution_clock` için bir typedef sunulmuştur `steady_clock`. Sonuç olarak, Microsoft içinde C++ derleyici `steady_clock::time_point` için bir typedef sunulmuştur `chrono::time_point<steady_clock>`; ancak bu zorunlu diğer uygulamaları için geçerli değildir.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <chrono>
```

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|----------|-----------------|
|[duration Sınıfı](../standard-library/duration-class.md)|Bir zaman aralığı tutan bir türü açıklar.|
|[time_point Sınıfı](../standard-library/time-point-class.md)|Zamanda bir noktayı temsil eden bir türü açıklar.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|----------|-----------------|
|[common_type Yapısı](../standard-library/common-type-structure.md)|Şablon sınıfı uzmanlıklarını tanımlar [common_type](../standard-library/common-type-class.md) örneklemeleri için `duration` ve `time_point`.|
|[duration_values Yapısı](../standard-library/duration-values-structure.md)|İçin belirli değerler sağlar `duration` şablon parametresi `Rep`.|
|[steady_clock yapısı](../standard-library/steady-clock-struct.md)|Temsil eden bir `steady` saati.|
|[system_clock Yapısı](../standard-library/system-clock-structure.md)|Temsil eden bir *saat türü* sistemin gerçek zamanlı saatini temel alır.|
|[treat_as_floating_point Yapısı](../standard-library/treat-as-floating-point-structure.md)|Bir tür bir kayan nokta türü olarak ele alınıp alınamayacağını belirtir.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|----------|-----------------|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Yayınları bir `duration` belirli nesne.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Yayınları bir `time_point` belirli nesne.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[operator-](../standard-library/chrono-operators.md#operator-)|Veya negation işleci `duration` ve `time_point` nesneleri.|
|[operator!=](../standard-library/chrono-operators.md#op_neq)|İle kullanılan eşitsizlik işleci `duration` veya `time_point` nesneleri.|
|[mod işleci](../standard-library/chrono-operators.md#op_modulo)|Modül işlemleri için işleç `duration` nesneleri.|
|[operator *](../standard-library/chrono-operators.md#op_star)|Çarpma işleci için `duration` nesneleri.|
|[operator /](../standard-library/chrono-operators.md#op_div)|Bölme işleci için `duration` nesneleri.|
|[operator +](../standard-library/chrono-operators.md#op_add)|Ekler `duration` ve `time_point` nesneleri.|
|[İşleci&lt;](../standard-library/chrono-operators.md#op_lt)|Az olup olmadığını belirler `duration` veya `time_point` nesnedir daha az `duration` veya `time_point` nesne.|
|[İşleci&lt;=](../standard-library/chrono-operators.md#op_lt_eq)|Az olup olmadığını belirler `duration` veya `time_point` nesnedir küçüktür veya eşittir diğerine `duration` veya `time_point` nesne.|
|[operator==](../standard-library/chrono-operators.md#op_eq_eq)|İki olup olmadığını belirler `duration` nesneleri aynı uzunluğa sahip zaman aralıklarını temsil etmek veya iki olduğunu `time_point` nesneleri zaman içinde aynı noktaya temsil eder.|
|[İşleci&gt;](../standard-library/chrono-operators.md#op_gt)|Az olup olmadığını belirler `duration` veya `time_point` nesnedir diğerinden daha büyük `duration` veya `time_point` nesne.|
|[İşleci&gt;=](../standard-library/chrono-operators.md#op_gt_eq)|Az olup olmadığını belirler `duration` veya `time_point` nesnedir büyüktür veya eşittir diğerine `duration` veya `time_point` nesne.|

### <a name="predefined-duration-types"></a>Önceden tanımlı süre türleri

Aşağıdaki tür tanımları içinde kullanılan oranı türleri hakkında daha fazla bilgi için bkz. [ \<oranı >](../standard-library/ratio.md).

|tür tanımı|Açıklama|
|-------------|-----------------|
|`typedef duration<long long, nano> nanoseconds;`|İçin eş anlamlı bir `duration` içerir tek bir değer çizgisi süre olan türü.|
|`typedef duration<long long, micro> microseconds;`|İçin eş anlamlı bir `duration` bir mikrosaniye ölçeğinde değer çizgisi aralığının olan türü.|
|`typedef duration<long long, milli> milliseconds;`|İçin eş anlamlı bir `duration` bir milisaniyeden kısa bir değer çizgisi süre olan türü.|
|`typedef duration<long long> seconds;`|İçin eş anlamlı bir `duration` bir saniyelik bir dönemini olan türü.|
|`typedef duration<int, ratio<60> > minutes;`|İçin eş anlamlı bir `duration` , bir dakikalık bir değer çizgisi süre olan türü.|
|`typedef duration<int, ratio<3600> > hours;`|İçin eş anlamlı bir `duration` bir saatlik bir değer çizgisi süre olan türü.|

### <a name="literals"></a>Sabit değerler

**(C ++ 11)**  \<Chrono > Üstbilgi aşağıdakileri tanımlar [kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md) büyük kolaylık, tür güvenliği ve sürdürülebilirliği kodunuzu kullanabilirsiniz. Bu sabit değerleri tanımlanan `literals::chrono_literals` satır içi ad alanı ve de kapsamı ne zaman std::chrono kapsamda olan.

|değişmez değer|Açıklama|
|-------------|-----------------|
|chrono::hours işleci "" h (imzasız uzun uzun Val)|Saat bir tamsayı değeri belirtir.|
|chrono::Duration\<çift oranı\<3600 >> işleci "" h (uzun çift Val)|Bir kayan nokta değeri belirler.|
|chrono::minutes (işleci "" min) (imzasız uzun uzun Val)|Dakika bir tamsayı değeri belirtir.|
|chrono::Duration\<çift oranı\<60 >> (işleci "" min) (Val uzun çift)|Dakika, bir kayan nokta değeri belirtir.|
|chrono::seconds işleci "" s (imzasız uzun uzun Val)|Dakika bir tamsayı değeri belirtir.|
|chrono::Duration\<çift > işleci "" s (uzun çift Val)|Saniye kayan nokta değerini belirtir.|
|chrono::milliseconds işleci "" ms (imzasız uzun uzun Val)|Milisaniye bir tamsayı değeri belirtir.|
|chrono::Duration\<çift, milisaniye > işleci "" ms (uzun çift Val)|Milisaniye kayan nokta değerini belirtir.|
|chrono::microseconds işleci "" ABD (imzasız uzun uzun Val)|Mikrosaniye bir tamsayı değeri belirtir.|
|chrono::Duration\<çift, mikro > işleci "" ABD (uzun çift Val)|Mikrosaniye bir kayan nokta değeri belirtir.|
|chrono::nanoseconds işleci "" ns (imzasız uzun uzun Val)|Etkinliğin nanosaniye bir tamsayı değeri belirtir.|
|chrono::Duration\<çift, nano > işleci "" ns (uzun çift Val)|Etkinliğin nanosaniye bir kayan nokta değeri belirtir.|
|||

Aşağıdaki örnekler chrono değişmez değerleri kullanmayı gösterir.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="remarks"></a>Açıklamalar

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
