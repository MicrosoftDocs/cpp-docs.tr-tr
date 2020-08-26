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
ms.openlocfilehash: b74c25e9c26d5767426576633e0999ae3ca44954
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88840654"
---
# <a name="ltchronogt"></a>&lt;Chrono&gt;

\<chrono>Zaman sürelerini ve zaman örneklamalarını temsil eden ve işleyen sınıfları ve işlevleri tanımlamak için standart üst bilgi ekleyin.

Visual Studio 2015 ' den başlayarak uygulaması, `steady_clock` steadiness ve monoton Için C++ standart gereksinimlerini karşılayacak şekilde değiştirilmiştir. `steady_clock` Artık, QueryPerformanceCounter 'yi () temel alır ve `high_resolution_clock` artık için bir typedef `steady_clock` . Sonuç olarak, Microsoft C++ derleyicisinde `steady_clock::time_point` için artık bir typedef vardır `chrono::time_point<steady_clock>` ; ancak, bu kural diğer uygulamalar için durum değildir.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<chrono>

**Ad alanı:** std

## <a name="members"></a>Üyeler

### <a name="classes"></a>Sınıflar

|Ad|Açıklama|
|-|-|
|[Duration sınıfı](../standard-library/duration-class.md)|Bir zaman aralığı tutan bir türü açıklar.|
|[time_point sınıfı](../standard-library/time-point-class.md)|Zaman içinde bir noktayı temsil eden bir türü açıklar.|

### <a name="structs"></a>Yapılar

|Ad|Açıklama|
|-|-|
|[common_type Yapısı](../standard-library/common-type-structure.md)|Ve örneklemeleri için [common_type](../standard-library/common-type-class.md) sınıf şablonu uzmanlıklarını açıklar `duration` `time_point` .|
|[duration_values Yapısı](../standard-library/duration-values-structure.md)|Şablon parametresi için belirli değerler sağlar `duration` `Rep` .|
|[high_resolution_clock yapısı](../standard-library/high-resolution-clock-struct.md)||
|[steady_clock yapısı](../standard-library/steady-clock-struct.md)|Bir saati temsil eder `steady` .|
|[system_clock Yapısı](../standard-library/system-clock-structure.md)|Sistemin gerçek zamanlı saatini temel alan bir *Saat türünü* temsil eder.|
|[treat_as_floating_point Yapısı](../standard-library/treat-as-floating-point-structure.md)|Bir türün kayan nokta türü olarak değerlendirilip değerlendirilmeyeceğini belirtir.|

### <a name="functions"></a>İşlevler

|Ad|Açıklama|
|-|-|
|[duration_cast](../standard-library/chrono-functions.md#duration_cast)|Bir `duration` nesneyi belirtilen bir türe yayınlar.|
|[time_point_cast](../standard-library/chrono-functions.md#time_point_cast)|Bir `time_point` nesneyi belirtilen bir türe yayınlar.|

### <a name="operators"></a>İşleçler

|Ad|Açıklama|
|-|-|
|[işlecinde](../standard-library/chrono-operators.md#operator-)|Ve nesnelerinin çıkarma ve olumsuzlama `duration` işleci `time_point` .|
|[işleç! =](../standard-library/chrono-operators.md#op_neq)|Veya nesneleriyle kullanılan eşitsizlik işleci `duration` `time_point` .|
|[işleç modül](../standard-library/chrono-operators.md#op_modulo)|Nesnelerdeki modül işlemleri için işleç `duration` .|
|[işlecinde](../standard-library/chrono-operators.md#op_star)|Nesneler için çarpma işleci `duration` .|
|[işlecinde](../standard-library/chrono-operators.md#op_div)|Nesneler için bölme işleci `duration` .|
|[işleç +](../standard-library/chrono-operators.md#op_add)|Ekler `duration` ve `time_point` nesneler.|
|[işlecinde&lt;](../standard-library/chrono-operators.md#op_lt)|Bir `duration` veya `time_point` nesnenin başka bir `duration` veya nesnesinden küçük olup olmadığını belirler `time_point` .|
|[işlecinde&lt;=](../standard-library/chrono-operators.md#op_lt_eq)|Bir `duration` ya da `time_point` nesnenin bir veya başka bir nesneden küçük ya da ona eşit olup olmadığını belirler `duration` `time_point` .|
|[işleç = =](../standard-library/chrono-operators.md#op_eq_eq)|İki `duration` nesnenin aynı uzunluğa sahip zaman aralıklarını mi temsil ettiğini yoksa iki `time_point` nesnenin de aynı noktayı temsil edip etmediğini belirler.|
|[işlecinde&gt;](../standard-library/chrono-operators.md#op_gt)|Bir `duration` veya `time_point` nesnenin başka bir `duration` veya nesnesinden büyük olup olmadığını belirler `time_point` .|
|[işlecinde&gt;=](../standard-library/chrono-operators.md#op_gt_eq)|Bir `duration` ya da `time_point` nesnenin başka bir veya nesneden büyük veya ona eşit olup olmadığını belirler `duration` `time_point` .|

### <a name="typedefs-predefined-duration-types"></a>Typedefs (önceden tanımlanmış süre türleri)

Aşağıdaki Typedefs 'ta kullanılan oran türleri hakkında daha fazla bilgi için bkz [\<ratio>](../standard-library/ratio.md) ..

|Ad|Açıklama|
|-|-|
|`typedef duration<long long, nano> nanoseconds;`|Değer 1 nanosaniyelik olan bir tür için eş anlamlı `duration` .|
|`typedef duration<long long, micro> microseconds;`|`duration`1 mikrosaniyelik bir işaret dönemi içeren bir türün eş anlamlısı.|
|`typedef duration<long long, milli> milliseconds;`|`duration`1 milisaniyelik değer süresine sahip bir türün eş anlamlısı.|
|`typedef duration<long long> seconds;`|Değer 1 saniye olan bir tür için eş anlamlı `duration` .|
|`typedef duration<int, ratio<60> > minutes;`|`duration`1 dakikalık bir işaret dönemi içeren bir tür için eş anlamlı.|
|`typedef duration<int, ratio<3600> > hours;`|Değer 1 saat olan bir tür için eş anlamlı `duration` .|

### <a name="literals"></a>Değişmez Değerler

**(C++ 11)** \<chrono> Üst bilgi, kodunuzun daha kolay, tür kullanımı ve bakım güvenliği için kullanabileceğiniz aşağıdaki [Kullanıcı tanımlı sabit değerleri](../cpp/user-defined-literals-cpp.md) tanımlar. Bu sabit değerler, `literals::chrono_literals` satır içi ad alanında tanımlanmıştır ve std::, kapsam içinde olduğunda kapsamdadır.

|Bildirim|Açıklama|
|-|-|
|`hours operator "" h(unsigned long long Val)`|Bir integral değeri olarak saat belirtir.|
|`duration<double, ratio<3600> > operator "" h(long double Val)`|Bir kayan nokta değeri olarak saat belirtir.|
|`minutes (operator "" min)(unsigned long long Val)`|Bir integral değeri olarak dakikaları belirtir.|
|`duration<double, ratio<60> > (operator "" min)( long double Val)`|Bir kayan nokta değeri olarak dakikaları belirtir.|
|`seconds operator "" s(unsigned long long Val)`|Bir integral değeri olarak dakikaları belirtir.|
|`duration<double> operator "" s(long double Val)`|Saniyeyi kayan nokta değeri olarak belirtir.|
|`milliseconds operator "" ms(unsigned long long Val)`|Milisaniyeyi integral değer olarak belirtir.|
|`duration<double, milli> operator "" ms(long double Val)`|Bir kayan nokta değeri olarak milisaniye belirtir.|
|`microseconds operator "" us(unsigned long long Val)`|Bir integral değer olarak mikrosaniye belirtir.|
|`duration<double, micro> operator "" us(long double Val)`|Bir kayan nokta değeri olarak mikrosaniye belirtir.|
|`nanoseconds operator "" ns(unsigned long long Val)`|Bir integral değer olarak nanosaniye belirtir.|
|`duration<double, nano> operator "" ns(long double Val)`|Bir kayan nokta değeri olarak nanosaniye belirtir.|

Aşağıdaki örneklerde, zaman hatası değerlerinin nasıl kullanılacağı gösterilmektedir.

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
