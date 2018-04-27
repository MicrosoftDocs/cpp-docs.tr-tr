---
title: uniform_real_distribution sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
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
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91f50119c3eed4f9dc71b64a50ec1e80819a084b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="uniformrealdistribution-class"></a>uniform_real_distribution Sınıfı

(Her değere eşit olası) Tekdüzen oluşturur (bunlar dahil) özel bir çıktı aralıkta kayan nokta dağıtım.

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

*RealType* kayan noktalı bir sonuç türü, varsayılan olarak `double`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı, böylece her değere eşit olası bir dağıtım noktası türüyle kayan bir kullanıcı tarafından belirtilen integral değerleri üreten bir özel (bunlar dahil) dağıtım açıklar. Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri.

||||
|-|-|-|
|[uniform_real_distribution](#uniform_real_distribution)|`uniform_real_distribution::a`|`uniform_real_distribution::param`|
|`uniform_real_distribution::operator()`|`uniform_real_distribution::b`|[param_type](#param_type)|

Özellik üyesi `a()` şu anda depolanan minimum bağlı dağıtımını döndürür sırada `b()` şu anda depolanan en fazla bağlı döndürür. Bu dağıtım sınıfı için bu minimum ve maksimum değerleri ortak özelliği işlevleri tarafından döndürülen aynıdır `min()` ve `max()` açıklanan [ \<rastgele >](../standard-library/random.md) konu.

Özellik üyesi `param()` ayarlar veya döndürür `param_type` depolanan dağıtım parametresi paket.

`min()` Ve `max()` üye işlevleri en küçük olası sonuç ve olası en büyük sonuç sırasıyla döndürür.

`reset()` Üye işlevi herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerlere bağlı değildir.

`operator()` Üye işlevleri URNG motoru, geçerli parametre paket veya belirtilen parametre paket göre sonraki oluşturulan değeri döndürür.

Dağıtım sınıflar ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).

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

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="uniform_real_distribution"></a>  uniform_real_distribution::uniform_real_distribution

Dağıtım oluşturur.

```cpp
explicit uniform_real_distribution(result_type a = 0.0, result_type b = 1.0);
explicit uniform_real_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*bir* rastgele değerler, kapsayıcı için alt sınır.

*b* rastgele değerler, özel kullanım için üst sınır.

*parametre* `param_type` dağıtım oluşturmak için kullanılan yapısı.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `a < b`

İlk Oluşturucusu bir nesne oluşturur, depolanan `a` değeri tutan değeri *bir* ve, depolanan `b` değeri tutan değeri *b*.

İkinci oluşturucu saklı parametreleri başlatılan bir nesne oluşturur *parametresi*. Elde edilir ve geçerli parametrelerinin varolan bir dağıtımına aranarak `param()` üye işlevi.

## <a name="param_type"></a>  uniform_real_distribution::param_type

Dağıtım tüm parametreleri depolar.

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

*bir* rastgele değerler, kapsayıcı için alt sınır.

*b* rastgele değerler, özel kullanım için üst sınır.

*sağ* `param_type` için karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `a < b`

Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
