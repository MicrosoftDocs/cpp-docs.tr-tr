---
title: binomial_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::binomial_distribution
- random/std::binomial_distribution::reset
- random/std::binomial_distribution::p
- random/std::binomial_distribution::t
- random/std::binomial_distribution::param
- random/std::binomial_distribution::min
- random/std::binomial_distribution::max
- random/std::binomial_distribution::operator()
- random/std::binomial_distribution::param_type
- random/std::binomial_distribution::param_type::p
- random/std::binomial_distribution::param_type::t
- random/std::binomial_distribution::param_type::operator==
- random/std::binomial_distribution::param_type::operator!=
helpviewer_keywords:
- std::binomial_distribution [C++]
- std::binomial_distribution [C++], reset
- std::binomial_distribution [C++], p
- std::binomial_distribution [C++], t
- std::binomial_distribution [C++], param
- std::binomial_distribution [C++], min
- std::binomial_distribution [C++], max
- std::binomial_distribution [C++], param_type
- std::binomial_distribution [C++], param_type
ms.assetid: b7c8a26a-da8c-45a5-a3a8-208f7a3609ce
ms.openlocfilehash: dc9bb1c3edf9187b1e5dc1e924298b9dbb02e2ba
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376707"
---
# <a name="binomial_distribution-class"></a>binomial_distribution Sınıfı

Binom dağılımı oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class IntType = int>
class binomial_distribution
   {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructors and reset functions
   explicit binomial_distribution(result_type t = 1, double p = 0.5);
   explicit binomial_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type t() const;
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

Sınıf şablonu, Binomial Distribution ayrık olasılık işlevine göre dağıtılan, kullanıcı tarafından belirtilen integral türüdeğerlerini üreten bir dağılım veya hiçbiri sağlanmamışsa **int** yazın bir dağılım açıklar. Aşağıdaki tablo, tek tek üyelerle ilgili makalelere bağlantılar ala.

||||
|-|-|-|
|[binomial_distribution](#binomial_distribution)|`binomial_distribution::t`|`binomial_distribution::param`|
|`binomial_distribution::operator()`|`binomial_distribution::p`|[param_type](#param_type)|

Özellik üyeleri `t()` `p()` ve sırasıyla şu anda depolanan dağıtım parametre değerleri *t* ve *p* döndürün.

Özellik üyesi, `param()` depolanan `param_type` dağıtım parametre paketini ayarlar veya döndürür.

`min()` Ve `max()` üye işlevler, sırasıyla mümkün olan en küçük sonucu ve mümkün olan en büyük sonucu döndürer.

`reset()` Üye işlev önbelleğe alınan değerleri atar, böylece bir sonraki `operator()` çağrının sonucu çağrıdan önce motordan elde edilen değerlere bağlı olmaz.

Üye `operator()` işlevler, geçerli parametre paketinden veya belirtilen parametre paketinden URNG motoruna dayalı olarak oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için [ \<rastgele>](../standard-library/random.md)bakın.

Binom dağılımı ayrık olasılık fonksiyonu hakkında ayrıntılı bilgi için Wolfram MathWorld makale [Binom Dağılımı'na](https://go.microsoft.com/fwlink/p/?linkid=398469)bakın.

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const int t, const double p, const int& s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::binomial_distribution<> distr(t, p);

    std::cout << std::endl;
    std::cout << "p == " << distr.p() << std::endl;
    std::cout << "t == " << distr.t() << std::endl;

    // generate the distribution as a histogram
    std::map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Histogram for " << s << " samples:" << std::endl;
    for (const auto& elem : histogram) {
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    int    t_dist = 1;
    double p_dist = 0.5;
    int    samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter an integer value for t distribution (where 0 <= t): ";
    std::cin >> t_dist;
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for a sample count: ";
    std::cin >> samples;

    test(t_dist, p_dist, samples);
}
```

İlk çalıştırma:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for t distribution (where 0 <= t): 22
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .25
Enter an integer value for a sample count: 100

p == 0.25
t == 22
Histogram for 100 samples:
    1 :
    2 ::
    3 :::::::::::::
    4 ::::::::::::::
    5 :::::::::::::::::::::::::
    6 ::::::::::::::::::
    7 :::::::::::::
    8 ::::::
    9 ::::::
    11 :
    12 :
```

İkinci tur:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for t distribution (where 0 <= t): 22
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .5
Enter an integer value for a sample count: 100

p == 0.5
t == 22
Histogram for 100 samples:
    6 :
    7 ::
    8 :::::::::
    9 ::::::::::
    10 ::::::::::::::::
    11 :::::::::::::::::::
    12 :::::::::::
    13 :::::::::::::
    14 :::::::::::::::
    15 ::
    16 ::
```

Üçüncü tur:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for t distribution (where 0 <= t): 22
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .75
Enter an integer value for a sample count: 100

p == 0.75
t == 22
Histogram for 100 samples:
    13 ::::
    14 :::::::::::
    15 :::::::::::::::
    16 :::::::::::::::::::::
    17 ::::::::::::::
    18 :::::::::::::::::
    19 :::::::::::
    20 ::::::
    21 :
```

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<rastgele>

**Ad alanı:** std

## <a name="binomial_distributionbinomial_distribution"></a><a name="binomial_distribution"></a>binomial_distribution:binomial_distribution

Dağıtımı kurar.

```cpp
explicit binomial_distribution(result_type t = 1, double p = 0.5);
explicit binomial_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*T*\
Dağıtım `t` parametresi.

*P*\
Dağıtım `p` parametresi.

*parm*\
Dağılımı `param_type` oluşturmak için kullanılan yapı.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:** `0 ≤ t` ve`0.0 ≤ p ≤ 1.0`

İlk oluşturucu, depolanan *p* değeri *p* değerini tutan ve depolanan *t* değeri t değerini tutan *bir*nesne inşa eder.

İkinci oluşturucu, depolanan parametreleri *parm'dan*başharfe çevrilmiş bir nesne inşa eder. Üye işlevi arayarak varolan bir dağıtımın `param()` geçerli parametrelerini alabilir ve ayarlayabilirsiniz.

## <a name="binomial_distributionparam_type"></a><a name="param_type"></a>binomial_distribution::param_type

Dağıtımın tüm parametrelerini depolar.

```cpp
struct param_type {
   typedef binomial_distribution<result_type> distribution_type;
   param_type(result_type t = 1, double p = 0.5);
   result_type t() const;
   double p() const;
   .....
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*T*\
Dağıtım `t` parametresi.

*P*\
Dağıtım `p` parametresi.

*Doğru*\
Bununla `param_type` karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:** `0 ≤ t` ve`0.0 ≤ p ≤ 1.0`

Bu yapı, varolan bir dağılımın depolanan parametrelerini `param()` ayarlamak ve `operator()` depolanan parametrelerin yerine kullanılmak üzere üye işlevine anında dağıtım Sınıfı oluşturucuya geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele>](../standard-library/random.md)
