---
title: '&lt;chrono &gt;'
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
ms.openlocfilehash: e27ff146c75da6e90e6336106beba714dbe7c8a8
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689872"
---
# <a name="ltchronogt"></a>&lt;chrono &gt;

Süreleri ve zaman sürelerini temsil eden ve işleyen sınıfları ve işlevleri tanımlamak için standart üst bilgi \<chrono > ekleyin.

Visual Studio 2015 ' den başlayarak `steady_clock` uygulaması, steadiness ve monoton için C++ standart gereksinimleri karşılayacak şekilde değiştirilmiştir. `steady_clock` artık QueryPerformanceCounter () ' i temel alır ve `high_resolution_clock` artık `steady_clock` için bir typedef. Sonuç olarak, Microsoft C++ derleyicisi `steady_clock::time_point` artık `chrono::time_point<steady_clock>` için bir typedef 'dir; Ancak, bu kural diğer uygulamalar için durum değildir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<chrono >

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
|[common_type Yapısı](../standard-library/common-type-structure.md)|@No__t_1 ve `time_point` örneklemeleri için sınıf şablonu [common_type](../standard-library/common-type-class.md) 'in uzmanlık özelliklerini açıklar.|
|[duration_values Yapısı](../standard-library/duration-values-structure.md)|@No__t_0 şablon parametresi için belirli değerler sağlar `Rep`.|
|[high_resolution_clock yapısı](../standard-library/high-resolution-clock-struct.md)||
|[steady_clock yapısı](../standard-library/steady-clock-struct.md)|Bir `steady` saati temsil eder.|
|[system_clock Yapısı](../standard-library/system-clock-structure.md)|Sistemin gerçek zamanlı saatini temel alan bir *Saat türünü* temsil eder.|
|[treat_as_floating_point Yapısı](../standard-library/treat-as-floating-point-structure.md)|Bir türün kayan nokta türü olarak değerlendirilip değerlendirilmeyeceğini belirtir.|

### <a name="functions"></a>İşlevler

|||
|-|-|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|@No__t_0 nesnesini belirtilen bir türe yayınlar.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|@No__t_0 nesnesini belirtilen bir türe yayınlar.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[işlecinde](../standard-library/chrono-operators.md#operator-)|@No__t_0 ve `time_point` nesnelerinin çıkarma veya olumsuzlama işleci.|
|[operator!=](../standard-library/chrono-operators.md#op_neq)|@No__t_0 veya `time_point` nesneleriyle kullanılan eşitsizlik işleci.|
|[işleç modül](../standard-library/chrono-operators.md#op_modulo)|@No__t_0 nesnelerinde modül işlemleri için işleç.|
|[işlecinde](../standard-library/chrono-operators.md#op_star)|@No__t_0 nesneler için çarpma işleci.|
|[işlecinde](../standard-library/chrono-operators.md#op_div)|@No__t_0 nesneler için bölme işleci.|
|[işleç +](../standard-library/chrono-operators.md#op_add)|@No__t_0 ve `time_point` nesneleri ekler.|
|[işleç &lt;](../standard-library/chrono-operators.md#op_lt)|Bir `duration` veya `time_point` nesnesinin başka bir `duration` veya `time_point` nesnesinden küçük olup olmadığını belirler.|
|[işleç &lt; =](../standard-library/chrono-operators.md#op_lt_eq)|Bir `duration` veya `time_point` nesnesinin, başka bir `duration` veya `time_point` nesnesinden küçük veya ona eşit olup olmadığını belirler.|
|[işleç = =](../standard-library/chrono-operators.md#op_eq_eq)|İki `duration` nesnenin aynı uzunluğa sahip zaman aralıklarını mi temsil ettiğini yoksa iki `time_point` nesnesinin de aynı noktayı temsil edip etmediğini belirler.|
|[işleç &gt;](../standard-library/chrono-operators.md#op_gt)|Bir `duration` veya `time_point` nesnesinin, başka bir `duration` veya `time_point` nesnesinden büyük olup olmadığını belirler.|
|[işleç &gt; =](../standard-library/chrono-operators.md#op_gt_eq)|Bir `duration` veya `time_point` nesnesinin, başka bir `duration` veya `time_point` nesnesinden büyük veya ona eşit olup olmadığını belirler.|

### <a name="typedefs-predefined-duration-types"></a>Typedefs (önceden tanımlanmış süre türleri)

Aşağıdaki Typedefs 'ta kullanılan oran türleri hakkında daha fazla bilgi için bkz. [\<ratio >](../standard-library/ratio.md).

|||
|-|-|
|`typedef duration<long long, nano> nanoseconds;`|Değer 1 nanosaniyelik olan `duration` türü için eş anlamlı.|
|`typedef duration<long long, micro> microseconds;`|1 mikro saniye değer çizgisi olan bir `duration` türü için eş anlamlı.|
|`typedef duration<long long, milli> milliseconds;`|1 milisaniyelik değer süresine sahip `duration` bir türün eş anlamlısı.|
|`typedef duration<long long> seconds;`|1 saniye değer çizgisi olan `duration` türü için eş anlamlı.|
|`typedef duration<int, ratio<60> > minutes;`|1 dakikalık bir değer dönemi içeren `duration` türü için eş anlamlı.|
|`typedef duration<int, ratio<3600> > hours;`|1 saat işaret eden bir `duration` türü için eş anlamlı.|

### <a name="literals"></a>Sabit değerler

**(C++ 11)** @No__t_1chrono > üst bilgisi, kodunuzun daha kolay, tür güvenliği ve bakım için kullanabileceğiniz aşağıdaki [Kullanıcı tanımlı sabit değerleri](../cpp/user-defined-literals-cpp.md) tanımlar. Bu sabit değerler `literals::chrono_literals` satır içi ad alanında tanımlanmıştır ve std::, kapsam içinde olduğunda kapsam içinde bulunur.

|||
|-|-|
|hours işleci "" h (işaretsiz Long Long Val)|Bir integral değeri olarak saat belirtir.|
|süre \<double, oran \<3600 > > işleci "" h (Long Double Val)|Bir kayan nokta değeri olarak saat belirtir.|
|dakika (operator "" min) (işaretsiz Long Long Val)|Bir integral değeri olarak dakikaları belirtir.|
|süre \<double, oran \<60 > > (operator "" min) (Long Double Val)|Bir kayan nokta değeri olarak dakikaları belirtir.|
|Saniyeler işleci "" s (işaretsiz Long Long Val)|Bir integral değeri olarak dakikaları belirtir.|
|süre \<double > işleci "" s (Long Double Val)|Saniyeyi kayan nokta değeri olarak belirtir.|
|milliseconds işleci "" MS (işaretsiz Long Long Val)|Milisaniyeyi integral değer olarak belirtir.|
|Duration \<double, Milli > işleci "" MS (Long Double Val)|Bir kayan nokta değeri olarak milisaniye belirtir.|
|mikrosaniye işleci "" US (imzasız uzun değer)|Bir integral değer olarak mikrosaniye belirtir.|
|Duration \<double, mikro > işleci "" US (Long Double Val)|Bir kayan nokta değeri olarak mikrosaniye belirtir.|
|nanosaniye işleci "" NS (işaretsiz Long Long Val)|Bir integral değer olarak nanosaniye belirtir.|
|Duration \<double, nano > işleci "" NS (Long Double Val)|Bir kayan nokta değeri olarak nanosaniye belirtir.|

Aşağıdaki örneklerde, zaman hatası değerlerinin nasıl kullanılacağı gösterilmektedir.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
