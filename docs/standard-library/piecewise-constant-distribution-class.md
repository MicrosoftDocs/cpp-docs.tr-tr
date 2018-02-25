---
title: "piecewise_constant_distribution sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::piecewise_constant_distribution
- random/std::piecewise_constant_distribution::reset
- random/std::piecewise_constant_distribution::intervals
- random/std::piecewise_constant_distribution::densities
- random/std::piecewise_constant_distribution::param
- random/std::piecewise_constant_distribution::min
- random/std::piecewise_constant_distribution::max
- random/std::piecewise_constant_distribution::operator()
- random/std::piecewise_constant_distribution::param_type
- random/std::piecewise_constant_distribution::param_type::intervals
- random/std::piecewise_constant_distribution::param_type::densities
- random/std::piecewise_constant_distribution::param_type::operator==
- random/std::piecewise_constant_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::piecewise_constant_distribution [C++]
- std::piecewise_constant_distribution [C++], reset
- std::piecewise_constant_distribution [C++], intervals
- std::piecewise_constant_distribution [C++], densities
- std::piecewise_constant_distribution [C++], param
- std::piecewise_constant_distribution [C++], min
- std::piecewise_constant_distribution [C++], max
- std::piecewise_constant_distribution [C++], param_type
- std::piecewise_constant_distribution [C++], param_type
ms.assetid: 2c9a21fa-623e-4d63-b827-3f1556b6dedb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 923398932307845bffb95e8ef3fd7ef83e38530f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="piecewiseconstantdistribution-class"></a>piecewise_constant_distribution Sınıfı
Bir piecewise oluşturur Tekdüzen olasılık değişen genişliği aralıklarıyla her aralığa sahip sabit dağıtım.  
  
## <a name="syntax"></a>Sözdizimi  
```  
template<class RealType = double>  
class piecewise_constant_distribution  
   {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   
   // constructor and reset functions  
   piecewise_constant_distribution();
   template <class InputIteratorI, class InputIteratorW>  
   piecewise_constant_distribution(
       InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);
   template <class UnaryOperation>  
   piecewise_constant_distribution(
      initializer_list<result_type> intervals, UnaryOperation weightfunc);
   template <class UnaryOperation>  
   piecewise_constant_distribution(
      size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   explicit piecewise_constant_distribution(const param_type& parm);
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
*RealType*  
Kayan nokta sonuç türü, varsayılan olarak `double`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="remarks"></a>Açıklamalar  
Bu örnekleme dağıtım Tekdüzen olasılık değişen genişliği aralıklarıyla her aralığa sahiptir. Diğer örnekleme dağıtımları hakkında daha fazla bilgi için bkz: [piecewise_linear_distribution sınıfı](../standard-library/piecewise-linear-distribution-class.md) ve [discrete_distribution](../standard-library/discrete-distribution-class.md).  
  
Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri:  
  
||||  
|-|-|-|  
|[piecewise_constant_distribution](#piecewise_constant_distribution)|`piecewise_constant_distribution::intervals`|`piecewise_constant_distribution::param`|  
|`piecewise_constant_distribution::operator()`|`piecewise_constant_distribution::densities`|[param_type](#param_type)|  
  
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
    vector<double> weights{ 1, 5, 10 };  
  
    piecewise_constant_distribution<double> distr(intervals.begin(), intervals.end(), weights.begin());  
  
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
        cout << setw(5) << elem.first << '-' << elem.first+1 << ' ' << string(elem.second, ':') << endl;  
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
          0:   0.0625000000          
          1:   0.0625000000          
          2:   0.0694444444
Distribution for 100 samples:
    0-1 :::::::    
    1-2 ::::::    
    2-3 :::::    
    3-4 ::::::    
    4-5 :::::::    
    5-6 ::::::    
    6-7 :::    
    7-8 ::::::::::    
    8-9 ::::::    
    9-10 ::::::::::::   
    10-11 :::::   
    11-12 ::::::   
    12-13 :::::::::   
    13-14 ::::   
    14-15 ::::::::  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
##  <a name="piecewise_constant_distribution"></a>  piecewise_constant_distribution::piecewise_constant_distribution  
Dağıtım oluşturur.  
  
```  
// default constructor  
piecewise_constant_distribution();
 
// constructs using a range of intervals, [firstI, lastI), with  
// matching weights starting at firstW  
template <class InputIteratorI, class InputIteratorW>  
piecewise_constant_distribution(InputIteratorI firstI, InputIteratorI lastI, InputIteratorW firstW);
 
// constructs using an initializer list for range of intervals,  
// with weights generated by function weightfunc  
template <class UnaryOperation>  
piecewise_constant_distribution(initializer_list<RealType>  
intervals, UnaryOperation weightfunc);
 
// constructs using an initializer list for range of count intervals,  
// distributed uniformly over [xmin,xmax] with weights generated by function weightfunc  
template <class UnaryOperation>  
piecewise_constant_distribution(size_t count, RealType xmin, RealType xmax, UnaryOperation weightfunc);
 
// constructs from an existing param_type structure  
explicit piecewise_constant_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parametreler  
 `firstI`  
 Giriş yineleyici dağıtım aralıktaki ilk öğesinin.  
  
 `lastI`  
 Giriş yineleyici dağıtım aralıktaki son öğesi.  
  
 `firstW`  
 Giriş yineleyici ağırlıkları aralıktaki ilk öğesinin.  
  
 `intervals`  
 Bir [initializer_list](../cpp/initializers.md) dağıtım aralıkları ile.  
  
 `count`  
 Dağıtım aralığında öğe sayısı.  
  
 `xmin`  
 Dağıtım aralığına en düşük değer.  
  
 `xmax`  
 Dağıtım aralığına en yüksek değer. Büyük olmalı `xmin`.  
  
 `weightfunc`  
 Dağıtım için olasılık işlevi temsil eden nesne. Parametre ve dönüş değeri dönüştürülebilir `double`.  
  
 `parm`  
 Dağıtım oluşturmak için kullanılan parametre yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
Bir aralık, 0 ve 1, 1 ile olasılık yoğunluğu olmasını gibi varsayılan oluşturucu saklı parametreleri ayarlar.  
  
Yineleyici aralığı Oluşturucusu  
```  
template <class InputIteratorI, class InputIteratorW>  
piecewise_constant_distribution(InputIteratorI firstI, InputIteratorI lastI,  
    InputIteratorW firstW);
```  
  
yineleyiciler gelen itnervals dağıtım nesnesiyle dizisi oluşturur [ `firstI`, `lastI`) ve eşleşen bir ağırlık dizisi başlayarak `firstW`.  
  
Başlatıcı listesi Oluşturucusu  
```  
template <class UnaryOperation>  
piecewise_constant_distribution(initializer_list<result_type>  
intervals,   
    UnaryOperation weightfunc);
```  
  
ıntializer listeden aralıkları dağıtım nesnesiyle yapıları `intervals` ve ağırlıklarını işlevinden oluşturulan `weightfunc`.  
  
Tanımlanan Oluşturucusu  
```  
template <class UnaryOperation>  
piecewise_constant_distribution(size_t count, result_type xmin, result_type xmax,  
    UnaryOperation weightfunc);
```  
  
bir dağıtım nesnesiyle oluşturur `count` aralıkları dağıtılmış hep üzerinde [ `xmin,xmax`], her aralığı atama ağırlık verir göre işlevi `weightfunc`, ve `weightfunc` bir parametre kabul etmeniz ve satır başı olması gerekir değeri, her ikisi de hangi dönüştürülebilir, `double`. **Önkoşul:** `xmin < xmax`  
  
Tanımlanan Oluşturucusu  
```  
explicit piecewise_constant_distribution(const param_type& parm);
```  
  
dağıtım nesnesi kullanılarak yapıları `parm` depolanan parametrenin yapısı olarak.  
  
##  <a name="param_type"></a>  piecewise_constant_distribution::param_type  
Dağıtım tüm parametreleri depolar.  
  
```    
struct param_type {  
   typedef piecewise_constant_distribution<result_type> distribution_type;  
   param_type();
   template <class IterI, class IterW>  
   param_type(IterI firstI, IterI lastI, IterW firstW);
   template <class UnaryOperation>  
   param_type(size_t count, result_type xmin, result_type xmax, UnaryOperation weightfunc);
   std::vector<result_type> densities() const;
   std::vector<result_type> intervals() const;
     
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>Parametreler  
Oluşturucu parametreleri için bkz: [piecewise_constant_distribution](#piecewise_constant_distribution).  
  
### <a name="remarks"></a>Açıklamalar  
 **Önkoşul:** `xmin < xmax`  
  
Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[\<rastgele >](../standard-library/random.md)   
[piecewise_linear_distribution](../standard-library/piecewise-linear-distribution-class.md)


