---
title: exponential_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::exponential_distribution
- random/std::exponential_distribution::reset
- random/std::exponential_distribution::lambda
- random/std::exponential_distribution::param
- random/std::exponential_distribution::min
- random/std::exponential_distribution::max
- random/std::exponential_distribution::operator()
- random/std::exponential_distribution::param_type
- random/std::exponential_distribution::param_type::lambda
- random/std::exponential_distribution::param_type::operator==
- random/std::exponential_distribution::param_type::operator!=
helpviewer_keywords:
- std::exponential_distribution [C++]
- std::exponential_distribution [C++], reset
- std::exponential_distribution [C++], lambda
- std::exponential_distribution [C++], param
- std::exponential_distribution [C++], min
- std::exponential_distribution [C++], max
- std::exponential_distribution [C++], param_type
- std::exponential_distribution [C++], param_type
ms.assetid: d54f3126-a09b-45f9-a30b-0d94d03bcdc9
ms.openlocfilehash: b419869785e9b6c2086ec6614363af3a3e12cb50
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51518157"
---
# <a name="exponentialdistribution-class"></a>exponential_distribution Sınıfı

Bir üstel dağılım üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class RealType = double>
class exponential_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructors and reset functions
   explicit exponential_distribution(result_type lambda = 1.0);
   explicit exponential_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type lambda() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametreler

*RealType*<br/>
Kayan noktalı bir sonuç türü varsayılan olarak **çift**. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*URNG*<br/>
Rasgele sayı üreteci altyapısı. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı tanımlar kullanıcı tanımlı bir integral değerini üreten bir dağıtım türü veya tür **çift** sağlanmazsa, üstel dağılımı göre dağıtılmış. Aşağıdaki tablo ilgili makalelerin bağlantısı için tek tek üyeleri.

||||
|-|-|-|
|[exponential_distribution](#exponential_distribution)|`exponential_distribution::lambda`|`exponential_distribution::param`|
|`exponential_distribution::operator()`||[param_type](#param_type)|

Özellik üye işlevi `lambda()` saklı dağıtım parametresinin değeri döndürür `lambda`.

Özellik üye işlevi `param()` ayarlar veya döndürür `param_type` saklı dağıtım parametre paketi.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

Üstel dağılımı hakkında ayrıntılı bilgi için Wolfram MathWorld bkz [üstel dağılımı](http://go.microsoft.com/fwlink/p/?linkid=401098).

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double l, const int s) {

    // uncomment to use a non-deterministic generator
    //    std::random_device gen;
    std::mt19937 gen(1701);

    std::exponential_distribution<> distr(l);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "lambda() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.lambda() << std::endl;

    // generate the distribution as a histogram
    std::map<double, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    int counter = 0;
    for (const auto& elem : histogram) {
        std::cout << std::fixed << std::setw(11) << ++counter << ": "
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double l_dist = 0.5;
    int samples = 10;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): ";
    std::cin >> l_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(l_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'lambda' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == 0
max() == 1.79769e+308
lambda() == 1.0000000000
Distribution for 10 samples:
    1: 0.0936880533
    2: 0.1225944894
    3: 0.6443593183
    4: 0.6551171649
    5: 0.7313457551
    6: 0.7313557977
    7: 0.7590097389
    8: 1.4466885214
    9: 1.6434088411
    10: 2.1201210996
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="exponential_distribution"></a>  exponential_distribution::exponential_distribution

Dağıtımı oluşturur.

```cpp
explicit exponential_distribution(result_type lambda = 1.0);
explicit exponential_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*lambda*<br/>
`lambda` Dağıtım parametresi.

*parametre*<br/>
Dağıtımın oluşturulması için kullanılan parametre paketi.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < lambda`

İlk Oluşturucu bir nesne oluşturur, saklı `lambda` değerine değeri *lambda*.

İkinci oluşturucu depolanmış parametreleri dan başlatılan bir nesne oluşturur *parametresi*. Alabilir ve çağırarak geçerli var olan bir dağıtım parametrelerini ayarlayın `param()` üye işlevi.

## <a name="param_type"></a>  exponential_distribution::param_type

Dağıtım parametrelerini depolar.

```cpp
struct param_type {
   typedef exponential_distribution<result_type> distribution_type;
   param_type(result_type lambda = 1.0);
   result_type lambda() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*lambda*<br/>
`lambda` Dağıtım parametresi.

*sağ*<br/>
`param_type` İçin karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < lambda`

Bu yapı dağıtım'ın sınıf oluşturucusu oluşturmada, en çok geçirilebilir `param()` depolanan parametre var olan bir dağıtım için ve ayarlamak için üye işlevi `operator()` depolanan parametrelerin yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
