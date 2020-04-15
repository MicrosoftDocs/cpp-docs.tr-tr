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
ms.openlocfilehash: 7d9e1f1b9af3002faa9e2d9b20b7ee76dce35aea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372081"
---
# <a name="piecewise_linear_distribution-class"></a>piecewise_linear_distribution Sınıfı

Her aralıkta doğrusal değişen olasılık ile değişen genişlik aralıkları olan parçalı doğrusal dağılım oluşturur.

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

*RealType*\
Kayan nokta sonuç türü, varsayılan **olarak iki katına çıkar.** Olası türler için [ \<rasgele>](../standard-library/random.md)bakın.

## <a name="remarks"></a>Açıklamalar

Bu örnekleme dağılımı, her aralıkta doğrusal olarak değişen olasılıklarla değişen genişlik aralıklarına sahiptir. Diğer örnekleme dağıtımları hakkında bilgi için [piecewise_linear_distribution](../standard-library/piecewise-constant-distribution-class.md) ve [discrete_distribution](../standard-library/discrete-distribution-class.md)bakın.

Bireysel üyeler le ilgili makalelere aşağıdaki tablo bağlantıları:

||||
|-|-|-|
|[piecewise_linear_distribution](#piecewise_linear_distribution)|`piecewise_linear_distribution::intervals`|`piecewise_linear_distribution::param`|
|`piecewise_linear_distribution::operator()`|`piecewise_linear_distribution::densities`|[param_type](#param_type)|

Özellik işlevi, `intervals()` `vector<result_type>` dağıtımın depolanan aralıkları kümesiyle bir döndürür.

Özellik işlevi, `densities()` `vector<result_type>` konstrüktör parametrelerinde sağlanan ağırlıklara göre hesaplanan her aralık kümesi için depolanan yoğunluklarla bir döndürür.

Özellik üyesi, `param()` depolanan `param_type` dağıtım parametre paketini ayarlar veya döndürür.

`min()` Ve `max()` üye işlevler, sırasıyla mümkün olan en küçük sonucu ve mümkün olan en büyük sonucu döndürer.

`reset()` Üye işlev önbelleğe alınan değerleri atar, böylece bir sonraki `operator()` çağrının sonucu çağrıdan önce motordan elde edilen değerlere bağlı olmaz.

Üye `operator()` işlevler, geçerli parametre paketinden veya belirtilen parametre paketinden URNG motoruna dayalı olarak oluşturulan bir sonraki değeri döndürür.

Dağıtım sınıfları ve üyeleri hakkında daha fazla bilgi için [ \<rastgele>](../standard-library/random.md)bakın.

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

**Üstbilgi:** \<rastgele>

**Ad alanı:** std

## <a name="piecewise_linear_distributionpiecewise_linear_distribution"></a><a name="piecewise_linear_distribution"></a>piecewise_linear_distribution::piecewise_linear_distribution

Dağıtımı kurar.

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

*firstI*\
Dağıtım aralığındaki ilk öğenin giriş yineleyicisi.

*lastI*\
Dağıtım aralığındaki son öğenin giriş yineleyicisi.

*ilkW*\
Ağırlık aralığındaki ilk öğenin giriş yineleyicisi.

*Aralık*\
Dağıtım aralıkları ile bir [initializer_list.](../cpp/initializers.md)

*Sayısı*\
Dağıtım aralığındaki eleman sayısı.

*xmin*\
Dağıtım aralığındaki en düşük değer.

*xmax*\
Dağıtım aralığındaki en yüksek değer. *Xmin'den*büyük olmalı.

*weightfunc*\
Dağılım için olasılık işlevini temsil eden nesne. Hem parametre hem de iade değeri **çift**e dönüştürülebilir olmalıdır.

*parm*\
Dağılımı oluşturmak için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan oluşturucu, depolanan parametreleri, olasılık yoğunluğu 1 olan 0 ile 1 arasında bir aralık olacak şekilde ayarlar.

Yineleyici aralık oluşturucu

```cpp
template <class InputIteratorI, class InputIteratorW>
piecewise_linear_distribution(
    InputIteratorI firstI,
    InputIteratorI lastI,
    InputIteratorW firstW);
```

bir dağıtım nesnesi, yinelemecilerin yinelemeleri ile `firstI`[, `lastI`) ve *ilkW'den*başlayan eşleşen bir ağırlık dizisi ile inşa eder.

Baş harf listesi oluşturucu

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    initializer_list<result_type> intervals,
    UnaryOperation weightfunc);
```

*weightfunc*işlevinden oluşturulan başharf liste *aralıklarından* ve ağırlıklardan aralıklarla bir dağıtım nesnesi inşa eder.

Olarak tanımlanan yapıcı

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    size_t count,
    result_type xmin,
    result_type xmax,
    UnaryOperation weightfunc);
```

[ `xmin,xmax`]üzerinde eşit olarak dağıtılan *sayı* aralıkları olan bir dağıtım nesnesi inşa eder, her aralık ağırlıkfunc'a göre her aralık ağırlıkları atayan ve *weightfunc* bir parametre kabul etmeli ve her ikisi de dönüştürülebilir bir dönüş değerine `double`sahip olmalıdır. *weightfunc* **Ön koşul:**`xmin < xmax`.

Olarak tanımlanan yapıcı

```cpp
explicit piecewise_linear_distribution(const param_type& parm);
```

depolanan parametre yapısı olarak *parm* kullanarak bir dağıtım nesnesi inşa eder.

## <a name="piecewise_linear_distributionparam_type"></a><a name="param_type"></a>piecewise_linear_distribution::param_type

Dağıtımın tüm parametrelerini depolar.

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

piecewise_linear_distribution için konstrüktör [parametrelerine](#piecewise_linear_distribution)bakın.

### <a name="remarks"></a>Açıklamalar

**Ön koşul:**`xmin < xmax`

Bu yapı, varolan bir dağılımın depolanan parametrelerini `param()` ayarlamak ve `operator()` depolanan parametrelerin yerine kullanılmak üzere üye işlevine anında dağıtım Sınıfı oluşturucuya geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele>](../standard-library/random.md)
