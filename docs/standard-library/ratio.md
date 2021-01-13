---
description: 'Daha fazla bilgi edinin: &lt; oran&gt;'
title: '&lt;sabit&gt;'
ms.date: 11/04/2016
f1_keywords:
- <ratio>
- ratio/std::mega
- ratio/std::peta
- ratio/std::ratio_greater
- ratio/std::micro
- ratio/std::ratio_add
- ratio/std::ratio_not_equal
- ratio/std::hecto
- ratio/std::nano
- ratio/std::ratio_less_equal
- ratio/std::ratio_less
- ratio/std::centi
- ratio/std::ratio_greater_equal
- ratio/std::ratio_subtract
- ratio/std::atto
- ratio/std::tera
- ratio/std::milli
- ratio/std::ratio_multiply
- ratio/std::kilo
- ratio/std::ratio_divide
- ratio/std::giga
- ratio/std::pico
- ratio/std::femto
- ratio/std::ratio_equal
- ratio/std::ratio
- ratio/std::exa
- ratio/std::deci
- ratio/std::deca
ms.assetid: 8543e912-2d84-45ea-b3c0-bd7bfacee405
ms.openlocfilehash: a32a8252347de1e6d7bfd5ffd29927c779ce8489
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126565"
---
# <a name="ltratiogt"></a>&lt;sabit&gt;

\<ratio>Derleme zamanında Rational numaralarını depolamak ve işlemek için kullanılan sabitleri ve şablonları tanımlamak için standart üstbilgiyi ekleyin.

## <a name="syntax"></a>Syntax

```cpp
#include <ratio>
```

### <a name="ratio-template"></a>oran şablonu

```cpp
template<std::intmax_t Numerator, std::intmax_t Denominator = 1>
struct ratio // holds the ratio of Numerator to Denominator
{
   static constexpr std::intmax_t num;
   static constexpr std::intmax_t den;
   typedef ratio<num, den> type;
}
```

Şablon `ratio` statik sabitleri `num` ve `den` Bu `num`  /  `den` = = pay/paydayı tanımlar ve `num` `den` ortak faktörlere sahip değildir. `num` / `den` , sınıf şablonuyla temsil edilen değerdir. Bu nedenle, `type` örnek oluşturmayı gösterir `ratio<num, den>` .

### <a name="specializations"></a>Uzmanlıklar

\<ratio> Ayrıca, `ratio` aşağıdaki biçime sahip olan öğesinin uzmanlıklarını tanımlar.

`template <class R1, class R2> struct ratio_specialization`

Her özelleşmenin de özelleştirilmiş olması gereken iki şablon parametresi alır `ratio` . Değeri, `type` ilişkili bir mantıksal işlem tarafından belirlenir.

|Ad|`type` Deeri|
|----------|------------------|
|`ratio_add`|`R1 + R2`|
|`ratio_divide`|`R1 / R2`|
|`ratio_equal`|`R1 == R2`|
|`ratio_greater`|`R1 > R2`|
|`ratio_greater_equal`|`R1 >= R2`|
|`ratio_less`|`R1 < R2`|
|`ratio_less_equal`|`R1 <= R2`|
|`ratio_multiply`|`R1 * R2`|
|`ratio_not_equal`|`!(R1 == R2)`|
|`ratio_subtract`|`R1 - R2`|

### <a name="typedefs"></a>tür tanımları

Daha kolay bir şekilde, üst bilgi standart sı ön ekleri için oranları tanımlar:

```cpp
typedef ratio<1, 1000000000000000000> atto;
typedef ratio<1, 1000000000000000> femto;
typedef ratio<1, 1000000000000> pico;
typedef ratio<1, 1000000000> nano;
typedef ratio<1, 1000000> micro;
typedef ratio<1, 1000> milli;
typedef ratio<1, 100> centi;
typedef ratio<1, 10> deci;
typedef ratio<10, 1> deca;
typedef ratio<100, 1> hecto;
typedef ratio<1000, 1> kilo;
typedef ratio<1000000, 1> mega;
typedef ratio<1000000000, 1> giga;
typedef ratio<1000000000000, 1> tera;
typedef ratio<1000000000000000, 1> peta;
typedef ratio<1000000000000000000, 1> exa;
```

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)
