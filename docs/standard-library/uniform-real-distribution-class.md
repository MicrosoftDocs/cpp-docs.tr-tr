---
title: uniform_real_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::uniform_real_distribution
- random/std::uniform_real_distribution::reset
- random/std::uniform_real_distribution::a
- random/std::uniform_real_distribution::b
- random/std::uniform_real_distribution::param
- random/std::uniform_real_distribution::min
- random/std::uniform_real_distribution::max
- random/std::uniform_real_distribution::operator()
- random/std::uniform_real_distribution::param_type
- random/std::uniform_real_distribution::param_type::a
- random/std::uniform_real_distribution::param_type::b
- random/std::uniform_real_distribution::param_type::operator==
- random/std::uniform_real_distribution::param_type::operator!=
helpviewer_keywords:
- std::uniform_real_distribution [C++]
- std::uniform_real_distribution [C++], reset
- std::uniform_real_distribution [C++], a
- std::uniform_real_distribution [C++], b
- std::uniform_real_distribution [C++], param
- std::uniform_real_distribution [C++], min
- std::uniform_real_distribution [C++], max
- std::uniform_real_distribution [C++], param_type
- std::uniform_real_distribution [C++], param_type
ms.assetid: 5cf906fd-0319-4984-b21b-98425cd7532d
ms.openlocfilehash: 4f293f73eb1fa8a38bf06692ef5b7938faeab0d0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367274"
---
# <a name="uniform_real_distribution-class"></a>uniform_real_distribution Sınıfı

Kapsayıcı-münhasır bir çıkış aralığı içinde bir üniforma (her değer eşit olasıdır) kayan nokta dağılımı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class RealType = double>
   class uniform_real_distribution {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructors and reset functions
   explicit uniform_real_distribution(
      result_type a = 0.0, result_type b = 1.0);
   explicit uniform_real_distribution(const param_type& parm);
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

Sınıf şablonu, her değerin eşit derecede olası olması için, kullanıcı tarafından belirtilen integral kayan nokta türü değerlerini bir dağılımla üreten kapsayıcı münhasır bir dağılım açıklar. Aşağıdaki tablo, tek tek üyelerle ilgili makalelere bağlantılar ala.

||||
|-|-|-|
|[uniform_real_distribution](#uniform_real_distribution)|`uniform_real_distribution::a`|`uniform_real_distribution::param`|
|`uniform_real_distribution::operator()`|`uniform_real_distribution::b`|[param_type](#param_type)|

Mülk üyesi, `a()` şu anda depolanan minimum `b()` dağıtım sınırını döndürürken, şu anda depolanan maksimum sınırı döndürür. Bu dağıtım sınıfı için, bu minimum ve en büyük değerler `min()` ortak `max()` özellik işlevleri tarafından döndürülen ve [ \<rasgele>](../standard-library/random.md) konuda açıklananlarla aynıdır.

Özellik üyesi, `param()` depolanan `param_type` dağıtım parametre paketini ayarlar veya döndürür.

`min()` Ve `max()` üye işlevler, sırasıyla mümkün olan en küçük sonucu ve mümkün olan en büyük sonucu döndürer.

`reset()` Üye işlev önbelleğe alınan değerleri atar, böylece bir sonraki `operator()` çağrının sonucu çağrıdan önce motordan elde edilen değerlere bağlı olmaz.

Üye `operator()` işlevler, geçerli parametre paketinden veya belirtilen parametre paketinden URNG motoruna dayalı olarak oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için [ \<rastgele>](../standard-library/random.md)bakın.

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double a, const double b, const int s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::uniform_real_distribution<> distr(a,b);

    std::cout << "lower bound == " << distr.a() << std::endl;
    std::cout << "upper bound == " << distr.b() << std::endl;

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
            << std::setprecision(10) << elem.first << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double a_dist = 1.0;
    double b_dist = 1.5;

    int samples = 10;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the lower bound of the distribution: ";
    std::cin >> a_dist;
    std::cout << "Enter a floating point value for the upper bound of the distribution: ";
    std::cin >> b_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(a_dist, b_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the lower bound of the distribution: 0
Enter a floating point value for the upper bound of the distribution: 1
Enter an integer value for the sample count: 10
lower bound == 0
upper bound == 1
Distribution for 10 samples:
          1: 0.0288609485
          2: 0.2007994386
          3: 0.3027480117
          4: 0.4124758695
          5: 0.4413777133
          6: 0.4846447405
          7: 0.6225745916
          8: 0.6880935217
          9: 0.7541936723
         10: 0.8795716566
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<rastgele>

**Ad alanı:** std

## <a name="uniform_real_distributionuniform_real_distribution"></a><a name="uniform_real_distribution"></a>uniform_real_distribution:uniform_real_distribution

Dağıtımı kurar.

```cpp
explicit uniform_real_distribution(result_type a = 0.0, result_type b = 1.0);
explicit uniform_real_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*A*\
Rasgele değerler için alt sınır, kapsayıcı.

*B*\
Rasgele değerler için üst sınır, özel.

*parm*\
Dağılımı `param_type` oluşturmak için kullanılan yapı.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:**`a < b`

İlk oluşturucu, depolanan değeri *a* değerini tutan ve depolanan *b* değeri *b*değerini tutan *bir* nesne yi inşa eder.

İkinci oluşturucu, depolanan parametreleri *parm'dan*başharfe çevrilmiş bir nesne inşa eder. Üye işlevi arayarak varolan bir dağıtımın `param()` geçerli parametrelerini alabilir ve ayarlayabilirsiniz.

## <a name="uniform_real_distributionparam_type"></a><a name="param_type"></a>uniform_real_distribution::param_type

Dağıtımın tüm parametrelerini depolar.

```cpp
struct param_type {
   typedef uniform_real_distribution<result_type> distribution_type;
   param_type(result_type a = 0.0, result_type b = 1.0);
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*A*\
Rasgele değerler için alt sınır, kapsayıcı.

*B*\
Rasgele değerler için üst sınır, özel.

*Doğru*\
Bununla `param_type` karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:**`a < b`

Bu yapı, varolan bir dağılımın depolanan parametrelerini `param()` ayarlamak ve `operator()` depolanan parametrelerin yerine kullanılmak üzere üye işlevine anında dağıtım Sınıfı oluşturucuya geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele>](../standard-library/random.md)
