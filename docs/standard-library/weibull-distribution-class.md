---
title: weibull_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::weibull_distribution
- random/std::weibull_distribution::reset
- random/std::weibull_distribution::a
- random/std::weibull_distribution::b
- random/std::weibull_distribution::param
- random/std::weibull_distribution::min
- random/std::weibull_distribution::max
- random/std::weibull_distribution::operator()
- random/std::weibull_distribution::param_type
- random/std::weibull_distribution::param_type::a
- random/std::weibull_distribution::param_type::b
- random/std::weibull_distribution::param_type::operator==
- random/std::weibull_distribution::param_type::operator!=
helpviewer_keywords:
- std::weibull_distribution [C++]
- std::weibull_distribution [C++], reset
- std::weibull_distribution [C++], a
- std::weibull_distribution [C++], b
- std::weibull_distribution [C++], param
- std::weibull_distribution [C++], min
- std::weibull_distribution [C++], max
- std::weibull_distribution [C++], param_type
- std::weibull_distribution [C++], param_type
ms.assetid: f20b49d3-1b9a-41af-8db4-baf800eaa02b
ms.openlocfilehash: 01640cd700f54facba06f65f63e172abc668a5be
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366373"
---
# <a name="weibull_distribution-class"></a>weibull_distribution Sınıfı

Weibull dağılımı nı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
class weibull_distribution
   {
   public:
    // types
   typedef RealType result_type;
   struct param_type;

    // constructor and reset functions
   explicit weibull_distribution(result_type a = 1.0, result_type b = 1.0);
   explicit weibull_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
      result_type operator()(URNG& gen);
   template <class URNG>
      result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type a() const;
   result_type b() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametreler

*RealType*\
Kayan nokta sonuç türü, varsayılan **olarak iki katına çıkar.** Olası türler için [ \<rasgele>](../standard-library/random.md)bakın.

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, Weibull Distribution'a göre dağıtılan kullanıcı tarafından belirtilen kayan nokta türü değerlerini üreten veya hiçbiri sağlanmamışsa **çift** yazın bir dağılım açıklar. Aşağıdaki tablo, tek tek üyelerle ilgili makalelere bağlantılar ala.

||||
|-|-|-|
|[weibull_distribution](#weibull_distribution)|`weibull_distribution::a`|`weibull_distribution::param`|
|`weibull_distribution::operator()`|`weibull_distribution::b`|[param_type](#param_type)|

Özellik fonksiyonları `a()` `b()` ve depolanan dağıtım parametreleri *a* ve *b*için kendi değerlerini döndürün.

Özellik üyesi, `param()` depolanan `param_type` dağıtım parametre paketini ayarlar veya döndürür.

`min()` Ve `max()` üye işlevler, sırasıyla mümkün olan en küçük sonucu ve mümkün olan en büyük sonucu döndürer.

`reset()` Üye işlev önbelleğe alınan değerleri atar, böylece bir sonraki `operator()` çağrının sonucu çağrıdan önce motordan elde edilen değerlere bağlı olmaz.

Üye `operator()` işlevler, geçerli parametre paketinden veya belirtilen parametre paketinden URNG motoruna dayalı olarak oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için [ \<rastgele>](../standard-library/random.md)bakın.

Weibull dağılımı hakkında ayrıntılı bilgi için Wolfram MathWorld makalesi [Weibull Dağıtım'a](https://mathworld.wolfram.com/WeibullDistribution.html)bakın.

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double a, const double b, const int s) {

    // uncomment to use a non-deterministic generator
    //    std::random_device gen;
    std::mt19937 gen(1701);

    std::weibull_distribution<> distr(a, b);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;

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
    double a_dist = 0.0;
    double b_dist = 1;

    int samples = 10;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the 'a' distribution parameter (must be greater than zero): ";
    std::cin >> a_dist;
    std::cout << "Enter a floating point value for the 'b' distribution parameter (must be greater than zero): ";
    std::cin >> b_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(a_dist, b_dist, samples);
}
```

## <a name="output"></a>Çıktı

İlk çalıştırma:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'a' distribution parameter (must be greater than zero): 1
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == 0
max() == 1.79769e+308
a() == 1.0000000000
b() == 1.0000000000
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

İkinci tur:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'a' distribution parameter (must be greater than zero): .5
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 5.5
Enter an integer value for the sample count: 10

min() == 0
max() == 1.79769e+308
a() == 0.5000000000
b() == 5.5000000000
Distribution for 10 samples:
    1: 0.0482759823
    2: 0.0826617486
    3: 2.2835941207
    4: 2.3604817485
    5: 2.9417663742
    6: 2.9418471657
    7: 3.1685268104
    8: 11.5109922290
    9: 14.8543594043
    10: 24.7220241239
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<rastgele>

**Ad alanı:** std

## <a name="weibull_distributionweibull_distribution"></a><a name="weibull_distribution"></a>weibull_distribution:weibull_distribution

```cpp
explicit weibull_distribution(result_type a = 1.0, result_type b = 1.0);
explicit weibull_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*A*\
Dağıtım `a` parametresi.

*B*\
Dağıtım `b` parametresi.

*parm*\
Dağılımı `param_type` oluşturmak için kullanılan yapı.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:** `0.0 < a` ve`0.0 < b`

İlk oluşturucu, `a` depolanan değeri *a* değerini tutan ve depolanan `b` değeri *b*değerini tutan bir nesne yi inşa eder.

İkinci oluşturucu, depolanan parametreleri *parm'dan*başharfe çevrilmiş bir nesne inşa eder. Üye işlevi arayarak varolan bir dağıtımın `param()` geçerli parametrelerini alabilir ve ayarlayabilirsiniz.

## <a name="weibull_distributionparam_type"></a><a name="param_type"></a>weibull_distribution::param_type

Dağıtım parametrelerini depolar.

```cpp
struct param_type {
   typedef weibull_distribution<result_type> distribution_type;
   param_type(result_type a = 1.0, result_type b = 1.0);
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*A*\
Dağıtım `a` parametresi.

*B*\
Dağıtım `b` parametresi.

*Doğru*\
Bununla `param_type` karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:** `0.0 < a` ve`0.0 < b`

Bu yapı, varolan bir dağılımın depolanan parametrelerini `param()` ayarlamak ve `operator()` depolanan parametrelerin yerine kullanılmak üzere üye işlevine anında dağıtım Sınıfı oluşturucuya geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele>](../standard-library/random.md)
