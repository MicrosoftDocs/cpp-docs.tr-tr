---
title: "random_device sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- random/std::random_device
- random/std::random_device::min
- random/std::random_device::max
- random/std::random_device::entropy
- random/std::random_device::operator()
dev_langs: C++
helpviewer_keywords:
- std::random_device [C++]
- std::random_device [C++], min
- std::random_device [C++], max
- std::random_device [C++], entropy
- std::random_device [C++], entropy
ms.assetid: 4393d515-0cb6-4e0d-a2ba-c780f05dc1bf
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e12c446ec97bc4cf9d2f2caff642b0ed6fb210d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="randomdevice-class"></a>random_device Sınıfı
Dış bir aygıttan rastgele bir sıra oluşturur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class random_device {  
public:  
   typedef unsigned int result_type;  
   
   // constructor 
   explicit random_device(const std::string& token = "");
   
   // properties 
   static result_type min();
   static result_type max();
   double entropy() const;
   
   // generate 
   result_type operator()();

   // no-copy functions 
   random_device(const random_device&) = delete;  
   void operator=(const random_device&) = delete;  
   };  
```  

## <a name="members"></a>Üyeler  
  
|||  
|-|-|  
|[random_device](#random_device)|[Dağınık](#entropy)|  
|[random_device::operator()](#op_call)||  
  
## <a name="remarks"></a>Açıklamalar  
Sınıfı rastgele sayı kaynağı açıklar ve izin verilen ancak belirleyici olmayan veya şifreleme açısından güvenli olması için ISO C++ Standart tarafından gerekli değildir. Visual Studio'da üretilen değerler belirleyici olmayan ve şifreleme yoluyla güvenli, uygulama ancak çalışan motorları ve altyapısı bağdaştırıcıları oluşturulan oluşturucuları daha yavaş (gibi [mersenne_twister_engine](../standard-library/mersenne-twister-engine-class.md), yüksek kaliteli ve hızlı motoru tercih çoğu uygulamalar için).  
  
`random_device`sonuçları hep kapalı aralığında dağıtılmış [ `0, 2` <sup>32</sup>).  
  
`random_device`Engelleyici olmayan bir çağrıda neden garanti edilmez.  
  
Genellikle, `random_device` altyapıları veya altyapısı bağdaştırıcıları ile oluşturulmuş diğer üreticiler oluşturmak için kullanılır. Daha fazla bilgi için bkz: [ \<rastgele >](../standard-library/random.md).  
  
## <a name="example"></a>Örnek  
Aşağıdaki kod bu sınıf ve örnek sonuçları temel işlevselliğini göstermektedir. Belirleyici olmayan yapısı nedeniyle `random_device`, gösterilen rastgele değerler **çıkış** bölüm sonuçlarınızı eşleşmez. Normal ve beklenen budur.  
  
```cpp  
// random_device_engine.cpp   
// cl.exe /W4 /nologo /EHsc /MTd   
#include <random>   
#include <iostream>   
using namespace std;  
  
int main()   
{   
    random_device gen;   
  
    cout << "entropy == " << gen.entropy() << endl;   
    cout << "min == " << gen.min() << endl;   
    cout << "max == " << gen.max() << endl;   
  
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
    cout << "a random value == " << gen() << endl;   
}  
```  
  
```Output  
entropy == 32
min == 0
max == 4294967295
a random value == 2378414971
a random value == 3633694716
a random value == 213725214
```  
  
Bu, simplistic ve genel kullanım örneğinin bu oluşturucunun temsilcisi örneğidir. Daha fazla temsili bir kod örneği için bkz [ \<rastgele >](../standard-library/random.md).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<rastgele >  
  
 **Namespace:** std  
  
##  <a name="random_device"></a>random_device::random_device  
Oluşturucu oluşturur.  
  
```  
random_device(const std::string& = "");
```  
  
### <a name="remarks"></a>Açıklamalar  
Oluşturucu üreteci, dize parametresi yoksayılıyor gerektiğinde başlatır. Türetilen uygulama tanımlı bir türde bir değer oluşturur [özel durum](../standard-library/exception-class.md) varsa `random_device` başlatılamadı.  
  
##  <a name="entropy"></a>random_device::Entropy  
Kaynak rastgele tahmin eder.  
  
```  
double entropy() const noexcept;  
```  
  
### <a name="remarks"></a>Açıklamalar  
Üye işlevini kaynak rastgele tahmini bit cinsinden ölçülen döndürür.  
  
##  <a name="op_call"></a>random_device::operator()  
Rastgele bir değeri döndürür.  
  
```  
result_type operator()();
```  
  
### <a name="remarks"></a>Açıklamalar  
Kapalı zaman aralığını hep dağıtılmış değerleri döndürür [ `min, max`] üye işlevleri tarafından belirlenen `min()` ve `max()`. Türetilen uygulama tanımlı bir türde bir değer oluşturur [özel durum](../standard-library/exception-class.md) rastgele bir sayı alınamadığından durumunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[\<rastgele >](../standard-library/random.md)

