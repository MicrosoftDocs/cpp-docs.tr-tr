---
title: discrete_distribution Sınıfı
ms.date: 11/04/2016
f1_keywords:
- random/std::discrete_distribution
- random/std::discrete_distribution::reset
- random/std::discrete_distribution::probabilities
- random/std::discrete_distribution::param
- random/std::discrete_distribution::min
- random/std::discrete_distribution::max
- random/std::discrete_distribution::operator()
- random/std::discrete_distribution::param_type
- random/std::discrete_distribution::param_type::probabilities
- random/std::discrete_distribution::param_type::operator==
- random/std::discrete_distribution::param_type::operator!=
helpviewer_keywords:
- std::discrete_distribution [C++]
- std::discrete_distribution [C++], reset
- std::discrete_distribution [C++], probabilities
- std::discrete_distribution [C++], param
- std::discrete_distribution [C++], min
- std::discrete_distribution [C++], max
- std::discrete_distribution [C++], param_type
- std::discrete_distribution [C++], param_type
ms.assetid: 8c8ba8f8-c06f-4f07-b354-f53950142fcf
ms.openlocfilehash: 65d5c993efd1cb9c6dd35f11223ed39e026ed7c6
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217811"
---
# <a name="discrete_distribution-class"></a>discrete_distribution Sınıfı

Her aralıkta Tekdüzen olasılığa sahip tek bir tamsayı dağılımı üretir.

## <a name="syntax"></a>Söz dizimi

```cpp
template<class IntType = int>
class discrete_distribution
   {
public:
   // types
   typedef IntType result_type;
   struct param_type;

   // constructor and reset functions
   discrete_distribution();
   template <class InputIterator>
   discrete_distribution(InputIterator firstW, InputIterator lastW);
   discrete_distribution(initializer_list<double> weightlist);
   template <class UnaryOperation>
   discrete_distribution(size_t count, double xmin, double xmax, UnaryOperation funcweight);
   explicit discrete_distribution(const param_type& parm);
   void reset();

   // generating functions
   template <class URNG>
   result_type operator()(URNG& gen);
   template <class URNG>
   result_type operator()(URNG& gen, const param_type& parm);

   // property functions
   vector<double> probabilities() const;
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

Bu örnekleme dağıtımında, her aralıkta Tekdüzen olasılığa sahip tek biçimli bir Aralık vardır. Diğer örnekleme dağıtımları hakkında daha fazla bilgi için bkz. [Piecewise_linear_distribution Class](../standard-library/piecewise-linear-distribution-class.md) and [piecewise_constant_distribution Class](../standard-library/piecewise-constant-distribution-class.md).

Aşağıdaki tablo, bireysel üyelerle ilgili makalelere bağlantı sağlar:

|||
|-|-|
|[discrete_distribution](#discrete_distribution)|`discrete_distribution::param`|
|`discrete_distribution::operator()`|[param_type](#param_type)|

Property işlevi, `vector<double> probabilities()` oluşturulan her tamsayı için bireysel olasılıkların tümünü döndürür.

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

    discrete_distribution<> distr({ 1, 2, 3, 4, 5 });

    cout << endl;
    cout << "min() == " << distr.min() << endl;
    cout << "max() == " << distr.max() << endl;
    cout << "probabilities (value: probability):" << endl;
    vector<double> p = distr.probabilities();
    int counter = 0;
    for (const auto& n : p) {
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
        cout << setw(5) << elem.first << ' ' << string(elem.second, ':') << endl;
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
max() == 4
probabilities (value: probability):
          0:   0.0666666667
          1:   0.1333333333
          2:   0.2000000000
          3:   0.2666666667
          4:   0.3333333333

Distribution for 100 samples:
    0 :::
    1 ::::::::::::::
    2 ::::::::::::::::::
    3 :::::::::::::::::::::::::::::
    4 ::::::::::::::::::::::::::::::::::::
```

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<random>

**Ad alanı:** std

## <a name="discrete_distributiondiscrete_distribution"></a><a name="discrete_distribution"></a>discrete_distribution::d iscrete_distribution

Dağıtımı oluşturur.

```cpp
// default constructor
discrete_distribution();

// construct using a range of weights, [firstW, lastW)
template <class InputIterator>
discrete_distribution(InputIterator firstW, InputIterator lastW);

// construct using an initializer list for range of weights
discrete_distribution(initializer_list<double> weightlist);

// construct using unary operation function
template <class UnaryOperation>
discrete_distribution(size_t count, double low, double high, UnaryOperation weightfunc);

// construct from an existing param_type structure
explicit discrete_distribution(const param_type& parm);
```

### <a name="parameters"></a>Parametreler

*firstW*\
Dağıtım oluşturmak için listedeki ilk Yineleyici.

*lastW*\
Dağıtım oluşturmak için kullanılan listedeki son Yineleyici (yineleyiciler, son için boş bir öğe kullandığından).

*ağırlıklı Tlist*\
Dağıtımın oluşturulacağı [initializer_list](../cpp/initializers.md) .

*biriktirme*\
Dağıtım aralığındaki öğe sayısı. `count==0`, Varsayılan oluşturucuya eşdeğerdir (her zaman sıfır üretir).

*zayıf*\
Dağıtım aralığındaki en düşük değer.

*geniş*\
Dağıtım aralığındaki en yüksek değer.

*ağırlıklı tfunc*\
Dağıtım için olasılık işlevini temsil eden nesne. Hem parametre hem de dönüş değeri öğesine dönüştürülebilir olmalıdır **`double`** .

*parametresi*\
`param_type`Dağıtımı oluşturmak için kullanılan yapı.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, saklı olasılık değeri 1 değeri olan bir öğeye sahip olan bir nesne oluşturur. Bu, her zaman sıfır üreten bir dağıtıma neden olur.

*FirstW* ve *lastw* parametreleri olan yineleyici Aralık Oluşturucusu, [*firstW*, *lastw*) Aralık sırası üzerinden yineleyiciler tarafından alınan ağırlık değerlerini kullanarak bir dağıtım nesnesi oluşturur.

Bir Weight *Tlist* parametresi olan *Başlatıcı listesi Oluşturucusu*, bir dağıtım nesnesi oluşturur ve bu, başlatıcı listesinden ağırlıklardır.

*Count*, *Low*, *High*ve *tartıtfunc* parametrelerine sahip Oluşturucu, bu kurallara göre başlatılan bir dağıtım nesnesi oluşturur:

- Eğer *sayı* < 1, **n** = 1 ise ve bu, varsayılan oluşturucuya eşdeğerdir, her zaman sıfır olarak oluşturulur.
- Eğer *sayım* > 0, **n**  =  *sayısı*. Belirtilen **d** = (*yüksek*  -  *düşük*)/ **n** , sıfırdan büyük **d** biçimli alt aralıklar kullanılarak, her ağırlığa şu şekilde atanır: `weight[k] = weightfunc(x)` , burada **x**  =  *Low*  +  **k**  *  **d**  +  **d** /2, **k** = 0,..., **n** -1.

Bir parametreye sahip Oluşturucu, `param_type` saklı *parm* parametre yapısı olarak *Pard* kullanarak bir dağıtım nesnesi oluşturur.

## <a name="discrete_distributionparam_type"></a><a name="param_type"></a>discrete_distribution::p aram_type

Dağıtımın tüm parametrelerini depolar.

```cpp
struct param_type {
   typedef discrete_distribution<result_type> distribution_type;
   param_type();

   // construct using a range of weights, [firstW, lastW)
   template <class InputIterator>
   param_type(InputIterator firstW, InputIterator lastW);

   // construct using an initializer list for range of weights
   param_type(initializer_list<double> weightlist);

   // construct using unary operation function
   template <class UnaryOperation>
   param_type(size_t count, double low, double high, UnaryOperation weightfunc);

   std::vector<double> probabilities() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };
```

### <a name="parameters"></a>Parametreler

*firstW*\
Dağıtım oluşturmak için listedeki ilk Yineleyici.

*lastW*\
Dağıtım oluşturmak için kullanılan listedeki son Yineleyici (yineleyiciler, son için boş bir öğe kullandığından).

*ağırlıklı Tlist*\
Dağıtımın oluşturulacağı [initializer_list](../cpp/initializers.md) .

*biriktirme*\
Dağıtım aralığındaki öğe sayısı. *Count* değeri 0 ise, bu varsayılan oluşturucuya eşdeğerdir (her zaman sıfır üretir).

*zayıf*\
Dağıtım aralığındaki en düşük değer.

*geniş*\
Dağıtım aralığındaki en yüksek değer.

*ağırlıklı tfunc*\
Dağıtım için olasılık işlevini temsil eden nesne. Hem parametre hem de dönüş değeri öğesine dönüştürülebilir olmalıdır **`double`** .

*Right*\
`param_type`Karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

Bu parametre paketi `operator()` , dönüş değeri oluşturmak için öğesine geçirilebilir.

## <a name="see-also"></a>Ayrıca bkz.

[\<random>](../standard-library/random.md)
