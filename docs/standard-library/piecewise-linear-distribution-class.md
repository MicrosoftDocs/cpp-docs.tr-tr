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
ms.openlocfilehash: 57c6e19bc56068c98f6c85978c7af68e56cb4f2a
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88832691"
---
# <a name="piecewise_linear_distribution-class"></a>piecewise_linear_distribution Sınıfı

Her aralıkta doğrusal olarak değişen olasılığa sahip, değişen genişlik aralıklarına sahip piecewise doğrusal bir dağıtım oluşturur.

## <a name="syntax"></a>Söz dizimi

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
Kayan nokta sonuç türü, varsayılan olarak olur **`double`** . Olası türler için bkz [\<random>](../standard-library/random.md) ..

## <a name="remarks"></a>Açıklamalar

Bu örnekleme dağıtımında, her aralıkta doğrusal olarak değişen olasılığa sahip farklı genişlik aralıkları vardır. Diğer örnekleme dağıtımları hakkında daha fazla bilgi için bkz. [piecewise_linear_distribution](../standard-library/piecewise-constant-distribution-class.md) ve [discrete_distribution](../standard-library/discrete-distribution-class.md).

Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar:

[piecewise_linear_distribution](#piecewise_linear_distribution)\
[param_type](#param_type)

Özellik işlevi, `intervals()` `vector<result_type>` dağıtımın saklı aralıkları kümesiyle bir döndürür.

Property işlevi, `densities()` `vector<result_type>` Oluşturucu parametrelerinde belirtilen ağırlığa göre hesaplanan her bir Aralık kümesi için depolanan normalleştirlıklarla birlikte döndürür.

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

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="piecewise_linear_distributionpiecewise_linear_distribution"></a><a name="piecewise_linear_distribution"></a> piecewise_linear_distribution::p iecewise_linear_distribution

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

*Ilki*\
Dağıtım aralığındaki ilk öğenin giriş yineleyicisi.

*lastI*\
Dağıtım aralığındaki son öğenin giriş yineleyicisi.

*firstW*\
Ağırlık aralığındaki ilk öğenin giriş yineleyicisi.

*aralıklarla*\
Dağıtım aralıklarıyla bir [initializer_list](../cpp/initializers.md) .

*biriktirme*\
Dağıtım aralığındaki öğe sayısı.

*xmin*\
Dağıtım aralığındaki en düşük değer.

*maksimum xmak*\
Dağıtım aralığındaki en yüksek değer. *XMin*'den büyük olmalıdır.

*ağırlıklı tfunc*\
Dağıtım için olasılık işlevini temsil eden nesne. Hem parametre hem de dönüş değeri öğesine dönüştürülebilir olmalıdır **`double`** .

*parametresi*\
Dağıtımı oluşturmak için kullanılan parametre yapısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, 1 ile 1 arasında, olasılık yoğunluğu 1 olan bir Aralık olmak üzere saklı parametreleri ayarlar.

Yineleyici Aralık Oluşturucusu

```cpp
template <class InputIteratorI, class InputIteratorW>
piecewise_linear_distribution(
    InputIteratorI firstI,
    InputIteratorI lastI,
    InputIteratorW firstW);
```

[,) sırası üzerinde yineleyiciler ile bir dağıtım nesnesi oluşturur `firstI` `lastI` ve *firstW*'dan başlayarak eşleşen bir ağırlık dizisi.

Başlatıcı listesi Oluşturucusu

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    initializer_list<result_type> intervals,
    UnaryOperation weightfunc);
```

Başlatıcı listesi *aralıklarıyla* ve ağırlık *tfunc*işlevinden oluşturulan ağırlıklarla bir dağıtım nesnesi oluşturur.

Olarak tanımlanan Oluşturucu

```cpp
template <class UnaryOperation>
piecewise_linear_distribution(
    size_t count,
    result_type xmin,
    result_type xmax,
    UnaryOperation weightfunc);
```

[] üzerinde eşit olarak dağıtılan *sayı* aralıklarına sahip bir dağıtım nesnesi oluşturur `xmin,xmax` , her Aralık ağırlıklarını, ağırlıkçalıştır *weightfunc*işlevine göre atanır ve *ağırlıklı tfunc* bir parametre kabul etmeli ve her ikisi de dönüştürülebilir bir dönüş değerine sahip olmalıdır **`double`** . Ön **koşul:** `xmin < xmax` .

Olarak tanımlanan Oluşturucu

```cpp
explicit piecewise_linear_distribution(const param_type& parm);
```

saklı parametre yapısı olarak *Pard* 'yi kullanarak bir dağıtım nesnesi oluşturur.

## <a name="piecewise_linear_distributionparam_type"></a><a name="param_type"></a> piecewise_linear_distribution::p aram_type

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

[Piecewise_linear_distribution](#piecewise_linear_distribution)için Oluşturucu parametreleri bölümüne bakın.

### <a name="remarks"></a>Açıklamalar

**Önkoşul:**`xmin < xmax`

Bu yapı, örnek oluşturma sırasında dağıtımın sınıf oluşturucusuna, `param()` var olan bir dağıtımın saklı parametrelerini ayarlamak için üye işlevine ve `operator()` depolanan parametrelerin yerine kullanılmak üzere geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
