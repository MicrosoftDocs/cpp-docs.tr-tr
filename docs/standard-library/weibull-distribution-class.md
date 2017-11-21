---
title: "weibull_distribution sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::weibull_distribution
- random/std::weibull_distribution::reset
- random/std::weibull_distribution::a
- random/std::weibull_distribution::b
- random/std::weibull_distribution::param
- random/std::weibull_distribution::min
- random/std::weibull_distribution::max
- random/std::weibull_distribution::operator()
- random/std::weibull_distribution::param_type
- random/std::weibull_distribution::param_type::a
- random/std::weibull_distribution::param_type::b
- random/std::weibull_distribution::param_type::operator==
- random/std::weibull_distribution::param_type::operator!=
dev_langs: C++
helpviewer_keywords:
- std::weibull_distribution [C++]
- std::weibull_distribution [C++], reset
- std::weibull_distribution [C++], a
- std::weibull_distribution [C++], b
- std::weibull_distribution [C++], param
- std::weibull_distribution [C++], min
- std::weibull_distribution [C++], max
- std::weibull_distribution [C++], param_type
- std::weibull_distribution [C++], param_type
ms.assetid: f20b49d3-1b9a-41af-8db4-baf800eaa02b
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 319a00cfd69ef2e83da5744606b9c4c10d4f9942
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="weibulldistribution-class"></a>weibull_distribution Sınıfı
WEIBULL dağıtım oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
```  
class weibull_distribution  
   {  
   public: 
    // types  
   typedef RealType result_type;  
   struct param_type; 

    // constructor and reset functions  
   explicit weibull_distribution(result_type a = 1.0, result_type b = 1.0);
   explicit weibull_distribution(const param_type& parm);
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
#### <a name="parameters"></a>Parametreler  
*RealType*  
Kayan noktalı bir sonuç türü, varsayılan olarak `double`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="remarks"></a>Açıklamalar  
Kullanıcı tanımlı bir kayan nokta değerleri üreten bir dağıtım şablonu sınıf tanımlar türü veya türü `double` göre WEIBULL dağıtım sağlanırsa, dağıtılmış. Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri.  
  
||||  
|-|-|-|  
|[weibull_distribution](#weibull_distribution)|`weibull_distribution::a`|`weibull_distribution::param`|  
|`weibull_distribution::operator()`|`weibull_distribution::b`|[param_type](#param_type)|  
  
Özellik işlevleri `a()` ve `b()` ilgili değerlerine depolanan dağıtım parametreleri için iade *bir* ve *b*.  
  
Özellik üyesi `param()` ayarlar veya döndürür `param_type` depolanan dağıtım parametresi paket.  

`min()` Ve `max()` üye işlevleri en küçük olası sonuç ve olası en büyük sonuç sırasıyla döndürür.  
  
`reset()` Üye işlevi herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerlere bağlı değildir.  
  
`operator()` Üye işlevleri URNG motoru, geçerli parametre paket veya belirtilen parametre paket göre sonraki oluşturulan değeri döndürür.
  
Dağıtım sınıflar ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).  
  
Wolfram MathWorld makaleyi WEIBULL dağıtımı hakkında ayrıntılı bilgi için bkz [WEIBULL dağıtım](http://go.microsoft.com/fwlink/LinkId=401115).  
  
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
  
    std::weibull_distribution<> distr(a, b);  
  
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
    std::cout << "Enter a floating point value for the 'a' distribution parameter (must be greater than zero): ";  
    std::cin >> a_dist;  
    std::cout << "Enter a floating point value for the 'b' distribution parameter (must be greater than zero): ";  
    std::cin >> b_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(a_dist, b_dist, samples);  
}  
  
```  
  
## <a name="output"></a>Çıkış  
 İlk çalıştırın:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter (must be greater than zero): 1  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 1  
Enter an integer value for the sample count: 10  
 
min() == 0  
max() == 1.79769e+308  
a() == 1.0000000000  
b() == 1.0000000000  
Distribution for 10 samples:  
    1: 0.0936880533  
    2: 0.1225944894  
    3: 0.6443593183  
    4: 0.6551171649  
    5: 0.7313457551  
    6: 0.7313557977  
    7: 0.7590097389  
    8: 1.4466885214  
    9: 1.6434088411  
    10: 2.1201210996  
```  
  
 İkinci çalıştırın:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.  
Enter a floating point value for the 'a' distribution parameter (must be greater than zero): .5  
Enter a floating point value for the 'b' distribution parameter (must be greater than zero): 5.5  
Enter an integer value for the sample count: 10  
 
min() == 0  
max() == 1.79769e+308  
a() == 0.5000000000  
b() == 5.5000000000  
Distribution for 10 samples:  
    1: 0.0482759823  
    2: 0.0826617486  
    3: 2.2835941207  
    4: 2.3604817485  
    5: 2.9417663742  
    6: 2.9418471657  
    7: 3.1685268104  
    8: 11.5109922290  
    9: 14.8543594043  
    10: 24.7220241239  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
##  <a name="weibull_distribution"></a>weibull_distribution::weibull_distribution  
  
```  
explicit weibull_distribution(result_type a = 1.0, result_type b = 1.0);
explicit weibull_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parametreler  
*bir*  
`a` Dağıtım parametresi.  
  
*b*  
`b` Dağıtım parametresi.  
  
*parametre*  
`param_type` Dağıtım oluşturmak için kullanılan yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **Önkoşul:** `0.0 < a` ve`0.0 < b`  
  
 İlk Oluşturucusu bir nesne oluşturur, depolanan `a` değeri tutan değeri *bir* ve, depolanan `b` değeri tutan değeri *b*.  
  
 İkinci oluşturucu saklı parametreleri başlatılan bir nesne oluşturur *parametresi*. Elde edilir ve geçerli parametrelerinin varolan bir dağıtımına aranarak `param()` üye işlevi.  
  
##  <a name="param_type"></a>weibull_distribution::param_type  
 Dağıtım parametreleri depolar.  
```  
struct param_type {  
   typedef weibull_distribution<result_type> distribution_type;  
   param_type(result_type a = 1.0, result_type b = 1.0);
   result_type a() const;
   result_type b() const;

   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```
### <a name="parameters"></a>Parametreler  
*bir*  
`a` Dağıtım parametresi.  
  
*b*  
`b` Dağıtım parametresi.  
  
*sağ*  
`param_type` İçin karşılaştırılacak nesne.  
  
### <a name="remarks"></a>Açıklamalar  
**Önkoşul:** `0.0 < a` ve`0.0 < b`  
  
Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<rastgele >](../standard-library/random.md)



