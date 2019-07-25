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
ms.openlocfilehash: 752226c9cacfdd36b93890502d62187f7b44a8da
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68454947"
---
# <a name="uniformrealdistribution-class"></a>uniform_real_distribution Sınıfı

Bir Tekdüzen (her değer eşit ölçüde olasıdır) bir çıkış aralığı içinde kapsamlı bir şekilde kayan nokta dağılımı üretir.

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
Kayan nokta sonuç türü, varsayılan olarak **Double**olur. Olası türler için bkz [ \<. Random >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, bir kullanıcı tarafından belirtilen integral kayan nokta türünün değerlerini, her değerin eşit ölçüde olası olması için bir dağıtımla üreten, dışlamalı bir dağıtımı açıklar. Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar.

||||
|-|-|-|
|[uniform_real_distribution](#uniform_real_distribution)|`uniform_real_distribution::a`|`uniform_real_distribution::param`|
|`uniform_real_distribution::operator()`|`uniform_real_distribution::b`|[param_type](#param_type)|

Özellik üyesi `a()` , dağıtımın Şu anda depolanmış en düşük ilişkisini döndürür, ancak `b()` Şu anda depolanan en yüksek sınırı döndürür. Bu dağıtım sınıfı için, bu en küçük ve en büyük değerler ortak özellik işlevleri `min()` tarafından döndürülen ve [ \<](../standard-library/random.md) `max()` rasgele > konusunda açıklanan şekilde aynıdır.

Özellik üyesi `param()` , `param_type` depolanan dağıtım parametresi paketini ayarlar veya döndürür.

`min()` Ve`max()` üye işlevleri, sırasıyla olası en küçük sonucu ve en büyük olası sonucu döndürür.

Üye işlevi önbelleğe alınmış tüm değerleri atar, böylece sonraki `operator()` çağrının sonucu, çağrıdan önce altyapıdan alınan değerlere bağlı değildir. `reset()`

`operator()` Üye işlevleri, geçerli parametre paketinden ya da belirtilen parametre paketinden, URNG altyapısına göre oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz [ \<. Random >](../standard-library/random.md).

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

**Üst bilgi:** \<rastgele >

**Ad alanı:** std

## <a name="uniform_real_distribution"></a>uniform_real_distribution::uniform_real_distribution

Dağıtımı oluşturur.

```cpp
explicit uniform_real_distribution(result_type a = 0.0, result_type b = 1.0);
explicit uniform_real_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*a*\
Rastgele değerler için alt sınır (dahil).

*kenarı*\
Rastgele değerler için üst sınır (dışlamalı).

*parametresi*\
Dağıtımı oluşturmak için kullanılan yapı.`param_type`

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `a < b`

İlk Oluşturucu, bir *değeri depolanan bir* nesne *oluşturur ve depolanan* *b* değeri *b*değerini tutar.

İkinci Oluşturucu, saklı parametreleri parmdan başlatılan bir nesne oluşturur . `param()` Üye işlevini çağırarak mevcut bir dağıtımın geçerli parametrelerini alabilir ve ayarlayabilirsiniz.

## <a name="param_type"></a>uniform_real_distribution::p aram_type

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

*a*\
Rastgele değerler için alt sınır (dahil).

*kenarı*\
Rastgele değerler için üst sınır (dışlamalı).

*Right*\
Karşılaştırılacak `param_type` nesne.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `a < b`

Bu yapı, örnek oluşturma sırasında dağıtımın sınıf oluşturucusuna, `param()` var olan bir dağıtımın saklı parametrelerini ayarlamak için üye işlevine `operator()` ve depolanan parametrelerin yerine kullanılmak üzere geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<Rastgele >](../standard-library/random.md)
