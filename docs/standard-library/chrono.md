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
ms.openlocfilehash: 72d16b068f337fe935d07e1eb2d0e2b74de6268f
ms.sourcegitcommit: 3590dc146525807500c0477d6c9c17a4a8a2d658
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68244857"
---
# <a name="ltchronogt"></a>&lt;chrono&gt;

Standart üst bilgiyi dahil \<chrono > sınıfları ve işlevleri temsil eder ve süre ve zaman instants tanımlamak için.

Visual Studio 2015'te uygulamasının başlangıç `steady_clock` steadiness ve monotonicity C++ Standart gereksinimlerini karşılayacak şekilde değişti. `steady_clock` artık üzerinde QueryPerformanceCounter() temel ve `high_resolution_clock` için bir typedef sunulmuştur `steady_clock`. Sonuç olarak, Microsoft içinde C++ derleyici `steady_clock::time_point` için bir typedef sunulmuştur `chrono::time_point<steady_clock>`; ancak, bu kural, diğer uygulamalar için durum mutlaka geçerli değildir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<chrono >

**Namespace:** std

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[duration Sınıfı](../standard-library/duration-class.md)|Bir zaman aralığı tutan bir türü açıklar.|
|[time_point Sınıfı](../standard-library/time-point-class.md)|Zamanda bir noktayı temsil eden bir türü açıklar.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[common_type Yapısı](../standard-library/common-type-structure.md)|Şablon sınıfı uzmanlıklarını tanımlar [common_type](../standard-library/common-type-class.md) örneklemeleri için `duration` ve `time_point`.|
|[duration_values Yapısı](../standard-library/duration-values-structure.md)|İçin belirli değerler sağlar `duration` şablon parametresi `Rep`.|
|[high_resolution_clock yapısı](../standard-library/high-resolution-clock-struct.md)||
|[steady_clock yapısı](../standard-library/steady-clock-struct.md)|Temsil eden bir `steady` saati.|
|[system_clock Yapısı](../standard-library/system-clock-structure.md)|Temsil eden bir *saat türü* sistemin gerçek zamanlı saatini temel alır.|
|[treat_as_floating_point Yapısı](../standard-library/treat-as-floating-point-structure.md)|Bir tür bir kayan nokta türü olarak ele alınıp alınamayacağını belirtir.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Yayınları bir `duration` belirli nesne.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Yayınları bir `time_point` belirli nesne.|

### <a name="operators"></a>İşleçler

|||
|-|-|
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

### <a name="typedefs-predefined-duration-types"></a>Tür tanımları (önceden tanımlanmış süresi türleri)

Aşağıdaki tür tanımları içinde kullanılan oranı türleri hakkında daha fazla bilgi için bkz. [ \<oranı >](../standard-library/ratio.md).

||| ||| | `typedef duration<long long, nano> nanoseconds;`| İçin eş anlamlı bir `duration` 1 içerir değer çizgisi aralığının olan türü. | |`typedef duration<long long, micro> microseconds;`| İçin eş anlamlı bir `duration` 1 mikrosaniye ölçeğinde değer çizgisi aralığının olan türü. | |`typedef duration<long long, milli> milliseconds;`| İçin eş anlamlı bir `duration` 1 milisaniyeden kısa bir değer çizgisi süre olan türü. | |`typedef duration<long long> seconds;`| İçin eş anlamlı bir `duration` bir değer çizgisi süresi 1 saniye olan türü. | |`typedef duration<int, ratio<60> > minutes;`| İçin eş anlamlı bir `duration` 1 dakikalık bir değer çizgisi süre olan türü. | |`typedef duration<int, ratio<3600> > hours;`| İçin eş anlamlı bir `duration` 1 saatlik bir dönemini olan türü. |

### <a name="literals"></a>Sabit değerler

**(C ++ 11)**  \<Chrono > Üstbilgi aşağıdakileri tanımlar [kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md) büyük kolaylık, tür güvenliği ve sürdürülebilirliği kodunuzu kullanabilirsiniz. Bu sabit değerleri tanımlanan `literals::chrono_literals` satır içi ad alanı ve de kapsamı ne zaman std::chrono kapsamda olan.

|||
|-|-|
|saat işleci "" h (imzasız uzun uzun Val)|Saat bir tamsayı değeri belirtir.|
|süre\<çift oranı\<3600 >> işleci "" h (uzun çift Val)|Bir kayan nokta değeri belirler.|
|dakika (işleci "" min) (imzasız uzun uzun Val)|Dakika bir tamsayı değeri belirtir.|
|süre\<çift oranı\<60 >> (işleci "" min) (Val uzun çift)|Dakika, bir kayan nokta değeri belirtir.|
|saniye işleci "" s (imzasız uzun uzun Val)|Dakika bir tamsayı değeri belirtir.|
|süre\<çift > işleci "" s (uzun çift Val)|Saniye kayan nokta değerini belirtir.|
|milisaniye işleci "" ms (imzasız uzun uzun Val)|Milisaniye bir tamsayı değeri belirtir.|
|süre\<çift, milisaniye > işleci "" ms (uzun çift Val)|Milisaniye kayan nokta değerini belirtir.|
|mikrosaniye işleci "" ABD (imzasız uzun uzun Val)|Mikrosaniye bir tamsayı değeri belirtir.|
|süre\<çift, mikro > işleci "" ABD (uzun çift Val)|Mikrosaniye bir kayan nokta değeri belirtir.|
|Etkinliğin nanosaniye işleci "" ns (imzasız uzun uzun Val)|Etkinliğin nanosaniye bir tamsayı değeri belirtir.|
|süre\<çift, nano > işleci "" ns (uzun çift Val)|Etkinliğin nanosaniye bir kayan nokta değeri belirtir.|

Aşağıdaki örnekler chrono değişmez değerleri kullanmayı gösterir.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
