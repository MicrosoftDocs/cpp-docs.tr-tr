---
title: geometric_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::geometric_distribution
- random/std::geometric_distribution::reset
- random/std::geometric_distribution::p
- random/std::geometric_distribution::param
- random/std::geometric_distribution::min
- random/std::geometric_distribution::max
- random/std::geometric_distribution::operator()
- random/std::geometric_distribution::param_type
- random/std::geometric_distribution::param_type::p
- random/std::geometric_distribution::param_type::operator==
- random/std::geometric_distribution::param_type::operator!=
helpviewer_keywords:
- std::geometric_distribution [C++]
- std::geometric_distribution [C++], reset
- std::geometric_distribution [C++], p
- std::geometric_distribution [C++], param
- std::geometric_distribution [C++], min
- std::geometric_distribution [C++], max
- std::geometric_distribution [C++], param_type
- std::geometric_distribution [C++], param_type
ms.assetid: 38f933af-3b49-492e-9d26-b6b272a60013
ms.openlocfilehash: 44b624995ed274212a2699cb457c91dfa4530f03
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370645"
---
# <a name="geometric_distribution-class"></a>geometric_distribution Sınıfı

Geometrik bir dağılım oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class IntType = int>
class geometric_distribution {
public:
    // types
    typedef IntType result_type;
    struct param_type;

    // constructors and reset functions
    explicit geometric_distribution(double p = 0.5);
    explicit geometric_distribution(const param_type& parm);
    void reset();

    // generating functions
    template <class URNG>
    result_type operator()(URNG& gen);
    template <class URNG>
    result_type operator()(URNG& gen, const param_type& parm);

    // property functions
    double p() const;
    param_type param() const;
    void param(const param_type& parm);
    result_type min() const;
    result_type max() const;
};
```

### <a name="parameters"></a>Parametreler

*IntType*\
**İnt**varsayılan olarak, tümsedo sonuç türü. Olası türler için [ \<rasgele>](../standard-library/random.md)bakın.

*ÜRNG*\
Tek tip rastgele sayı üreteç motoru. Olası türler için [ \<rasgele>](../standard-library/random.md)bakın.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, geometrik dağılıma sahip kullanıcı tarafından belirtilen integral türüdeğerlerini üreten bir dağılım açıklar. Aşağıdaki tablo, tek tek üyelerle ilgili makalelere bağlantılar ala.

||||
|-|-|-|
|[geometric_distribution](#geometric_distribution)|`geometric_distribution::p`|`geometric_distribution::param`|
|`geometric_distribution::operator()`||[param_type](#param_type)|

Özellik işlevi `p()` depolanan dağıtım parametresi `p`için değeri döndürür.

Özellik üyesi, `param()` depolanan `param_type` dağıtım parametre paketini ayarlar veya döndürür.

`min()` Ve `max()` üye işlevler, sırasıyla mümkün olan en küçük sonucu ve mümkün olan en büyük sonucu döndürer.

`reset()` Üye işlev önbelleğe alınan değerleri atar, böylece bir sonraki `operator()` çağrının sonucu çağrıdan önce motordan elde edilen değerlere bağlı olmaz.

Üye `operator()` işlevler, geçerli parametre paketinden veya belirtilen parametre paketinden URNG motoruna dayalı olarak oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için [ \<rastgele>](../standard-library/random.md)bakın.

Ki-kare dağılımı hakkında ayrıntılı bilgi için Wolfram MathWorld makalesi [Geometrik Dağılım'a](https://go.microsoft.com/fwlink/p/?linkid=400529)bakın.

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

    std::geometric_distribution<> distr(p);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.p() << std::endl;

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
    double p_dist = 0.5;

    int samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the \'p\' distribution parameter: ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(p_dist, samples);
}
```

İlk test:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'p' distribution parameter: .5
Enter an integer value for the sample count: 100

min() == 0
max() == 2147483647
p() == 0.5000000000
Distribution for 100 samples:
    0 :::::::::::::::::::::::::::::::::::::::::::::::::::::
    1 ::::::::::::::::::::::::::
    2 ::::::::::::
    3 ::::::
    4 ::
    5 :
```

İkinci test:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'p' distribution parameter: .1
Enter an integer value for the sample count: 100

min() == 0
max() == 2147483647
p() == 0.1000000000
Distribution for 100 samples:
    0 :::::::::
    1 :::::::::::
    2 ::::::::::
    3 :::::::
    4 :::::
    5 ::::::::
    6 :::
    7 ::::::
    8 :::::::
    9 :::::
   10 :::
   11 :::
   12 ::
   13 :
   14 :::
   15 ::
   16 :::
   17 :::
   20 :::::
   21 :
   29 :
   32 :
   35 :
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<rastgele>

**Ad alanı:** std

## <a name="geometric_distributiongeometric_distribution"></a><a name="geometric_distribution"></a>geometric_distribution:geometric_distribution

Dağıtımı kurar.

```cpp
explicit geometric_distribution(double p = 0.5);
explicit geometric_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*P*\
Dağıtım `p` parametresi.

*parm*\
Dağılımı oluşturmak için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:**`0.0 < p && p < 1.0`

İlk oluşturucu, depolanan `p` değeri *p*değerini tutan bir nesne inşa eder.

İkinci oluşturucu, depolanan parametreleri *parm'dan*başharfe çevrilmiş bir nesne inşa eder. Üye işlevi arayarak varolan bir dağıtımın `param()` geçerli parametrelerini alabilir ve ayarlayabilirsiniz.

## <a name="geometric_distributionparam_type"></a><a name="param_type"></a>geometric_distribution::param_type

Dağıtım parametrelerini depolar.

```cpp
struct param_type {
   typedef geometric_distribution<result_type> distribution_type;
   param_type(double p = 0.5);
   double p() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*P*\
Dağıtım `p` parametresi.

*Doğru*\
Bunu `param_type` karşılaştırmak için örnek.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:**`0.0 < p && p < 1.0`

Bu yapı, varolan bir dağılımın depolanan parametrelerini `param()` ayarlamak ve `operator()` depolanan parametrelerin yerine kullanılmak üzere üye işlevine anında dağıtım Sınıfı oluşturucuya geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele>](../standard-library/random.md)
