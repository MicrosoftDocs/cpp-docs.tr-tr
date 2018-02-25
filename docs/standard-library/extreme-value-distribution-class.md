---
title: "extreme_value_distribution sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- random/std::extreme_value_distribution
- random/std::extreme_value_distribution::reset
- random/std::extreme_value_distribution::a
- random/std::extreme_value_distribution::b
- random/std::extreme_value_distribution::param
- random/std::extreme_value_distribution::min
- random/std::extreme_value_distribution::max
- random/std::extreme_value_distribution::operator()
- random/std::extreme_value_distribution::param_type
- random/std::extreme_value_distribution::param_type::a
- random/std::extreme_value_distribution::param_type::b
- random/std::extreme_value_distribution::param_type::operator==
- random/std::extreme_value_distribution::param_type::operator!=
dev_langs:
- C++
helpviewer_keywords:
- std::extreme_value_distribution [C++]
- std::extreme_value_distribution [C++], reset
- std::extreme_value_distribution [C++], a
- std::extreme_value_distribution [C++], b
- std::extreme_value_distribution [C++], param
- std::extreme_value_distribution [C++], min
- std::extreme_value_distribution [C++], max
- std::extreme_value_distribution [C++], param_type
- std::extreme_value_distribution [C++], param_type
ms.assetid: a0cd8370-0a54-4e26-9388-8b9678fb57da
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 93bf21b8dd17ddff4bf3de56417c85c6b415cb5e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="extremevaluedistribution-class"></a>extreme_value_distribution Sınıfı
Extreme değer dağıtımı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
```  
template<class RealType = double>
class extreme_value_distribution  
   {  
public:  
   // types  
   typedef RealType result_type;  
   struct param_type;  
   
   // constructor and reset functions  
   explicit extreme_value_distribution(result_type a = 0.0, result_type b = 1.0);
   explicit extreme_value_distribution(const param_type& parm);
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
*RealType*  
Kayan noktalı bir sonuç türü, varsayılan olarak `double`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).  
  
*URNG* rastgele sayı oluşturucu altyapısı. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).
  
## <a name="remarks"></a>Açıklamalar  
 Kayan nokta değerleri, bir kullanıcı tarafından belirtilen üreten bir dağıtım şablonu sınıf tanımlar türü veya türü `double` sağlanırsa, aşırı değeri dağıtım göre dağıtılmış. Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri.  
  
||||  
|-|-|-|  
|[extreme_value_distribution](#extreme_value_distribution)|`extreme_value_distribution::a`|`extreme_value_distribution::param`|  
|`extreme_value_distribution::operator()`|`extreme_value_distribution::b`|[param_type](#param_type)|  
  
 Özellik işlevleri `a()` ve `b()` ilgili değerlerine depolanan dağıtım parametreleri için iade `a` ve `b`.  
  
 Dağıtım sınıflar ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).  
  
 Extreme değer dağıtımı hakkında ayrıntılı bilgi için Wolfram MathWorld makalesine bakın [aşırı değeri dağıtım](http://go.microsoft.com/fwlink/p/?linkid=401110).  
  
## <a name="example"></a>Örnek  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double a, const double b, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
  
    std::mt19937 gen(1701);  
  
    std::extreme_value_distribution<> distr(a, b);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "a() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.a() << std::endl;  
    std::cout << "b() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.b() << std::endl;  
  
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
            << std::setw(14) << std::setprecision(10) << elem.first << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double a_dist = 0.0;  
    double b_dist = 1;  
  
    int samples = 10;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the \'a\' distribution parameter: ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the \'b\' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
```  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter: 0  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == -1.79769e+308  
max() == 1.79769e+308  
a() == 0.0000000000  
b() == 1.0000000000  
Distribution for 10 samples:  
    1: -0.8813940331  
    2: -0.7698972281  
    3: 0.2951258007  
    4: 0.3110450734  
    5: 0.4210546820  
    6: 0.4210688771  
    7: 0.4598857960  
    8: 1.3155194200  
    9: 1.5379170046  
    10: 2.0568757061  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
##  <a name="extreme_value_distribution"></a>  extreme_value_distribution::extreme_value_distribution  
 Dağıtım oluşturur.  
  
```  
explicit extreme_value_distribution(result_type a_value = 0.0, result_type b_value = 1.0);
explicit extreme_value_distribution(const param_type& parm);  
```  
  
### <a name="parameters"></a>Parametreler  
*a_value*  
 `a` Dağıtım parametresi.  
  
*b_value*  
 `b` Dağıtım parametresi.  
  
*parametre*  
 `param_type` Dağıtım oluşturmak için kullanılan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **Önkoşul:** `0.0 < b`  
  
 İlk Oluşturucusu bir nesne oluşturur, depolanan `a` değeri tutan değeri *a_value* ve, depolanan `b` değeri tutan değeri *b_value*.  
  
 İkinci oluşturucu saklı parametreleri başlatılan bir nesne oluşturur *parametresi*. Elde edilir ve geçerli parametrelerinin varolan bir dağıtımına aranarak `param()` üye işlevi.  
  
##  <a name="param_type"></a>  extreme_value_distribution::param_type  
Dağıtım parametreleri depolar.  
  
```cpp  
struct param_type {  
   typedef extreme_value_distribution<result_type> distribution_type;  
   param_type(result_type a_value = 0.0, result_type b_value = 1.0);
   result_type a() const;
   result_type b() const;
    
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>Parametreler  
*a_value*  
 `a` Dağıtım parametresi.  
  
*b_value*  
 `b` Dağıtım parametresi.  
  
*Sağ*  
 `param_type` İçin karşılaştırılacak nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 **Önkoşul:** `0.0 < b`  
  
 Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<rastgele >](../standard-library/random.md)



