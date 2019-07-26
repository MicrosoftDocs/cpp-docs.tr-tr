---
title: '&lt;Chrono&gt;'
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
ms.openlocfilehash: f01b00a1469cdf82590a1bdfc742312ec96912c9
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459458"
---
# <a name="ltchronogt"></a>&lt;Chrono&gt;

Zaman sürelerini ve zaman \<aşamalarını temsil eden ve işleyen sınıfları ve işlevleri tanımlamak için, bir standart üst bilgi hatası > ekleyin.

Visual Studio 2015 ' den başlayarak uygulaması `steady_clock` , steadiness ve monoton için C++ standart gereksinimleri karşılayacak şekilde değiştirilmiştir. `steady_clock`Artık, QueryPerformanceCounter 'yi () temel alır `high_resolution_clock` ve artık için `steady_clock`bir typedef. Sonuç olarak, Microsoft C++ derleyicisi `steady_clock::time_point` artık için `chrono::time_point<steady_clock>`bir typedef 'dir; ancak, bu kural diğer uygulamalar için durum değildir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<> hatası

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[duration Sınıfı](../standard-library/duration-class.md)|Bir zaman aralığı tutan bir türü açıklar.|
|[time_point Sınıfı](../standard-library/time-point-class.md)|Zaman içinde bir noktayı temsil eden bir türü açıklar.|

### <a name="structs"></a>Yapılar

|||
|-|-|
|[common_type Yapısı](../standard-library/common-type-structure.md)|`duration` [](../standard-library/common-type-class.md) Ve`time_point`örneklemeleri için common_type şablon sınıfının uzmanlık özelliklerini açıklar.|
|[duration_values Yapısı](../standard-library/duration-values-structure.md)|`duration` Şablon parametresi`Rep`için belirli değerler sağlar.|
|[high_resolution_clock yapısı](../standard-library/high-resolution-clock-struct.md)||
|[steady_clock yapısı](../standard-library/steady-clock-struct.md)|Bir `steady` saati temsil eder.|
|[system_clock Yapısı](../standard-library/system-clock-structure.md)|Sistemin gerçek zamanlı saatini temel alan bir *Saat türünü* temsil eder.|
|[treat_as_floating_point Yapısı](../standard-library/treat-as-floating-point-structure.md)|Bir türün kayan nokta türü olarak değerlendirilip değerlendirilmeyeceğini belirtir.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Bir `duration` nesneyi belirtilen bir türe yayınlar.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Bir `time_point` nesneyi belirtilen bir türe yayınlar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işlecinde](../standard-library/chrono-operators.md#operator-)|`duration` Ve nesnelerinin çıkarma ve `time_point` olumsuzlama işleci.|
|[operator!=](../standard-library/chrono-operators.md#op_neq)|`duration` Veya`time_point` nesneleriyle kullanılan eşitsizlik işleci.|
|[işleç modül](../standard-library/chrono-operators.md#op_modulo)|`duration` Nesnelerdeki modül işlemleri için işleç.|
|[işlecinde](../standard-library/chrono-operators.md#op_star)|Nesneler için `duration` çarpma işleci.|
|[işlecinde](../standard-library/chrono-operators.md#op_div)|Nesneler için `duration` bölme işleci.|
|[işleç +](../standard-library/chrono-operators.md#op_add)|Ekler `duration` ve`time_point` nesneler.|
|[işlecinde&lt;](../standard-library/chrono-operators.md#op_lt)|Bir `duration` veya `time_point` nesnenin başka bir `duration` veya `time_point` nesnesinden küçük olup olmadığını belirler.|
|[işlecinde&lt;=](../standard-library/chrono-operators.md#op_lt_eq)|Bir `duration` ya da `time_point` nesnenin bir veya başka bir `duration` `time_point` nesneden küçük ya da ona eşit olup olmadığını belirler.|
|[operator==](../standard-library/chrono-operators.md#op_eq_eq)|İki `duration` nesnenin aynı uzunluğa sahip zaman aralıklarını mi temsil ettiğini yoksa iki `time_point` nesnenin de aynı noktayı temsil edip etmediğini belirler.|
|[işlecinde&gt;](../standard-library/chrono-operators.md#op_gt)|Bir `duration` veya `time_point` nesnenin başka bir `duration` veya `time_point` nesnesinden büyük olup olmadığını belirler.|
|[işlecinde&gt;=](../standard-library/chrono-operators.md#op_gt_eq)|Bir `duration` ya da `time_point` nesnenin başka bir `duration` veya `time_point` nesneden büyük veya ona eşit olup olmadığını belirler.|

### <a name="typedefs-predefined-duration-types"></a>Typedefs (önceden tanımlanmış süre türleri)

Aşağıdaki Typedefs 'ta kullanılan oran türleri hakkında daha fazla bilgi için bkz [ \<. Ratio >](../standard-library/ratio.md).

||| ||| | `typedef duration<long long, nano> nanoseconds;`| Değer 1 nanosaniyelik `duration` olan bir tür için eş anlamlı. | | |`typedef duration<long long, micro> microseconds;` 1 mikrosaniyelik `duration` bir işaret dönemi içeren bir tür için eş anlamlı. | | |`typedef duration<long long, milli> milliseconds;` 1 milisaniyelik `duration` değer süresine sahip bir türün eş anlamlısı. | | |`typedef duration<long long> seconds;` Değer 1 saniye `duration` olan bir tür için eş anlamlı. | | |`typedef duration<int, ratio<60> > minutes;` 1 dakikalık bir `duration` işaret dönemi içeren bir tür için eş anlamlı. | | |`typedef duration<int, ratio<3600> > hours;` Değer 1 saat `duration` olan bir tür için eş anlamlı. |

### <a name="literals"></a>Sabit değerler

**(C++ 11)** Tarihçe > üst bilgisi, kodunuzun daha kolay, tür kullanımı ve bakım güvenliği için kullanabileceğiniz aşağıdaki [Kullanıcı tanımlı sabit değerleri](../cpp/user-defined-literals-cpp.md) tanımlar. \< Bu sabit değerler, `literals::chrono_literals` satır içi ad alanında tanımlanmıştır ve std::, kapsam içinde olduğunda kapsamdadır.

|||
|-|-|
|hours işleci "" h (işaretsiz Long Long Val)|Bir integral değeri olarak saat belirtir.|
|süre\<Double, oran\<3600 > > işleci "" h (Long Double Val)|Bir kayan nokta değeri olarak saat belirtir.|
|dakika (operator "" min) (işaretsiz Long Long Val)|Bir integral değeri olarak dakikaları belirtir.|
|süre\<Double, oran\<60 > > (işleç "" min) (Long Double Val)|Bir kayan nokta değeri olarak dakikaları belirtir.|
|Saniyeler işleci "" s (işaretsiz Long Long Val)|Bir integral değeri olarak dakikaları belirtir.|
|süre\<çift > işleci "" s (Long Double Val)|Saniyeyi kayan nokta değeri olarak belirtir.|
|milliseconds işleci "" MS (işaretsiz Long Long Val)|Milisaniyeyi integral değer olarak belirtir.|
|Duration\<Double, Milli > işleci "" MS (Long Double Val)|Bir kayan nokta değeri olarak milisaniye belirtir.|
|mikrosaniye işleci "" US (imzasız uzun değer)|Bir integral değer olarak mikrosaniye belirtir.|
|Duration\<Double, mikro > işleci "" US (Long Double Val)|Bir kayan nokta değeri olarak mikrosaniye belirtir.|
|nanosaniye işleci "" NS (işaretsiz Long Long Val)|Bir integral değer olarak nanosaniye belirtir.|
|Duration\<Double, nano > işleci "" NS (Long Double Val)|Bir kayan nokta değeri olarak nanosaniye belirtir.|

Aşağıdaki örneklerde, zaman hatası değerlerinin nasıl kullanılacağı gösterilmektedir.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
