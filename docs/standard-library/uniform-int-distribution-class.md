---
description: 'Hakkında daha fazla bilgi edinin: uniform_int_distribution sınıfı'
title: uniform_int_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::uniform_int_distribution
- random/std::uniform_int_distribution::reset
- random/std::uniform_int_distribution::a
- random/std::uniform_int_distribution::b
- random/std::uniform_int_distribution::param
- random/std::uniform_int_distribution::min
- random/std::uniform_int_distribution::max
- random/std::uniform_int_distribution::operator()
- random/std::uniform_int_distribution::param_type
- random/std::uniform_int_distribution::param_type::a
- random/std::uniform_int_distribution::param_type::b
- random/std::uniform_int_distribution::param_type::operator==
- random/std::uniform_int_distribution::param_type::operator!=
helpviewer_keywords:
- std::uniform_int_distribution [C++]
- std::uniform_int_distribution [C++], reset
- std::uniform_int_distribution [C++], a
- std::uniform_int_distribution [C++], b
- std::uniform_int_distribution [C++], param
- std::uniform_int_distribution [C++], min
- std::uniform_int_distribution [C++], max
- std::uniform_int_distribution [C++], param_type
- std::uniform_int_distribution [C++], param_type
ms.assetid: a1867dcd-3bd9-4787-afe3-4b62692c1d04
ms.openlocfilehash: 96e5782c04ce77f8d705f60002ef8316b26793e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97132697"
---
# <a name="uniform_int_distribution-class"></a>uniform_int_distribution Sınıfı

Kapsamlı bir çıkış aralığında (her değer eşit ölçüde olası) tam sayı dağılımı üretir.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class IntType = int>
   class uniform_int_distribution {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructors and reset functions
   explicit uniform_int_distribution(
      result_type a = 0, result_type b = numeric_limits<result_type>::max());
   explicit uniform_int_distribution(const param_type& parm);
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

*IntType*\
Tamsayı sonuç türü, varsayılan olarak olur **`int`** . Olası türler için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

Sınıf şablonu, her değerin eşit olması için bir dağıtımla birlikte Kullanıcı tarafından belirtilen integral türünün değerlerini üreten kapsamlı bir dağılımı açıklar. Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar.

[uniform_int_distribution](#uniform_int_distribution)\
[param_type](#param_type)

Özellik üyesi, `a()` dağıtımın Şu anda depolanmış en düşük ilişkisini döndürür, ancak `b()` Şu anda depolanan en yüksek sınırı döndürür. Bu dağıtım sınıfı için, bu minimum ve maksimum değerler, ortak özellik işlevleri ve tarafından Döndürülenler ile aynıdır `min()` `max()` .

Özellik üyesi, `param()` `param_type` depolanan dağıtım parametresi paketini ayarlar veya döndürür.

`min()`Ve `max()` üye işlevleri, sırasıyla olası en küçük sonucu ve en büyük olası sonucu döndürür.

`reset()`Üye işlevi önbelleğe alınmış tüm değerleri atar, böylece sonraki çağrının sonucu, `operator()` çağrıdan önce altyapıdan alınan değerlere bağlı değildir.

`operator()`Üye işlevleri, geçerli parametre paketinden ya da belirtilen parametre paketinden, URNG altyapısına göre oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz [\<random>](../standard-library/random.md) ..

## <a name="example"></a>Örnek

```cpp
// compile with: /EHsc /W4
#include <random>
#include <iostream>
#include <iomanip>
#include <string>
#include <map>

void test(const int a, const int b, const int s) {

    // uncomment to use a non-deterministic seed
    //    std::random_device rd;
    //    std::mt19937 gen(rd());
    std::mt19937 gen(1729);

    std::uniform_int_distribution<> distr(a, b);

    std::cout << "lower bound == " << distr.a() << std::endl;
    std::cout << "upper bound == " << distr.b() << std::endl;

    // generate the distribution as a histogram
    std::map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    std::cout << "Distribution for " << s << " samples:" << std::endl;
    for (const auto& elem : histogram) {
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;
    }
    std::cout << std::endl;
}

int main()
{
    int a_dist = 1;
    int b_dist = 10;

    int samples = 100;

    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;
    std::cout << "Enter an integer value for the lower bound of the distribution: ";
    std::cin >> a_dist;
    std::cout << "Enter an integer value for the upper bound of the distribution: ";
    std::cin >> b_dist;
    std::cout << "Enter an integer value for the sample count: ";
    std::cin >> samples;

    test(a_dist, b_dist, samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the lower bound of the distribution: 0
Enter an integer value for the upper bound of the distribution: 12
Enter an integer value for the sample count: 200
lower bound == 0
upper bound == 12
Distribution for 200 samples:
    0 :::::::::::::::
    1 :::::::::::::::::::::
    2 ::::::::::::::::::
    3 :::::::::::::::
    4 :::::::
    5 :::::::::::::::::::::
    6 :::::::::::::
    7 ::::::::::
    8 :::::::::::::::
    9 :::::::::::::
   10 ::::::::::::::::::::::
   11 :::::::::::::
   12 :::::::::::::::::
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="uniform_int_distributionuniform_int_distribution"></a><a name="uniform_int_distribution"></a> uniform_int_distribution:: uniform_int_distribution

Dağıtımı oluşturur.

```cpp
explicit uniform_int_distribution(
   result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
explicit uniform_int_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*a*\
Rastgele değerler için alt sınır (dahil).

*kenarı*\
Rastgele değerler için üst sınır (dahil).

*parametresi*\
`param_type`Dağıtımı oluşturmak için kullanılan yapı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:**`a ≤ b`

İlk Oluşturucu *, bir değeri depolanan bir* nesne *oluşturur ve depolanan* *b* değeri *b* değerini tutar.

İkinci Oluşturucu, saklı parametreleri *parmdan* başlatılan bir nesne oluşturur. Üye işlevini çağırarak mevcut bir dağıtımın geçerli parametrelerini alabilir ve ayarlayabilirsiniz `param()` .

## <a name="uniform_int_distributionparam_type"></a><a name="param_type"></a> uniform_int_distribution::p aram_type

Dağıtımın parametrelerini depolar.

```cpp
struct param_type {
   typedef uniform_int_distribution<result_type> distribution_type;
   param_type(
      result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
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
Rastgele değerler için üst sınır (dahil).

*Right*\
`param_type`Karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:**`a ≤ b`

Bu yapı, örnek oluşturma sırasında dağıtımın sınıf oluşturucusuna, `param()` var olan bir dağıtımın saklı parametrelerini ayarlamak için üye işlevine ve `operator()` depolanan parametrelerin yerine kullanılmak üzere geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
