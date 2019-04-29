---
title: piecewise_linear_distribution Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 327da9c6793e4e74f099bdc313ce34720561bbd0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62370379"
---
# <a name="piecewiselineardistribution-class"></a>piecewise_linear_distribution Sınıfı

Oluşturur bir piecewise doğrusal olarak değişen olasılık değişen genişlikli aralıklarıyla her aralığında sahip doğrusal dağılımı.

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

*RealType*<br/>
Kayan nokta sonuç türü ve ayarlarına **çift**. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu örnekleme dağıtım her aralığında değişen genişlikli doğrusal olarak değişen olasılık aralıklarıyla sahiptir. Diğer örnekleme dağıtımları hakkında daha fazla bilgi için bkz. [piecewise_linear_distribution](../standard-library/piecewise-constant-distribution-class.md) ve [discrete_distribution](../standard-library/discrete-distribution-class.md).

Aşağıdaki tablo ilgili makalelerin bağlantısı için tek tek üyeleri:

||||
|-|-|-|
|[piecewise_linear_distribution](#piecewise_linear_distribution)|`piecewise_linear_distribution::intervals`|`piecewise_linear_distribution::param`|
|`piecewise_linear_distribution::operator()`|`piecewise_linear_distribution::densities`|[param_type](#param_type)|

Özellik işlevi `intervals()` döndürür bir `vector<result_type>` dağılımının saklı aralıkları kümesiyle.

Özellik işlevi `densities()` döndürür bir `vector<result_type>` Oluşturucu parametresi sağlanan ağırlıklara göre hesaplanan saklı densities her aralığı kümesi ile.

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

Dağıtımı oluşturur.

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

*firstI*<br/>
Dağıtım aralıktaki ilk öğenin bir giriş yineleyici.

*lastI*<br/>
Dağıtım aralıktaki son öğeden bir giriş yineleyici.

*firstW*<br/>
Ağırlıklar aralıktaki ilk öğenin bir giriş yineleyici.

*aralıkları*<br/>
Bir [initializer_list](../cpp/initializers.md) dağıtım aralıklarına sahip.

*Sayısı*<br/>
Dağıtım aralıktaki öğelerin sayısı.

*xMin*<br/>
Dağıtım aralıktaki en düşük değeri.

*xmax*<br/>
Dağıtım aralıktaki en yüksek değeri. Değerinden büyük olmalıdır *xmin*.

*weightfunc*<br/>
Dağıtım için olasılık işlevini temsil eden nesne. Parametre ve dönüş değeri hem dönüştürülebilir olmalıdır **çift**.

*parametre*<br/>
Dağıtımın oluşturulması için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

Var olan bir aralık, 0-1, 1 ile bir olasılık yoğunluğu, varsayılan oluşturucu depolanmış parametreleri ayarlar.

Yineleyici aralığı Oluşturucusu

```cpp
template <class InputIteratorI, class InputIteratorW>
piecewise_linear_distribution(
    InputIteratorI firstI,
    InputIteratorI lastI,
    InputIteratorW firstW);
```

yineleyiciler gelen itnervals dağıtım nesnesiyle dizisi oluşturur [ `firstI`, `lastI`) ve eşleşen bir ağırlık dizisi başlayarak *firstW*.

Başlatıcı listesi Oluşturucusu

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    initializer_list<result_type> intervals,
    UnaryOperation weightfunc);
```

Başlatıcı listesi aralıklarını dağıtım nesnesiyle oluşturur *aralıkları* ve işlevden oluşturulan ağırlıkları *weightfunc*.

Tanımlanan Oluşturucusu

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    size_t count,
    result_type xmin,
    result_type xmax,
    UnaryOperation weightfunc);
```

bir dağıtım nesnesiyle oluşturur *sayısı* aralıkları üzerinde birörnek dağıtılmış [ `xmin,xmax`], ağırlık verme göre işlevi her aralığı atama *weightfunc*, ve  *weightfunc* bir parametre kabul etmeniz ve ikisi için de dönüştürülebilir bir dönüş değeri olması gerekir `double`. **Önkoşul:**`xmin < xmax`.

Tanımlanan Oluşturucusu

```cpp
explicit piecewise_linear_distribution(const param_type& parm);
```

dağıtım nesnesi kullanılarak oluşturur *parametresi* depolanmış parametre yapısı olarak.

## <a name="param_type"></a>  piecewise_linear_distribution::param_type

Dağıtım, tüm parametreleri depolar.

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

Oluşturucu parametresi için bkz. [piecewise_linear_distribution](#piecewise_linear_distribution).

### <a name="remarks"></a>Açıklamalar

**Önkoşul:** `xmin < xmax`

Bu yapı dağıtım'ın sınıf oluşturucusu oluşturmada, en çok geçirilebilir `param()` depolanan parametre var olan bir dağıtım için ve ayarlamak için üye işlevi `operator()` depolanan parametrelerin yerine kullanılacak.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
