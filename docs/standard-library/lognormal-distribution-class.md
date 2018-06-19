---
title: lognormal_distribution sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::lognormal_distribution
- random/std::lognormal_distribution::reset
- random/std::lognormal_distribution::m
- random/std::lognormal_distribution::s
- random/std::lognormal_distribution::param
- random/std::lognormal_distribution::min
- random/std::lognormal_distribution::max
- random/std::lognormal_distribution::operator()
- random/std::lognormal_distribution::param_type
- random/std::lognormal_distribution::param_type::m
- random/std::lognormal_distribution::param_type::s
- random/std::lognormal_distribution::param_type::operator==
- random/std::lognormal_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::lognormal_distribution [C++]
- std::lognormal_distribution [C++], reset
- std::lognormal_distribution [C++], m
- std::lognormal_distribution [C++], s
- std::lognormal_distribution [C++], param
- std::lognormal_distribution [C++], min
- std::lognormal_distribution [C++], max
- std::lognormal_distribution [C++], param_type
- std::lognormal_distribution [C++], param_type
ms.assetid: f2d6a431-6c3a-4370-b12e-4adb4ddf6cc4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 72b42546f140dfd150676c8bc21b4b651815281f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33864170"
---
# <a name="lognormaldistribution-class"></a>lognormal_distribution Sınıfı

Günlük normal dağıtım oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class RealType = double>
class lognormal_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;
   // constructor and reset functions
   explicit lognormal_distribution(result_type m = 0.0, result_type s = 1.0);
   explicit lognormal_distribution(const param_type& parm);
   void reset();
   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);
   // property functions
   result_type m() const;
   result_type s() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametreler

*RealType* kayan noktalı bir sonuç türü, varsayılan olarak `double`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bir kullanıcı tarafından belirtilen integral değerleri üreten bir dağıtım şablonu sınıf tanımlar türü veya türü `double` sağlanırsa, günlük Normal dağıtım göre dağıtılmış. Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri.

||||
|-|-|-|
|[lognormal_distribution](#lognormal_distribution)|`lognormal_distribution::m`|`lognormal_distribution::param`|
|`lognormal_distribution::operator()`|`lognormal_distribution::s`|[param_type](#param_type)|

Özellik işlevleri `m()` ve `s()` dönüş depolanan dağıtım parametreleri için değerleri *m* ve *s*sırasıyla.

Özellik üyesi `param()` ayarlar veya döndürür `param_type` depolanan dağıtım parametresi paket.

`min()` Ve `max()` üye işlevleri en küçük olası sonuç ve olası en büyük sonuç sırasıyla döndürür.

`reset()` Üye işlevi herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerlere bağlı değildir.

`operator()` Üye işlevleri URNG motoru, geçerli parametre paket veya belirtilen parametre paket göre sonraki oluşturulan değeri döndürür.

Dağıtım sınıflar ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

Wolfram MathWorld makaleyi LogNormal dağılımı hakkında ayrıntılı bilgi için bkz: [LogNormal dağıtım](http://go.microsoft.com/fwlink/p/?linkid=400917).

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

    lognormal_distribution<> distr(m, s);

    cout << endl;
    cout << "min() == " << distr.min() << endl;
    cout << "max() == " << distr.max() << endl;
    cout << "m() == " << fixed << setw(11) << setprecision(10) << distr.m() << endl;
    cout << "s() == " << fixed << setw(11) << setprecision(10) << distr.s() << endl;

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
    cout << "Enter a floating point value for the 'm' distribution parameter: ";
    cin >> m_dist;
    cout << "Enter a floating point value for the 's' distribution parameter (must be greater than zero): ";
    cin >> s_dist;
    cout << "Enter an integer value for the sample count: ";
    cin >> samples;

    test(m_dist, s_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'm' distribution parameter: 0
Enter a floating point value for the 's' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == -1.79769e+308
max() == 1.79769e+308
m() == 0.0000000000
s() == 1.0000000000
Distribution for 10 samples:
    1: 0.3862809339
    2: 0.4128865601
    3: 0.4490576787
    4: 0.4862035428
    5: 0.5930607126
    6: 0.8190778771
    7: 0.8902379317
    8: 2.8332911667
    9: 5.1359445565
    10: 5.4406507912
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="lognormal_distribution"></a>  lognormal_distribution::lognormal_distribution

Dağıtım oluşturur.

```cpp
explicit lognormal_distribution(RealType m = 0.0, RealType s = 1.0);
explicit lognormal_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*m* `m` dağıtım parametresi.

*s* `s` dağıtım parametresi.

*parametre* `param_type` dağıtım oluşturmak için kullanılan yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < s`

İlk Oluşturucusu bir nesne oluşturur, depolanan `m` değeri tutan değeri *m* ve, depolanan `s` değeri tutan değeri *s*.

İkinci oluşturucu saklı parametreleri başlatılan bir nesne oluşturur *parametresi*. Elde edilir ve geçerli parametrelerinin varolan bir dağıtımına aranarak `param()` üye işlevi.

## <a name="param_type"></a>  lognormal_distribution::param_type

Dağıtım parametreleri depolar.

```cpp
struct param_type {
   typedef lognormal_distribution<result_type> distribution_type;
   param_type(result_type m = 0.0, result_type s = 1.0);
   result_type m() const;
   result_type s() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
};
```

### <a name="parameters"></a>Parametreler

*m* `m` dağıtım parametresi.

*s* `s` dağıtım parametresi.

*sağ* `param_type` karşılaştırmak için kullanılan yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < s`

Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
