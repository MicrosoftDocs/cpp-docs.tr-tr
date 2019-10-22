---
title: normal_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::normal_distribution
- random/std::normal_distribution::reset
- random/std::normal_distribution::mean
- random/std::normal_distribution::stddev
- random/std::normal_distribution::param
- random/std::normal_distribution::min
- random/std::normal_distribution::max
- random/std::normal_distribution::operator()
- random/std::normal_distribution::param_type
- random/std::normal_distribution::param_type::mean
- random/std::normal_distribution::param_type::stddev
- random/std::normal_distribution::param_type::operator==
- random/std::normal_distribution::param_type::operator!=
helpviewer_keywords:
- std::normal_distribution [C++]
- std::normal_distribution [C++], reset
- std::normal_distribution [C++], mean
- std::normal_distribution [C++], stddev
- std::normal_distribution [C++], param
- std::normal_distribution [C++], min
- std::normal_distribution [C++], max
- std::normal_distribution [C++], param_type
- std::normal_distribution [C++], param_type
ms.assetid: bf92cdbd-bc72-4d4a-b588-173d748f0d7d
ms.openlocfilehash: 39c5321d5bc22e14ace3335e4a925bf7284d1cb0
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689243"
---
# <a name="normal_distribution-class"></a>normal_distribution Sınıfı

Normal bir dağıtım oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class RealType = double>
class normal_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructors and reset functions
   explicit normal_distribution(result_type mean = 0.0, result_type stddev = 1.0);
   explicit normal_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type mean() const;
   result_type stddev() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametreler

*RealType* \
Kayan nokta sonuç türü, varsayılan olarak **Double**olur. Olası türler için bkz. [\<random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, Kullanıcı tarafından belirtilen integral türünün değerlerini üreten bir dağıtımı açıklar veya yoksa **Double** , normal dağıtıma göre dağıtılır. Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar.

||||
|-|-|-|
|[normal_distribution](#normal_distribution)|`normal_distribution::mean`|`normal_distribution::param`|
|`normal_distribution::operator()`|`normal_distribution::stddev`|[param_type](#param_type)|

Özellik işlevleri `mean()` ve `stddev()` saklanan dağıtım parametrelerinin *Ortalama* ve *StdDev* değerlerini döndürür.

Özellik üyesi `param()` `param_type` depolanan dağıtım parametresi paketini ayarlar veya döndürür.

@No__t_0 ve `max()` üye işlevleri, sırasıyla olası en küçük sonucu ve en büyük olası sonucu döndürür.

@No__t_0 member işlevi, önbelleğe alınmış tüm değerleri atar, böylece `operator()` bir sonraki çağrının sonucu, çağrıdan önce altyapıdan alınan değerlere bağlı değildir.

@No__t_0 üye işlevleri, geçerli parametre paketinden ya da belirtilen parametre paketinden, URNG altyapısına göre oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz. [\<random >](../standard-library/random.md).

Normal dağıtım hakkında ayrıntılı bilgi için, bkz. Wolfram MathWorld article [normal dağıtım](https://go.microsoft.com/fwlink/p/?linkid=400924).

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

using namespace std;

void test(const double m, const double s, const int samples) {

    // uncomment to use a non-deterministic seed
    //    random_device gen;
    //    mt19937 gen(rd());
    mt19937 gen(1701);

    normal_distribution<> distr(m, s);

    cout << endl;
    cout << "min() == " << distr.min() << endl;
    cout << "max() == " << distr.max() << endl;
    cout << "m() == " << fixed << setw(11) << setprecision(10) << distr.mean() << endl;
    cout << "s() == " << fixed << setw(11) << setprecision(10) << distr.stddev() << endl;

    // generate the distribution as a histogram
    map<double, int> histogram;
    for (int i = 0; i < samples; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    cout << "Distribution for " << samples << " samples:" << endl;
    int counter = 0;
    for (const auto& elem : histogram) {
        cout << fixed << setw(11) << ++counter << ": "
            << setw(14) << setprecision(10) << elem.first << endl;
    }
    cout << endl;
}

int main()
{
    double m_dist = 1;
    double s_dist = 1;
    int samples = 10;

    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;
    cout << "Enter a floating point value for the 'mean' distribution parameter: ";
    cin >> m_dist;
    cout << "Enter a floating point value for the 'stddev' distribution parameter (must be greater than zero): ";
    cin >> s_dist;
    cout << "Enter an integer value for the sample count: ";
    cin >> samples;

    test(m_dist, s_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter: 0
Enter a floating point value for the 'stddev' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == -1.79769e+308
max() == 1.79769e+308
m() == 0.0000000000
s() == 1.0000000000
Distribution for 10 samples:
    1: -0.8845823965
    2: -0.1995761116
    3: -0.1162665130
    4: -0.0685154932
    5: 0.0403741461
    6: 0.1591327792
    7: 1.0414389924
    8: 1.5876269426
    9: 1.6362637713
    10: 2.7821317338
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<random >

**Ad alanı:** std

## <a name="normal_distribution"></a>normal_distribution::normal_distribution

Dağıtımı oluşturur.

```cpp
explicit normal_distribution(result_type mean = 0.0, result_type stddev = 1.0);
explicit normal_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*ortalama* \
@No__t_0 dağıtım parametresi.

*StdDev* \
@No__t_0 dağıtım parametresi.

*para* \
Dağıtımı oluşturmak için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < stddev`

İlk Oluşturucu, depolanan `mean` değeri *Ortalama* değeri tutan ve depolanan `stddev` değeri *StdDev*değerini tutan bir nesne oluşturur.

İkinci Oluşturucu, saklı parametreleri *parmdan*başlatılan bir nesne oluşturur. @No__t_0 üye işlevini çağırarak mevcut bir dağıtımın geçerli parametrelerini alabilir ve ayarlayabilirsiniz.

## <a name="param_type"></a>normal_distribution::p aram_type

Dağıtımın parametrelerini depolar.

```cpp
struct param_type {
   typedef normal_distribution<result_type> distribution_type;
   param_type(result_type mean = 0.0, result_type stddev = 1.0);
   result_type mean() const;
   result_type stddev() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*ortalama* \
@No__t_0 dağıtım parametresi.

*StdDev* \
@No__t_0 dağıtım parametresi.

*sağ* \
Karşılaştırmak için kullanılan `param_type` yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < stddev`

Bu yapı, örnek oluşturma sırasında dağıtımın sınıf oluşturucusuna, var olan bir dağıtımın saklı parametrelerini ayarlamak için `param()` member işlevine ve depolanan parametrelerin yerine kullanılacak `operator()` geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<random >](../standard-library/random.md)
