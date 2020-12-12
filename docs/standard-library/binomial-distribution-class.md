---
description: 'Hakkında daha fazla bilgi edinin: binomial_distribution sınıfı'
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
ms.openlocfilehash: 2cdb55fe312cd19c944ee6279286fe48e515b8a4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325484"
---
# <a name="binomial_distribution-class"></a>binomial_distribution Sınıfı

Binom dağılımı üretir.

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
Tamsayı sonuç türü, varsayılan olarak olur **`int`** . Olası türler için bkz [\<random>](../standard-library/random.md) ..

*URNG*\
Tekdüzen rastgele sayı Oluşturucu altyapısı. Olası türler için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, Kullanıcı tarafından belirtilen integral türünün değerlerini üreten bir dağıtımı veya **`int`** hiçbir değer sağlanmazsa, binom dağılımı ayrık olasılık işlevine göre dağıtılan bir dağılımı açıklar. Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar.

[binomial_distribution](#binomial_distribution)\
[param_type](#param_type)

Özellik üyeleri `t()` ve `p()` Şu anda depolanmış olan dağıtım parametre değerlerini sırasıyla *t* ve *p* döndürür.

Özellik üyesi, `param()` `param_type` depolanan dağıtım parametresi paketini ayarlar veya döndürür.

`min()`Ve `max()` üye işlevleri, sırasıyla olası en küçük sonucu ve en büyük olası sonucu döndürür.

`reset()`Üye işlevi önbelleğe alınmış tüm değerleri atar, böylece sonraki çağrının sonucu, `operator()` çağrıdan önce altyapıdan alınan değerlere bağlı değildir.

`operator()`Üye işlevleri, geçerli parametre paketinden ya da belirtilen parametre paketinden, URNG altyapısına göre oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz [\<random>](../standard-library/random.md) ..

Binom dağılımı ayrık olasılık işlevi hakkında ayrıntılı bilgi için Wolfram MathWorld article [binom dağıtımına](https://go.microsoft.com/fwlink/p/?linkid=398469)bakın.

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

İkinci çalıştırma:

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

Üçüncü çalıştırma:

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

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="binomial_distributionbinomial_distribution"></a><a name="binomial_distribution"></a> binomial_distribution:: binomial_distribution

Dağıtımı oluşturur.

```cpp
explicit binomial_distribution(result_type t = 1, double p = 0.5);
explicit binomial_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*şı*\
`t`Dağıtım parametresi.

*Lama*\
`p`Dağıtım parametresi.

*parametresi*\
`param_type`Dağıtımı oluşturmak için kullanılan yapı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0 ≤ t` ' `0.0 ≤ p ≤ 1.0`

İlk Oluşturucu, saklı *p* değeri *p* değerini tutan ve depolanan *t* değeri *t* değerini tutan bir nesne oluşturur.

İkinci Oluşturucu, saklı parametreleri *parmdan* başlatılan bir nesne oluşturur. Üye işlevini çağırarak mevcut bir dağıtımın geçerli parametrelerini alabilir ve ayarlayabilirsiniz `param()` .

## <a name="binomial_distributionparam_type"></a><a name="param_type"></a> binomial_distribution::p aram_type

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

*şı*\
`t`Dağıtım parametresi.

*Lama*\
`p`Dağıtım parametresi.

*Right*\
`param_type`Karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0 ≤ t` ' `0.0 ≤ p ≤ 1.0`

Bu yapı, örnek oluşturma sırasında dağıtımın sınıf oluşturucusuna, `param()` var olan bir dağıtımın saklı parametrelerini ayarlamak için üye işlevine ve `operator()` depolanan parametrelerin yerine kullanılmak üzere geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
