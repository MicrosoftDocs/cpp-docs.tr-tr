---
title: negative_binomial_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::negative_binomial_distribution
- random/std::negative_binomial_distribution::reset
- random/std::negative_binomial_distribution::k
- random/std::negative_binomial_distribution::p
- random/std::negative_binomial_distribution::param
- random/std::negative_binomial_distribution::min
- random/std::negative_binomial_distribution::max
- random/std::negative_binomial_distribution::operator()
- random/std::negative_binomial_distribution::param_type
- random/std::negative_binomial_distribution::param_type::k
- random/std::negative_binomial_distribution::param_type::p
- random/std::negative_binomial_distribution::param_type::operator==
- random/std::negative_binomial_distribution::param_type::operator!=
helpviewer_keywords:
- std::negative_binomial_distribution [C++]
- std::negative_binomial_distribution [C++], reset
- std::negative_binomial_distribution [C++], k
- std::negative_binomial_distribution [C++], p
- std::negative_binomial_distribution [C++], param
- std::negative_binomial_distribution [C++], min
- std::negative_binomial_distribution [C++], max
- std::negative_binomial_distribution [C++], param_type
- std::negative_binomial_distribution [C++], param_type
ms.assetid: 7f5f0967-7fdd-4578-99d4-88f292b4fe9c
ms.openlocfilehash: d8e71b351d88a1c4dee61f88c18aec513d776cd3
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689251"
---
# <a name="negative_binomial_distribution-class"></a>negative_binomial_distribution Sınıfı

Negatif bir binom dağılımı üretir.

## <a name="syntax"></a>Sözdizimi

```
template<class IntType = int>
class negative_binomial_distribution
{
public:
    // types
    typedef IntType result_type;
    struct param_type;

    // constructor and reset functions
    explicit negative_binomial_distribution(result_type k = 1, double p = 0.5);
    explicit negative_binomial_distribution(const param_type& parm);
    void reset();

    // generating functions
    template `<`class URNG>
    result_type operator()(URNG& gen);
    template `<`class URNG>
    result_type operator()(URNG& gen, const param_type& parm);

    // property functions
    result_type k() const;
    double p() const;
    param_type param() const;
    void param(const param_type& parm);
    result_type min() const;
    result_type max() const;
};
```

### <a name="parameters"></a>Parametreler

*IntType* \
Tamsayı sonuç türü, varsayılan olarak **int 'tir**. Olası türler için bkz. [\<random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, Kullanıcı tarafından belirtilen **integral türünün değerlerini** üreten bir dağıtımı açıklar ya da hiçbir değer sağlanmazsa negatif binom dağıtım ayrık olasılık işlevine göre dağıtılır. Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar.

||||
|-|-|-|
|[negative_binomial_distribution](#negative_binomial_distribution)|`negative_binomial_distribution::k`|`negative_binomial_distribution::param`|
|`negative_binomial_distribution::operator()`|`negative_binomial_distribution::p`|[param_type](#param_type)|

Özellik üyeleri `k()` ve `p()` Şu anda depolanmış olan dağıtım parametresi değerlerini sırasıyla *k* ve *p* döndürür.

Özellik üyesi `param()` `param_type` depolanan dağıtım parametresi paketini ayarlar veya döndürür.

@No__t_0 ve `max()` üye işlevleri, sırasıyla olası en küçük sonucu ve en büyük olası sonucu döndürür.

@No__t_0 member işlevi, önbelleğe alınmış tüm değerleri atar, böylece `operator()` bir sonraki çağrının sonucu, çağrıdan önce altyapıdan alınan değerlere bağlı değildir.

@No__t_0 üye işlevleri, geçerli parametre paketinden ya da belirtilen parametre paketinden, URNG altyapısına göre oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz. [\<random >](../standard-library/random.md).

Negatif binom dağıtım ayrık olasılık işlevi hakkında ayrıntılı bilgi için, Wolfram MathWorld article [negatif binom dağıtımına](https://go.microsoft.com/fwlink/p/?linkid=400516)bakın.

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const int k, const double p, const int& s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::negative_binomial_distribution<> distr(k, p);

    std::cout << std::endl;
    std::cout << "k == " << distr.k() << std::endl;
    std::cout << "p == " << distr.p() << std::endl;

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
    int    k_dist = 1;
    double p_dist = 0.5;
    int    samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter an integer value for k distribution (where 0 < k): ";
    std::cin >> k_dist;
    std::cout << "Enter a double value for p distribution (where 0.0 < p <= 1.0): ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for a sample count: ";
    std::cin >> samples;

    test(k_dist, p_dist, samples);
}
```

İlk çalıştırma:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for k distribution (where 0 `<` k): 1
Enter a double value for p distribution (where 0.0 `<`p `<`= 1.0): .5
Enter an integer value for a sample count: 100

k == 1
p == 0.5
Histogram for 100 samples:
    0 :::::::::::::::::::::::::::::::::::::::::::
    1 ::::::::::::::::::::::::::::::::
    2 ::::::::::::
    3 :::::::
    4 ::::
    5 ::
```

İkinci çalıştırma:

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for k distribution (where 0 `<` k): 100
Enter a double value for p distribution (where 0.0 `<` p <= 1.0): .667
Enter an integer value for a sample count: 100

k == 100
p == 0.667
Histogram for 100 samples:
    31 ::
    32 :
    33 ::
    34 :
    35 ::
    37 ::
    38 :
    39 :
    40 ::
    41 :::
    42 :::
    43 :::::
    44 :::::
    45 ::::
    46 ::::::
    47 ::::::::
    48 :::
    49 :::
    50 :::::::::
    51 :::::::
    52 ::
    53 :::
    54 :::::
    56 ::::
    58 :
    59 :::::
    60 ::
    61 :
    62 ::
    64 :
    69 ::::
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<random >

**Ad alanı:** std

## <a name="negative_binomial_distribution"></a>negative_binomial_distribution::negative_binomial_distribution

Dağıtımı oluşturur.

```cpp
explicit negative_binomial_distribution(result_type k = 1, double p = 0.5);
explicit negative_binomial_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*k* \
@No__t_0 dağıtım parametresi.

*p* \
@No__t_0 dağıtım parametresi.

*para* \
Dağıtımı oluşturmak için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

Ön **koşul:** `0.0 < k` ve `0.0 < p ≤ 1.0`

İlk Oluşturucu, depolanan `p` değeri *p* değerini tutan ve depolanan `k` değeri *k*değerini tutan bir nesne oluşturur.

İkinci Oluşturucu, saklı parametreleri *parmdan*başlatılan bir nesne oluşturur. @No__t_0 üye işlevini çağırarak mevcut bir dağıtımın geçerli parametrelerini alabilir ve ayarlayabilirsiniz.

## <a name="param_type"></a>negative_binomial_distribution::p aram_type

Dağıtımın parametrelerini depolar.

struct param_type {typedef negative_binomial_distribution `<`result_type > distribution_type; param_type (result_type k = 1, Double p = 0,5); result_type k () const; Double p () const;

   bool işleç = = (const param_type & Right) const; bool işleç! = (const param_type & Right) const; };

### <a name="parameters"></a>Parametreler

*k* \
@No__t_0 dağıtım parametresi.

*p* \
@No__t_0 dağıtım parametresi.

*sağ* \
Karşılaştırmak için kullanılan `param_type` yapısı.

### <a name="remarks"></a>Açıklamalar

Ön **koşul:** `0.0 < k` ve `0.0 < p ≤ 1.0`

Bu yapı, örnek oluşturma sırasında dağıtımın sınıf oluşturucusuna, var olan bir dağıtımın saklı parametrelerini ayarlamak için `param()` member işlevine ve depolanan parametrelerin yerine kullanılacak `operator()` geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<random >](../standard-library/random.md)
