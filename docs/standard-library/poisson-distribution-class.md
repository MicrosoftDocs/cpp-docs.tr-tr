---
title: "poisson_distribution sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::poisson_distribution
- random/std::poisson_distribution::reset
- random/std::poisson_distribution::mean
- random/std::poisson_distribution::param
- random/std::poisson_distribution::min
- random/std::poisson_distribution::max
- random/std::poisson_distribution::operator()
- random/std::poisson_distribution::param_type
- random/std::poisson_distribution::param_type::mean
- random/std::poisson_distribution::param_type::operator==
- random/std::poisson_distribution::param_type::operator!=
dev_langs: C++
helpviewer_keywords:
- std::poisson_distribution [C++]
- std::poisson_distribution [C++], reset
- std::poisson_distribution [C++], mean
- std::poisson_distribution [C++], param
- std::poisson_distribution [C++], min
- std::poisson_distribution [C++], max
- std::poisson_distribution [C++], param_type
- std::poisson_distribution [C++], param_type
ms.assetid: 09614281-349a-45f7-8e95-c0196be0a937
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e9ebeb453aefee8310e45779f1fd60c7bd207771
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="poissondistribution-class"></a>poisson_distribution Sınıfı
Poisson dağılımı oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template<class IntType = int>
class poisson_distribution  
   {  
public:  
   // types  
   typedef IntType result_type;  
   struct param_type;  
   
   // constructors and reset functions  
   explicit poisson_distribution(double mean = 1.0);
   explicit poisson_distribution(const param_type& parm);
   void reset();
   
   // generating functions  
   template <class URNG>  
   result_type operator()(URNG& gen);
   template <class URNG>  
   result_type operator()(URNG& gen, const param_type& parm);
   
   // property functions  
   double mean() const;
   param_type param() const;
   void param(const param_type& parm);
   result_type min() const;
   result_type max() const;
   };  
``` 
  
#### <a name="parameters"></a>Parametreler  
*İnt'i*  
Tamsayı sonuç türü varsayılan olarak `int`. Olası türleri için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="remarks"></a>Açıklamalar  
Poisson dağılımı ile kullanıcı tarafından belirtilen tam sayı türü değerleri üreten bir dağıtım şablonu sınıfı tanımlar. Aşağıdaki tabloda ilgili makalelerin bağlantısı için tek tek üyeleri.  
  
||||  
|-|-|-|  
|[poisson_distribution](#poisson_distribution)|`poisson_distribution::mean`|`poisson_distribution::param`|  
|`poisson_distribution::operator()`||[param_type](#param_type)|  
  
Özellik işlevi `mean()` depolanan dağıtım parametresinin değeri döndürür *anlamına*.  
  
Özellik üyesi `param()` ayarlar veya döndürür `param_type` depolanan dağıtım parametresi paket.  

`min()` Ve `max()` üye işlevleri en küçük olası sonuç ve olası en büyük sonuç sırasıyla döndürür.  
  
`reset()` Üye işlevi herhangi bir önbelleğe alınan değeri atar böylece sonraki çağrı sonucunu `operator()` çağırmadan önce altyapısından alınan değerlere bağlı değildir.  
  
`operator()` Üye işlevleri URNG motoru, geçerli parametre paket veya belirtilen parametre paket göre sonraki oluşturulan değeri döndürür.
  
Dağıtım sınıflar ve üyeleri hakkında daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).  
  
Poisson dağılımı hakkında ayrıntılı bilgi için Wolfram MathWorld makalesine bakın [dağılımı](http://go.microsoft.com/fwlink/p/?linkid=401112).  
  
## <a name="example"></a>Örnek  
  
```cpp  
// compile with: /EHsc /W4  
#include <random>   
#include <iostream>  
#include <iomanip>  
#include <string>  
#include <map>  
  
void test(const double p, const int s) {  
  
    // uncomment to use a non-deterministic generator  
    //    std::random_device gen;  
    std::mt19937 gen(1701);  
  
    std::poisson_distribution<> distr(p);  
  
    std::cout << std::endl;  
    std::cout << "min() == " << distr.min() << std::endl;  
    std::cout << "max() == " << distr.max() << std::endl;  
    std::cout << "p() == " << std::fixed << std::setw(11) << std::setprecision(10) << distr.mean() << std::endl;  
  
    // generate the distribution as a histogram  
    std::map<int, int> histogram;  
    for (int i = 0; i < s; ++i) {  
        ++histogram[distr(gen)];  
    }  
  
    // print results  
    std::cout << "Distribution for " << s << " samples:" << std::endl;  
    for (const auto& elem : histogram) {  
        std::cout << std::setw(5) << elem.first << ' ' << std::string(elem.second, ':') << std::endl;  
    }  
    std::cout << std::endl;  
}  
  
int main()  
{  
    double p_dist = 1.0;  
  
    int samples = 100;  
  
    std::cout << "Use CTRL-Z to bypass data entry and run using default values." << std::endl;  
    std::cout << "Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): ";  
    std::cin >> p_dist;  
    std::cout << "Enter an integer value for the sample count: ";  
    std::cin >> samples;  
  
    test(p_dist, samples);  
}  
  
```  
  
İlk testi:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 1
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 1.0000000000
Distribution for 100 samples:
    0 ::::::::::::::::::::::::::::::
    1 ::::::::::::::::::::::::::::::::::::::
    2 :::::::::::::::::::::::
    3 ::::::::
    5 :  
```  
  
İkinci test edin:  
  
```Output  
Use CTRL-Z to bypass data entry and run using default values.
Enter a floating point value for the 'mean' distribution parameter (must be greater than zero): 10
Enter an integer value for the sample count: 100
min() == 0
max() == 2147483647
p() == 10.0000000000
Distribution for 100 samples:
    3 :
    4 ::
    5 ::
    6 ::::::::
    7 ::::
    8 ::::::::
    9 ::::::::::::::
   10 ::::::::::::
   11 ::::::::::::::::
   12 :::::::::::::::
   13 ::::::::
   14 ::::::
   15 :
   16 ::
   17 :  
```  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
##  <a name="poisson_distribution"></a>poisson_distribution::poisson_distribution  
Dağıtım oluşturur.  
  
```  
explicit poisson_distribution(RealType mean = 1.0);
explicit binomial_distribution(const param_type& parm);
```  
  
### <a name="parameters"></a>Parametreler  
*Ortalama*  
`mean` Dağıtım parametresi.  
  
*parametre*  
Dağıtım oluşturmak için kullanılan parametre yapısı.  
  
### <a name="remarks"></a>Açıklamalar  
 **Önkoşul:**`0.0 < mean`  
  
İlk Oluşturucusu bir nesne oluşturur, depolanan `mean` değeri tutan değeri *anlamına*.  
  
İkinci oluşturucu saklı parametreleri başlatılan bir nesne oluşturur *parametresi*. Elde edilir ve geçerli parametrelerinin varolan bir dağıtımına aranarak `param()` üye işlevi.  
  
##  <a name="param_type"></a>poisson_distribution::param_type  
Dağıtım parametreleri depolar.  
  
```    
struct param_type {  
   typedef poisson_distribution<IntType> distribution_type;  
   param_type(double mean = 1.0);
   double mean() const;
     
   bool operator==(const param_type& right) const;
   bool operator!=(const param_type& right) const;
   };  
```  
  
### <a name="parameters"></a>Parametreler  
Oluşturucu parametreleri için bkz: [poisson_distribution](#poisson_distribution).  
  
### <a name="remarks"></a>Açıklamalar  
 **Önkoşul:**`0.0 < mean`  
  
Bu yapı dağıtım 's sınıfı oluşturucuya oluşturmada, en çok geçirilebilir `param()` var olan bir dağıtım ve için saklı parametrelerini ayarlamak için üye işlevi `operator()` saklı parametreleri yerine kullanılacak.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<rastgele >](../standard-library/random.md)

