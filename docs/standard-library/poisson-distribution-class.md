---
title: poisson_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::poisson_distribution
- random/std::poisson_distribution::reset
- random/std::poisson_distribution::mean
- random/std::poisson_distribution::param
- random/std::poisson_distribution::min
- random/std::poisson_distribution::max
- random/std::poisson_distribution::operator()
- random/std::poisson_distribution::param_type
- random/std::poisson_distribution::param_type::mean
- random/std::poisson_distribution::param_type::operator==
- random/std::poisson_distribution::param_type::operator!=
helpviewer_keywords:
- std::poisson_distribution [C++]
- std::poisson_distribution [C++], reset
- std::poisson_distribution [C++], mean
- std::poisson_distribution [C++], param
- std::poisson_distribution [C++], min
- std::poisson_distribution [C++], max
- std::poisson_distribution [C++], param_type
- std::poisson_distribution [C++], param_type
ms.assetid: 09614281-349a-45f7-8e95-c0196be0a937
ms.openlocfilehash: 4c8e35c097513176551db16471ed3a8c4ca1e824
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51521486"
---
# <a name="poissondistribution-class"></a>poisson_distribution Sınıfı

Bir Poisson dağılımı üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class IntType = int>
class poisson_distribution
   {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructors and reset functions
   explicit poisson_distribution(double mean = 1.0);
   explicit poisson_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   double mean() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametreler

*İnt'i*<br/>
Tamsayı sonuç türü varsayılan olarak **int**. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir kullanıcı tarafından belirtilen integral türünden bir Poisson dağılımı değerleri üreten bir dağıtım açıklar. Aşağıdaki tablo ilgili makalelerin bağlantısı için tek tek üyeleri.

||||
|-|-|-|
|[poisson_distribution](#poisson_distribution)|`poisson_distribution::mean`|`poisson_distribution::param`|
|`poisson_distribution::operator()`||[param_type](#param_type)|

Özellik işlevi `mean()` saklı dağıtım parametresinin değeri döndürür *ortalama*.

Özellik üyesi `param()` ayarlar veya döndürür `param_type` saklı dağıtım parametre paketi.

`min()` Ve `max()` üye işlevleri olası en küçük sonuç ve olası en büyük sonuç sırasıyla döndürür.

`reset()` Üye işlevi herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerleri, bağlı değildir.

`operator()` Üye işlevler URNG motoru, geçerli parametre paketi veya belirtilen parametre paketi göre sonraki oluşturulan değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

Poisson dağılımı hakkında ayrıntılı bilgi için Wolfram MathWorld bkz [Poisson dağılımı](http://go.microsoft.com/fwlink/p/?linkid=401112).

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double p, const int s) {

    // uncomment to use a non-deterministic generator
    //    std::random_device gen;
    std::mt19937 gen(1701);

    std::poisson_distribution<> distr(p);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.mean() << std::endl;

    // generate the distribution as a histogram
    std::map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    for (const auto& elem : histogram) {
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double p_dist = 1.0;

    int samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(p_dist, samples);
}
```

İlk test:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 1.0000000000
Distribution for 100 samples:
    0 ::::::::::::::::::::::::::::::
    1 ::::::::::::::::::::::::::::::::::::::
    2 :::::::::::::::::::::::
    3 ::::::::
    5 :
```

İkinci test:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 10
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 10.0000000000
Distribution for 100 samples:
    3 :
    4 ::
    5 ::
    6 ::::::::
    7 ::::
    8 ::::::::
    9 ::::::::::::::
   10 ::::::::::::
   11 ::::::::::::::::
   12 :::::::::::::::
   13 ::::::::
   14 ::::::
   15 :
   16 ::
   17 :
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="poisson_distribution"></a>  poisson_distribution::poisson_distribution

Dağıtımı oluşturur.

```cpp
explicit poisson_distribution(RealType mean = 1.0);
explicit binomial_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*Ortalama*<br/>
`mean` Dağıtım parametresi.

*parametre*<br/>
Dağıtımın oluşturulması için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < mean`

İlk Oluşturucu bir nesne oluşturur, saklı `mean` değerine değeri *ortalama*.

İkinci oluşturucu depolanmış parametreleri dan başlatılan bir nesne oluşturur *parametresi*. Alabilir ve çağırarak geçerli var olan bir dağıtım parametrelerini ayarlayın `param()` üye işlevi.

## <a name="param_type"></a>  poisson_distribution::param_type

Dağıtım parametrelerini depolar.

```cpp
struct param_type {
   typedef poisson_distribution<IntType> distribution_type;
   param_type(double mean = 1.0);
   double mean() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

Oluşturucu parametresi için bkz. [poisson_distribution](#poisson_distribution).

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < mean`

Bu yapı dağıtım'ın sınıf oluşturucusu oluşturmada, en çok geçirilebilir `param()` depolanan parametre var olan bir dağıtım için ve ayarlamak için üye işlevi `operator()` depolanan parametrelerin yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
