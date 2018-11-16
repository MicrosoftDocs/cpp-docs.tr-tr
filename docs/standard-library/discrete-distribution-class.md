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
ms.openlocfilehash: 7ad375c14e9034a55d280a2927d6ef00f098ddbc
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693913"
---
# <a name="discretedistribution-class"></a>discrete_distribution Sınıfı

Her aralığında Tekdüzen olasılık Tekdüzen genişlikli aralıklarıyla sahip ayrı bir tam sayı dağılımı üretir.

## <a name="syntax"></a>Sözdizimi

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

*İnt'i*<br/>
Tamsayı sonuç türü varsayılan olarak **int**. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).

## <a name="remarks"></a>Açıklamalar

Bu örnekleme dağıtım Tekdüzen olasılık Tekdüzen genişlikli aralıklarıyla her aralığında sahiptir. Diğer örnekleme dağıtımları hakkında daha fazla bilgi için bkz. [piecewise_linear_distribution sınıfı](../standard-library/piecewise-linear-distribution-class.md) ve [piecewise_constant_distribution sınıfı](../standard-library/piecewise-constant-distribution-class.md).

Aşağıdaki tablo ilgili makalelerin bağlantısı için tek tek üyeleri:

|||
|-|-|
|[discrete_distribution](#discrete_distribution)|`discrete_distribution::param`|
|`discrete_distribution::operator()`|[param_type](#param_type)|

Özellik işlevi `vector<double> probabilities()` bireysel olasılıklar oluşturulan her bir tamsayı döndürür.

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

**Başlık:** \<rastgele >

**Namespace:** std

## <a name="discrete_distribution"></a>  discrete_distribution::discrete_distribution

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

*firstW*<br/>
Dağıtımın oluşturulması için listeden birinci yineleyicisi.

*lastW*<br/>
(Boş bir öğenin sona yineleyiciler kullandığından dahil) dağıtımın oluşturulması hangi listesindeki son yineleyici.

*weightlist*<br/>
[İnitializer_list](../cpp/initializers.md) ilk dağıtımın oluşturulması.

*Sayısı*<br/>
Dağıtım aralıktaki öğelerin sayısı. Varsa `count==0`, varsayılan oluşturucu eşdeğerdir (her zaman sıfır oluşturur).

*Düşük*<br/>
Dağıtım aralıktaki en düşük değeri.

*Yüksek*<br/>
Dağıtım aralıktaki en yüksek değeri.

*weightfunc*<br/>
Dağıtım için olasılık işlevini temsil eden nesne. Parametre ve dönüş değeri hem dönüştürülebilir olmalıdır **çift**.

*parametre*<br/>
`param_type` Dağıtımın oluşturulması için kullanılan yapısı.

### <a name="remarks"></a>Açıklamalar

Varsayılan Oluşturucu, saklı olasılık değeri değeri 1 olan bir öğeye sahip bir nesne oluşturur. Bu, her zaman sıfır oluşturan bir dağıtım neden olur.

Parametrelere sahip yineleyici aralık oluşturucu *firstW* ve *lastW* Yineleyicilerin aralığı dizisi üzerinde gerçekleştirilen ağırlık değerleri kullanarak bir dağıtım nesnesi oluşturur. [ *firstW*, *lastW*).

Sahip başlatıcı listesi Oluşturucusu bir *weightlist* parametresi ağırlıkları Başlatıcı listesinde bir dağıtım nesnesiyle oluşturur *weightlist*.

Sahip Oluşturucu *sayısı*, *düşük*, *yüksek*, ve *weightfunc* tabanlı bir dağıtım nesnesi başlatılmadı parametreleri yapıları Bu kurallar hakkında:

- Varsa *sayısı* < 1 **n** = 1 ve bu nedenle, her zaman sıfır oluşturma varsayılan oluşturucuya eşdeğerdir.
- Varsa *sayısı* > 0 ise, **n** = *sayısı*. Sağlanan **d** = (*yüksek* - *düşük*) / **n** büyüktür kullanarak sıfır **d** Tekdüzen alt aralıklara, her ağırlık şu şekilde atanır: `weight[k] = weightfunc(x)`burada **x** = *düşük* + **k**  *  **d** + **d** / 2, için **k** = 0,..., **n** - 1.

Var Oluşturucusu bir `param_type` parametre *parametresi* kullanarak bir dağıtım nesnesi oluşturur *parametresi* depolanmış parametre yapısı olarak.

## <a name="param_type"></a>  discrete_distribution::param_type

Dağıtım, tüm parametreleri depolar.

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

*firstW*<br/>
Dağıtımın oluşturulması için listeden birinci yineleyicisi.

*lastW*<br/>
(Boş bir öğenin sona yineleyiciler kullandığından dahil) dağıtımın oluşturulması hangi listesindeki son yineleyici.

*weightlist*<br/>
[İnitializer_list](../cpp/initializers.md) ilk dağıtımın oluşturulması.

*Sayısı*<br/>
Dağıtım aralıktaki öğelerin sayısı. Varsa *sayısı* 0'dır, bu varsayılan oluşturucuya eşdeğerdir (her zaman sıfır oluşturur).

*Düşük*<br/>
Dağıtım aralıktaki en düşük değeri.

*Yüksek*<br/>
Dağıtım aralıktaki en yüksek değeri.

*weightfunc*<br/>
Dağıtım için olasılık işlevini temsil eden nesne. Parametre ve dönüş değeri hem dönüştürülebilir olmalıdır **çift**.

*sağ*<br/>
`param_type` İçin karşılaştırılacak nesne.

### <a name="remarks"></a>Açıklamalar

Bu parametre paketi geçirilebilir `operator()` dönüş değerini oluşturmak için.

## <a name="see-also"></a>Ayrıca bkz.

[\<rastgele >](../standard-library/random.md)<br/>
