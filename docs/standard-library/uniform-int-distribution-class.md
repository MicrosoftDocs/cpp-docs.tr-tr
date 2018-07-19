---
title: uniform_int_distribution sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d982aee3f5542e8bfcff1da96ce3e70775ead5fe
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38961584"
---
# <a name="uniformintdistribution-class"></a>uniform_int_distribution Sınıfı

Oluşturur Tekdüzen (her değer eşit düzeyde olasıdır) bir tam sayı dağılımı içeren-içeren bir çıkış aralığı içinde.

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

*İnt'i* tamsayı sonuç türü varsayılan olarak **int**. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı bir dağıtımla kullanıcı tanımlı integral türü değerleri üreten ve böylece her değer eşit düzeyde olasıdır içeren bir dağıtım açıklar. Aşağıdaki tablo ilgili makalelerin bağlantısı için tek tek üyeleri.

||||
|-|-|-|
|[uniform_int_distribution](#uniform_int_distribution)|`uniform_int_distribution::a`|`uniform_int_distribution::param`|
|`uniform_int_distribution::operator()`|`uniform_int_distribution::b`|[param_type](#param_type)|

Özellik üyesi `a()` şuan depolanan en bağlı dağılımını döndürür ancak `b()` şuan depolanan maksimum sınır döndürür. Bu dağıtım sınıfı için bu minimum ve maksimum değerleri ortak özelliği işlevleri tarafından döndürülen aynıdır `min()` ve `max()`.

Özellik üyesi `param()` ayarlar veya döndürür `param_type` saklı dağıtım parametre paketi.

`min()` Ve `max()` üye işlevleri olası en küçük sonuç ve olası en büyük sonuç sırasıyla döndürür.

`reset()` Üye işlevi herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerleri, bağlı değildir.

`operator()` Üye işlevler URNG motoru, geçerli parametre paketi veya belirtilen parametre paketi göre sonraki oluşturulan değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

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

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="uniform_int_distribution"></a>  uniform_int_distribution::uniform_int_distribution

Dağıtımı oluşturur.

```cpp
explicit uniform_int_distribution(
   result_type a = 0, result_type b = std::numeric_limits<result_type>::max());
explicit uniform_int_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*a*  
Kapsamlı rastgele değerler için alt sınır.

*b*  
Kapsamlı rastgele değerler için üst sınır.

*parametre*  
`param_type` Dağıtımın oluşturulması için kullanılan yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `a ≤ b`

İlk Oluşturucu bir nesne oluşturur, saklı *bir* değerine değeri *bir* ve saklı *b* değerine değeri *b*.

İkinci oluşturucu depolanmış parametreleri dan başlatılan bir nesne oluşturur *parametresi*. Alabilir ve çağırarak geçerli var olan bir dağıtım parametrelerini ayarlayın `param()` üye işlevi.

## <a name="param_type"></a>  uniform_int_distribution::param_type

Dağıtım parametrelerini depolar.

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

*a*  
Kapsamlı rastgele değerler için alt sınır.

*b*  
Kapsamlı rastgele değerler için üst sınır.

*sağ*  
`param_type` İçin karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `a ≤ b`

Bu yapı dağıtım'ın sınıf oluşturucusu oluşturmada, en çok geçirilebilir `param()` depolanan parametre var olan bir dağıtım için ve ayarlamak için üye işlevi `operator()` depolanan parametrelerin yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
