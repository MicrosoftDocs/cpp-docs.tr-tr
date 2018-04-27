---
title: '&lt;karmaşık&gt; | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- <complex>
- std::<complex>
dev_langs:
- C++
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 133d969121599e77e74448a0b29b4d8de56cf97d
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltcomplexgt"></a>&lt;karmaşık&gt;

Kapsayıcı Şablon sınıfı tanımlayan **karmaşık** ve destekleyici şablonları.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <complex>
```

## <a name="remarks"></a>Açıklamalar

Gerçek sayılar sıralı bir çiftinden karmaşık sayıdır. Tamamen geometrik bağlamında, karmaşık düzlemi gerçek, iki boyutlu Düzlemi ' dir. Karmaşık düzlemi, gerçek düzlemi ayırt özel niteliklerini kendi ek cebirsel yapısı nedeniyle yaşıyorsanız. Bu cebirsel yapısı iki temel işlemler vardır:

- Ek olarak tanımlanır (*bir*, *b*) + (*c*, *d*) = (*bir* + *c* , *b* + *d*)

- Tanımlanan çarpma (*bir*, *b*) \* (*c*, *d*) = (*ac*  -  *bd*, *ad* + *bc*)

Karmaşık numaralar kümesiyle karmaşık toplama ve karmaşık çarpma işlemleri standart cebirsel algılama alanında şunlardır:

- Toplama ve çarpma işlemleri yer değiştirebilme ve ilişkilendirilebilir ve tam olarak gerçek toplama ve gerçek sayılar alanı çarpma yaptığı gibi ek çarpma dağıtır.

- Karmaşık (0, 0) sayıdır ADDITIVE kimlik ve (1, 0) çarpma kimliğidir.

- Karmaşık sayıyı ADDITIVE ters (*bir*, *b*) olan (-*bir*, -*b*) ve multiplicative ters tüm karmaşık numaralar dışında (0, 0) değil

   (*bir*/ (*bir*<sup>2</sup> + *b*<sup>2</sup>), -*b*/ (*bir*<sup>2</sup> + *b*<sup>2</sup>))

Karmaşık bir sayıyı temsil eden tarafından *z* = (*bir*, *b*) biçiminde *z* = *bir*  +  *BI*, burada *ı*<sup>2</sup> gerçek sayı kümesi cebiri karmaşık sayı kümesi ve bileşenleri için uygulanabilir için = -1, kuralları. Örneğin:

   (1 + 2*i*) \* (2 + 3*i*)  
   = 1 \* (2 + 3*i*) + 2*i* \* (2 + 3*i*)  
   = (2 + 3*i*) + (4*i* + 6*i*<sup>2</sup>)  
   = (2 - 6) + (3 + 4)*i*  
   = -4 + 7*i*

Karmaşık numaralar sistem alanıdır ancak sıralı bir alan değil. Olduğundan gerçek sayılar ve onun alt kümeler, alan için gerçek sayılar için oldukları gibi karmaşık numaralar inequalities uygulanamaz karmaşık numaralarını sıralamaya yoktur.

Karmaşık bir sayıyı temsil eden üç ortak formlar vardır *z*:

- Kartezyen: *z* = *bir* + *BI*

- Kutupsal: *z* = *r* (cos *p* + *ı* sin *p*)

- Üstel: *z* = *r* \* *e*<sup>*IP*</sup>

Karmaşık bir sayının standart işbu Beyanları içinde kullanılan terimler için şu şekilde adlandırılır:

- Gerçek Kartezyen bileşeni ya da gerçek bölüm *bir*.

- Sanal Kartezyen bileşeni ya da sanal bölümü *b*.

- Modulus veya karmaşık bir sayının mutlak değerini *r*.

- Bağımsız değişken veya aşamasında açı *p* radyan cinsinden açı.

Aksi belirtilmediği sürece, birden fazla değer döndüren işlevler - π'dan büyük ve küçük kendi bağımsız değişkenler için asıl bir değer döndürmesi için gerekli olan daha veya eşit π tek değerli kalmalarını için +. Tüm açıları radyan cinsinden ifade edilen gerekir bir daire içinde 2π radyan (360 derece) olduğu.

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[Abs](../standard-library/complex-functions.md#abs)|Karmaşık bir sayının modulus hesaplar.|
|[Arg](../standard-library/complex-functions.md#arg)|Bağımsız değişkeni bir karmaşık numarasından ayıklar.|
|[conj](../standard-library/complex-functions.md#conj)|Karmaşık bir sayının karmaşık çiftini döndürür.|
|[cos](../standard-library/complex-functions.md#cos)|Karmaşık bir sayının kosinüsünü döndürür.|
|[COSH](../standard-library/complex-functions.md#cosh)|Karmaşık bir sayının hiperbolik kosinüsünü döndürür.|
|[exp](../standard-library/complex-functions.md#exp)|Karmaşık bir sayının üstel işlevi döndürür.|
|[imag](../standard-library/complex-functions.md#imag)|Karmaşık bir sayının sanal bileşeni ayıklar.|
|[log](../standard-library/complex-functions.md#log)|Karmaşık bir sayının doğal logaritmasını döndürür.|
|[log10](../standard-library/complex-functions.md#log10)|Karmaşık bir sayının 10 tabanında logaritmasını döndürür.|
|[Norm](../standard-library/complex-functions.md#norm)|Karmaşık bir sayının norm ayıklar.|
|[Kutupsal](../standard-library/complex-functions.md#polar)|Belirtilen modül ve bağımsız değişken için karşılık gelen, karmaşık sayı Kartezyen biçiminde döndürür.|
|[POW](../standard-library/complex-functions.md#pow)|Karmaşık sayıyı diğer bir karmaşık sayının kuvvetine bir tabanı yükselterek elde karmaşık sayı değerlendirir.|
|[Gerçek](../standard-library/complex-functions.md#real)|Karmaşık bir sayının gerçek bileşen ayıklar.|
|[sin](../standard-library/complex-functions.md#sin)|Karmaşık bir sayının sinüsünü döndürür.|
|[SİNH](../standard-library/complex-functions.md#sinh)|Karmaşık bir sayının hiperbolik sinüsünü döndürür.|
|[sqrt](../standard-library/complex-functions.md#sqrt)|Karmaşık bir sayının kare kökünü döndürür.|
|[tan](../standard-library/complex-functions.md#tan)|Karmaşık bir sayının tanjantını döndürür.|
|[TANH](../standard-library/complex-functions.md#tanh)|Karmaşık bir sayının hiperbolik tanjantını döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/complex-operators.md#op_neq)|Testleri eşitsizlik açısından iki karmaşık numaralar, biri veya her ikisi de arasındaki bir tür gerçek ve sanal bölümleri için alt ait olabilir.|
|[işleç *](../standard-library/complex-operators.md#op_star)|İki çarpar karmaşık numaralar, biri veya her ikisi de ait alt gerçek ve sanal bölümleri için türü.|
|[operator +](../standard-library/complex-operators.md#op_add)|İki karmaşık numaralar, biri veya her ikisi de alt gerçek ve sanal bölümleri için türü ait ekler.|
|[operator-](../standard-library/complex-operators.md#operator-)|İki çıkarır karmaşık numaralar, biri veya her ikisi de ait alt gerçek ve sanal bölümleri için türü.|
|[operator /](../standard-library/complex-operators.md#op_div)|Böler iki karmaşık numaralar, biri veya her ikisi de alt gerçek ve sanal bölümleri için türü ait.|
|[operator <\<](../standard-library/complex-operators.md#op_lt_lt)|Çıkış akışı bir karmaşık numara ekler şablon işlevi.|
|[operator==](../standard-library/complex-operators.md#op_eq_eq)|İki karmaşık numaralar, biri veya her ikisi de arasında eşitlik için test türü gerçek ve sanal bölümleri için alt ait olabilir.|
|[İşleç >>](../standard-library/complex-operators.md#op_gt_gt)|Giriş akışından karmaşık değer ayıklar şablon işlevi.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[karmaşık\<çift >](../standard-library/complex-double.md)|Nesne, türü hem de sıralı bir çifti depolayan bir nesne açıkça özelleşmiş şablon sınıf tanımlar **çift**burada ilk karmaşık bir sayının gerçek bölümünü temsil eder ve ikinci sanal bölümünü temsil eder.|
|[karmaşık\<float >](../standard-library/complex-float.md)|Nesne, türü hem de sıralı bir çifti depolayan bir nesne açıkça özelleşmiş şablon sınıf tanımlar **float**burada ilk karmaşık bir sayının gerçek bölümünü temsil eder ve ikinci sanal bölümünü temsil eder.|
|[karmaşık\<uzun çift >](../standard-library/complex-long-double.md)|Nesne, türü hem de sıralı bir çifti depolayan bir nesne açıkça özelleşmiş şablon sınıf tanımlar **uzun çift**burada ilk karmaşık bir sayının gerçek bölümünü temsil eder ve ikinci sanal bölümünü temsil eder.|
|[karmaşık](../standard-library/complex-class.md)|Şablon sınıfı karmaşık sayı sistemini temsil eder ve karmaşık aritmetik işlemler gerçekleştirmek için kullanılan nesneyi tanımlar.|

### <a name="literals"></a>Sabit değerler

\<Karmaşık > Üstbilgi tanımlar aşağıdaki [kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md) sıfır olan gerçek bölüm ve giriş parametresinin değeri olan sanal bölümü ile karmaşık bir sayının oluşturun.

|||
|-|-|
|`constexpr complex<long double> operator""il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|döndürür: `complex<long double>{0.0L, static_cast<long double>(d)}`|
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|Döndürür: `complex<double>{0.0, static_cast<double>(d)}`.|
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|Döndürür: `complex<float>{0.0f, static_cast<float>(d)}`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
