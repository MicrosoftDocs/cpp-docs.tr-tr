---
title: piecewise_linear_distribution sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- random/std::piecewise_linear_distribution
- random/std::piecewise_linear_distribution::reset
- random/std::piecewise_linear_distribution::intervals
- random/std::piecewise_linear_distribution::densities
- random/std::piecewise_linear_distribution::param
- random/std::piecewise_linear_distribution::min
- random/std::piecewise_linear_distribution::max
- random/std::piecewise_linear_distribution::operator()
- random/std::piecewise_linear_distribution::param_type
- random/std::piecewise_linear_distribution::param_type::intervals
- random/std::piecewise_linear_distribution::param_type::densities
- random/std::piecewise_linear_distribution::param_type::operator==
- random/std::piecewise_linear_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::piecewise_linear_distribution [C++]
- std::piecewise_linear_distribution [C++], reset
- std::piecewise_linear_distribution [C++], intervals
- std::piecewise_linear_distribution [C++], densities
- std::piecewise_linear_distribution [C++], param
- std::piecewise_linear_distribution [C++], min
- std::piecewise_linear_distribution [C++], max
- std::piecewise_linear_distribution [C++], param_type
- std::piecewise_linear_distribution [C++], param_type
ms.assetid: cd141152-7163-4754-8f98-c6d6500005e0
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9d8a2a8195284ce5f8c051bfa217b99c96f7e3
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="piecewiselineardistribution-class"></a>piecewise_linear_distribution Sınıfı

Bir piecewise oluşturur doğrusal olarak değişen olasılık değişen genişliği aralıklarıyla her aralığa sahip doğrusal dağıtım.

## <a name="syntax"></a>Sözdizimi

```cpp
template<class RealType = double>
class piecewise_linear_distribution
   {
public:
   // types
   typedef RealType result_type;
   struct param_type;

   // constructor and reset functions
   piecewise_linear_distribution();
   template <class InputIteratorI, class InputIteratorW>
   piecewise_linear_distribution(
      InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);
   template <class UnaryOperation>
   piecewise_linear_distribution(
      initializer_list<result_type> intervals, UnaryOperation weightfunc);
   template <class UnaryOperation>
   piecewise_linear_distribution(
      size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   explicit piecewise_linear_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   vector<result_type> intervals() const;
   vector<result_type> densities() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };
```

### <a name="parameters"></a>Parametreler

`RealType` Kayan nokta sonuç türü, varsayılan olarak `double`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu örnekleme dağıtım doğrusal olarak değişen olasılık değişen genişliği aralıklarıyla her aralığa sahiptir. Diğer örnekleme dağıtımları hakkında daha fazla bilgi için bkz: [piecewise_linear_distribution](../standard-library/piecewise-constant-distribution-class.md) ve [discrete_distribution](../standard-library/discrete-distribution-class.md).

Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri:

||||
|-|-|-|
|[piecewise_linear_distribution](#piecewise_linear_distribution)|`piecewise_linear_distribution::intervals`|`piecewise_linear_distribution::param`|
|`piecewise_linear_distribution::operator()`|`piecewise_linear_distribution::densities`|[param_type](#param_type)|

Özellik işlevi `intervals()` döndüren bir `vector<result_type>` dağıtım saklı aralıklar kümesi ile.

Özellik işlevi `densities()` döndüren bir `vector<result_type>` Oluşturucusu parametrelerinde sağlanan ağırlıklara göre hesaplanan saklı densities her aralığı kümesi ile.

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

using namespace std;

void test(const int s) {

    // uncomment to use a non-deterministic generator
    // random_device rd;
    // mt19937 gen(rd());
    mt19937 gen(1701);

    // Three intervals, non-uniform: 0 to 1, 1 to 6, and 6 to 15
    vector<double> intervals{ 0, 1, 6, 15 };
    // weights determine the densities used by the distribution
    vector<double> weights{ 1, 5, 5, 10 };

    piecewise_linear_distribution<double> distr(intervals.begin(), intervals.end(), weights.begin());

    cout << endl;
    cout << "min() == " << distr.min() << endl;
    cout << "max() == " << distr.max() << endl;
    cout << "intervals (index: interval):" << endl;
    vector<double> i = distr.intervals();
    int counter = 0;
    for (const auto& n : i) {
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;
        ++counter;
    }
    cout << endl;
    cout << "densities (index: density):" << endl;
    vector<double> d = distr.densities();
    counter = 0;
    for (const auto& n : d) {
        cout << fixed << setw(11) << counter << ": " << setw(14) << setprecision(10) << n << endl;
        ++counter;
    }
    cout << endl;

    // generate the distribution as a histogram
    map<int, int> histogram;
    for (int i = 0; i < s; ++i) {
        ++histogram[distr(gen)];
    }

    // print results
    cout << "Distribution for " << s << " samples:" << endl;
    for (const auto& elem : histogram) {
        cout << setw(5) << elem.first << '-' << elem.first + 1 << ' ' << string(elem.second, ':') << endl;
    }
    cout << endl;
}

int main()
{
    int samples = 100;

    cout << "Use CTRL-Z to bypass data entry and run using default values." << endl;
    cout << "Enter an integer value for the sample count: ";
    cin >> samples;

    test(samples);
}
```

```Output
Use CTRL-Z to bypass data entry and run using default values.
Enter an integer value for the sample count: 100
min() == 0
max() == 15
intervals (index: interval):
          0:   0.0000000000
          1:   1.0000000000
          2:   6.0000000000
          3:  15.0000000000
densities (index: density):
          0:   0.0645161290
          1:   0.3225806452
          2:   0.3225806452
          3:   0.6451612903
Distribution for 100 samples:
    0-1 :::::::::::::::::::::
    1-2 ::::::
    2-3 :::
    3-4 :::::::
    4-5 ::::::
    5-6 ::::::
    6-7 :::::
    7-8 ::::::::::
    8-9 ::::::::::
    9-10 ::::::
   10-11 ::::
   11-12 :::
   12-13 :::
   13-14 :::::
   14-15 :::::
```

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="piecewise_linear_distribution"></a>  piecewise_linear_distribution::piecewise_linear_distribution

Dağıtım oluşturur.

```cpp
// default constructor
piecewise_linear_distribution();

// constructs using a range of intervals, [firstI, lastI), with
// matching weights starting at firstW
template <class InputIteratorI, class InputIteratorW>
piecewise_linear_distribution(InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);

// constructs using an initializer list for range of intervals,
// with weights generated by function weightfunc
template <class UnaryOperation>
piecewise_linear_distribution(initializer_list<RealType>
intervals, UnaryOperation weightfunc);

// constructs using an initializer list for range of count intervals,
// distributed uniformly over [xmin,xmax] with weights generated by function weightfunc
template <class UnaryOperation>
piecewise_linear_distribution(size_t count, RealType xmin, RealType xmax, UnaryOperation weightfunc);

// constructs from an existing param_type structure
explicit piecewise_linear_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*firstI* giriş yineleyici dağıtım aralıktaki ilk öğesinin.

*lastI* giriş yineleyici dağıtım aralıktaki son öğesi.

*firstW* giriş yineleyici ağırlıkları aralıktaki ilk öğesinin.

*aralıkları* bir [initializer_list](../cpp/initializers.md) dağıtım aralıkları ile.

*Count* dağıtım aralığına öğe sayısı.

*xMin* dağıtım aralığındaki en düşük değer.

*xMax* dağıtım aralığındaki en yüksek değer. Büyük olmalı *xmin*.

*weightfunc* dağıtım olasılık işlevi temsil eden nesne. Parametre ve dönüş değeri dönüştürülebilir `double`.

*parametre* dağıtım oluşturmak için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

Bir aralık, 0 ve 1, 1 ile olasılık yoğunluğu olmasını gibi varsayılan oluşturucu saklı parametreleri ayarlar.

Yineleyici aralığı Oluşturucusu

```cpp
template <class InputIteratorI, class InputIteratorW>
piecewise_linear_distribution(
    InputIteratorI firstI,
    InputIteratorI lastI,
    InputIteratorW firstW);
```

yineleyiciler gelen itnervals dağıtım nesnesiyle dizisi oluşturur [ `firstI`, `lastI`) ve eşleşen bir ağırlık dizisi başlayarak `firstW`.

Başlatıcı listesi Oluşturucusu

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    initializer_list<result_type> intervals,
    UnaryOperation weightfunc);
```

ıntializer listeden aralıkları dağıtım nesnesiyle yapıları `intervals` ve ağırlıklarını işlevinden oluşturulan `weightfunc`.

Tanımlanan Oluşturucusu

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    size_t count,
    result_type xmin,
    result_type xmax,
    UnaryOperation weightfunc);
```

bir dağıtım nesnesiyle oluşturur `count` aralıkları dağıtılmış hep üzerinde [ `xmin,xmax`], her aralığı atama ağırlık verir göre işlevi `weightfunc`, ve `weightfunc` bir parametre kabul etmeniz ve satır başı olması gerekir değeri, her ikisi de hangi dönüştürülebilir, `double`. **Önkoşul:**`xmin < xmax`.

Tanımlanan Oluşturucusu

```cpp
explicit piecewise_linear_distribution(const param_type& parm);
```

dağıtım nesnesi kullanılarak yapıları `parm` depolanan parametrenin yapısı olarak.

## <a name="param_type"></a>  piecewise_linear_distribution::param_type

Dağıtım tüm parametreleri depolar.

```cpp
struct param_type {
   typedef piecewise_linear_distribution<result_type> distribution_type;
   param_type();
   template <class IterI, class IterW>
   param_type(
      IterI firstI, IterI lastI, IterW firstW);
   template <class UnaryOperation>
   param_type(
      size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   std::vector<result_type> densities() const;
   std::vector<result_type> intervals() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

Oluşturucu parametreleri için bkz: [piecewise_linear_distribution](#piecewise_linear_distribution).

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `xmin < xmax`

Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
