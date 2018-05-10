---
title: fisher_f_distribution sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- random/std::fisher_f_distribution
- random/std::fisher_f_distribution::reset
- random/std::fisher_f_distribution::m
- random/std::fisher_f_distribution::n
- random/std::fisher_f_distribution::param
- random/std::fisher_f_distribution::min
- random/std::fisher_f_distribution::max
- random/std::fisher_f_distribution::operator()
- random/std::fisher_f_distribution::param_type
- random/std::fisher_f_distribution::param_type::m
- random/std::fisher_f_distribution::param_type::n
- random/std::fisher_f_distribution::param_type::operator==
- random/std::fisher_f_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::fisher_f_distribution [C++]
- std::fisher_f_distribution [C++], reset
- std::fisher_f_distribution [C++], m
- std::fisher_f_distribution [C++], n
- std::fisher_f_distribution [C++], param
- std::fisher_f_distribution [C++], min
- std::fisher_f_distribution [C++], max
- std::fisher_f_distribution [C++], param_type
- std::fisher_f_distribution [C++], param_type
ms.assetid: 9513b6ce-3309-4be1-829b-f504bca35bbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 79ddd6ad1d27f1479bb653373517f7d8c1f1d3bc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="fisherfdistribution-class"></a>fisher_f_distribution Sınıfı

Fisher F dağıtım oluşturur.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class RealType = double>
class fisher_f_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;  // constructor and reset functions
   explicit fisher_f_distribution(result_type m = 1.0, result_type n = 1.0);
   explicit fisher_f_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   result_type m() const;
   result_type n() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametreler

*RealType* kayan noktalı bir sonuç türü, varsayılan olarak `double`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

*URNG* Tekdüzen rastgele sayı oluşturucu altyapısı. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Kayan nokta değerleri, bir kullanıcı tarafından belirtilen üreten bir dağıtım şablonu sınıf tanımlar türü veya türü `double` sağlanırsa, Fisher'ın F-dağıtım göre dağıtılmış. Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri.

||||
|-|-|-|
|[fisher_f_distribution](#fisher_f_distribution)|`fisher_f_distribution::m`|`fisher_f_distribution::param`|
|`fisher_f_distribution::operator()`|`fisher_f_distribution::n`|[param_type](#param_type)|

Özellik işlevleri `m()` ve `n()` dönüş depolanan dağıtım parametreleri için değerleri `m` ve `n` sırasıyla.

Özellik üyesi `param()` ayarlar veya döndürür `param_type` depolanan dağıtım parametresi paket.

`min()` Ve `max()` üye işlevleri en küçük olası sonuç ve olası en büyük sonuç sırasıyla döndürür.

`reset()` Üye işlevi herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerlere bağlı değildir.

`operator()` Üye işlevleri URNG motoru, geçerli parametre paket veya belirtilen parametre paket göre sonraki oluşturulan değeri döndürür.

Dağıtım sınıflar ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

F-dağıtım hakkında ayrıntılı bilgi için Wolfram MathWorld makalesine bakın [F-dağıtım](http://go.microsoft.com/fwlink/p/?linkid=400899).

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const double m, const double n, const int s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1701);

    std::fisher_f_distribution<> distr(m, n);

    std::cout << std::endl;
    std::cout << "min() == " << distr.min() << std::endl;
    std::cout << "max() == " << distr.max() << std::endl;
    std::cout << "m() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.m() << std::endl;
    std::cout << "n() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.n() << std::endl;

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
    double m_dist = 1;
    double n_dist = 1;
    int samples = 10;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter a floating point value for the \'m\' distribution parameter (must be greater than zero): ";
    std::cin >> m_dist;
    std::cout << "Enter a floating point value for the \'n\' distribution parameter (must be greater than zero): ";
    std::cin >> n_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(m_dist, n_dist, samples);
}

```

## <a name="output"></a>Çıkış

İlk çalıştırın:

```Output
Enter a floating point value for the 'm' distribution parameter (must be greater than zero): 1
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == 0
max() == 1.79769e+308
m() == 1.0000000000
n() == 1.0000000000
Distribution for 10 samples:
    1: 0.0204569549
    2: 0.0221376644
    3: 0.0297234962
    4: 0.1600937252
    5: 0.2775342196
    6: 0.3950701700
    7: 0.8363200295
    8: 0.9512500702
    9: 2.7844815974
    10: 3.4320929653
```

İkinci çalıştırın:

```Output
Enter a floating point value for the 'm' distribution parameter (must be greater than zero): 1
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): .1
Enter an integer value for the sample count: 10

min() == 0
max() == 1.79769e+308
m() == 1.0000000000
n() == 0.1000000000
Distribution for 10 samples:
    1: 0.0977725649
    2: 0.5304122767
    3: 4.9468518084
    4: 25.1012074939
    5: 48.8082121613
    6: 401.8075539377
    7: 8199.5947873699
    8: 226492.6855335717
    9: 2782062.6639740225
    10: 20829747131.7185860000
```

Üçüncü çalıştırın:

```Output
Enter a floating point value for the 'm' distribution parameter (must be greater than zero): .1
Enter a floating point value for the 'n' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 10

min() == 0
max() == 1.79769e+308
m() == 0.1000000000
n() == 1.0000000000
Distribution for 10 samples:
    1: 0.0000000000
    2: 0.0000000000
    3: 0.0000000000
    4: 0.0000000000
    5: 0.0000000033
    6: 0.0000073975
    7: 0.0000703800
    8: 0.0280427735
    9: 0.2660239949
    10: 3.4363333954
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="fisher_f_distribution"></a>  fisher_f_distribution::fisher_f_distribution

Dağıtım oluşturur.

```cpp
explicit fisher_f_distribution(result_type m = 1.0, result_type n = 1.0);
explicit fisher_f_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*m* `m` dağıtım parametresi.

*n* `n` dağıtım parametresi.

*parametre* `param_type` dağıtım oluşturmak için kullanılan yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < m` ve `0.0 < n`

İlk Oluşturucusu bir nesne oluşturur, depolanan `m` değeri tutan değeri *m* ve, depolanan `n` değeri tutan değeri *n*.

İkinci oluşturucu saklı parametreleri başlatılan bir nesne oluşturur *parametresi*. Elde edilir ve geçerli parametrelerinin varolan bir dağıtımına aranarak `param()` üye işlevi.

## <a name="param_type"></a>  fisher_f_distribution::param_type

Dağıtım parametreleri depolar.

```cpp
struct param_type {
   typedef fisher_f_distribution<result_type> distribution_type;
   param_type(result_type m = 1.0, result_type n = 1.0);
   result_type m() const;
   result_type n() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*m* `m` dağıtım parametresi.

*n* `n` dağıtım parametresi.

*sağ* `param_type` için karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `0.0 < m` ve `0.0 < n`

Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
