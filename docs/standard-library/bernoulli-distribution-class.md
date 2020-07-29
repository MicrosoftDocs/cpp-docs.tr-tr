---
title: bernoulli_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::bernoulli_distribution
- random/std::bernoulli_distribution::reset
- random/std::bernoulli_distribution::p
- random/std::bernoulli_distribution::param
- random/std::bernoulli_distribution::min
- random/std::bernoulli_distribution::max
- random/std::bernoulli_distribution::operator()
- random/std::bernoulli_distribution::param_type
- random/std::bernoulli_distribution::param_type::p
- random/std::bernoulli_distribution::param_type::operator==
- random/std::bernoulli_distribution::param_type::operator!=
helpviewer_keywords:
- std::bernoulli_distribution [C++]
- std::bernoulli_distribution [C++], reset
- std::bernoulli_distribution [C++], p
- std::bernoulli_distribution [C++], param
- std::bernoulli_distribution [C++], min
- std::bernoulli_distribution [C++], max
- std::bernoulli_distribution [C++], param_type
- std::bernoulli_distribution [C++], param_type
ms.assetid: 586bcde1-95ca-411a-bf17-4aaf19482f34
ms.openlocfilehash: 8b8e433b5ea1283fb60273a2fd21106c65867c0b
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230265"
---
# <a name="bernoulli_distribution-class"></a>bernoulli_distribution Sınıfı

Bir Bernoulli dağılımı üretir.

## <a name="syntax"></a>Söz dizimi

```cpp
class bernoulli_distribution
   {
public:
   // types
   typedef bool result_type;
   struct param_type;

   // constructors and reset functions
   explicit bernoulli_distribution(double p = 0.5);
   explicit bernoulli_distribution(const param_type& parm);
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

*URNG*\
Tekdüzen rastgele sayı Oluşturucu altyapısı. Olası türler için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

Sınıfı, **`bool`** Bernoulli Distribution ayrık olasılık işlevine göre dağıtılan türünde değerler üreten bir dağıtımı açıklar. Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar.

||||
|-|-|-|
|[bernoulli_distribution](#bernoulli_distribution)|`bernoulli_distribution::p`|`bernoulli_distribution::param`|
|`bernoulli_distribution::operator()`||[param_type](#param_type)|

Özellik üyesi, `p()` depolanmış olan dağıtım parametresi değerini döndürür `p` .

Özellik üyesi, `param()` `param_type` depolanan dağıtım parametresi paketini ayarlar veya döndürür.

`min()`Ve `max()` üye işlevleri, sırasıyla olası en küçük sonucu ve en büyük olası sonucu döndürür.

`reset()`Üye işlevi önbelleğe alınmış tüm değerleri atar, böylece sonraki çağrının sonucu, `operator()` çağrıdan önce altyapıdan alınan değerlere bağlı değildir.

`operator()`Üye işlevleri, geçerli parametre paketinden ya da belirtilen parametre paketinden, URNG altyapısına göre oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz [\<random>](../standard-library/random.md) ..

Bernoulli Distribution ayrık olasılık işlevi hakkında ayrıntılı bilgi için Wolfram MathWorld article [Bernoulli dağıtımına](https://go.microsoft.com/fwlink/p/?linkid=398467)bakın.

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double p, const int s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::bernoulli_distribution distr(p);

    std::cout << "p == " << distr.p() << std::endl;

    // generate the distribution as a histogram
    std::map<bool, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Histogram for " << s << " samples:" << std::endl;
    for (const auto& elem : histogram) {
        std::cout << std::boolalpha << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    double p_dist = 0.5;
    int samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a double value for p distribution (where 0.0 <= p <= 1.0): ";
    std::cin >> p_dist;
    std::cout << "Enter an integer value for a sample count: ";
    std::cin >> samples;

    test(p_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a double value for p distribution (where 0.0 <= p <= 1.0): .45
Enter an integer value for a sample count: 100
p == 0.45
Histogram for 100 samples:
false :::::::::::::::::::::::::::::::::::::::::::::::::::::::::::
true :::::::::::::::::::::::::::::::::::::::::
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="bernoulli_distributionbernoulli_distribution"></a><a name="bernoulli_distribution"></a>bernoulli_distribution:: bernoulli_distribution

Dağıtımı oluşturur.

```cpp
explicit bernoulli_distribution(double p = 0.5);
explicit bernoulli_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*Lama*\
Depolanan `p` dağıtım parametresi.

*parametresi*\
`param_type`Dağıtımı oluşturmak için kullanılan yapı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:**`0.0 ≤ p ≤ 1.0`

İlk Oluşturucu, saklı `p` değeri *p*değerini tutan bir nesne oluşturur.

İkinci Oluşturucu, saklı parametreleri *parmdan*başlatılan bir nesne oluşturur. Üye işlevini çağırarak mevcut bir dağıtımın geçerli parametrelerini alabilir ve ayarlayabilirsiniz `param()` .

## <a name="bernoulli_distributionparam_type"></a><a name="param_type"></a>bernoulli_distribution::p aram_type

Dağıtımın parametrelerini içerir.

struct param_type {typedef bernoulli_distribution distribution_type; param_type (çift p = 0,5); Double p () const;

   bool işleç = = (const param_type& right) const; bool işleç! = (const param_type& right) const; };

### <a name="parameters"></a>Parametreler

*Lama*\
Depolanan `p` dağıtım parametresi.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:**`0.0 ≤ p ≤ 1.0`

Bu yapı, örnek oluşturma sırasında dağıtımın sınıf oluşturucusuna, `param()` var olan bir dağıtımın saklı parametrelerini ayarlamak için üye işlevine ve `operator()` depolanan parametrelerin yerine kullanılmak üzere geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
