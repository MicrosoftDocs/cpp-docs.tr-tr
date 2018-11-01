---
title: '&lt;karmaşık&gt;'
ms.date: 11/04/2016
f1_keywords:
- <complex>
- std::<complex>
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
ms.openlocfilehash: afcdb1246d9c02f83dbc8708326d10e802ad2779
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50525873"
---
# <a name="ltcomplexgt"></a>&lt;karmaşık&gt;

Kapsayıcı Şablon sınıfı tanımlar `complex` ve kendi destek şablonları.

## <a name="syntax"></a>Sözdizimi

```cpp
#include <complex>
```

## <a name="remarks"></a>Açıklamalar

Gerçek sayıları sıralı bir çift olan bir karmaşık sayıdır. Tamamen geometrik bağlamında, karmaşık düzlemi gerçek, iki boyutlu Düzlemi ' dir. Gerçek düzleminde ayırt özel kalitelerini karmaşık düzlemin, ek bir cebirsel yapısı nedeniyle yaşıyorsanız. Bu cebirsel yapısı iki temel işlemler bulunur:

- Ek olarak tanımlanır (*bir*, *b*) + (*c*, *d*) = (*bir* + *c* , *b* + *d*)

- Tanımlanan çarpma (*bir*, *b*) \* (*c*, *d*) = (*ac*  -  *bd*, *ad* + *bc*)

Karmaşık toplama ve karmaşık çarpma işlemleri karmaşık sayılar kümesiyle standart cebirsel anlamda bir alanda şunlardır:

- Toplama ve çarpma işlemleri yer değiştirebilirlik ve ilişkilendirilebilir ve tam olarak gerçek toplama ve gerçek sayılar alan üzerinde çarpımı ile yaptığı gibi çarpma toplama üzerinde dağıtır.

- Karmaşık sayıyı (0, 0) olan eklenebilir kimlik ve (1, 0) çarpma kimliğidir.

- Karmaşık bir sayıyı için eklenebilir ters (*bir*, *b*) olduğunu (-*bir*, -*b*) ve tüm karmaşık sayılar için multiplicative ters dışında (0, 0) olan

   (*bir*/ (*bir*<sup>2</sup> + *b*<sup>2</sup>), -*b*/ (*bir*<sup>2</sup> + *b*<sup>2</sup>))

Karmaşık bir sayıyı temsil eden tarafından *z* = (*bir*, *b*) biçiminde *z* = *bir*  +  *BI*burada *miyim*<sup>2</sup> Cebir gerçek sayılar kümesinin karmaşık sayılar kümesini ve bileşenleri için uygulanabilir için -1, kuralları =. Örneğin:

   (1 + 2*miyim*) \* (2 + 3*miyim*) = 1 \* (2 + 3*miyim*) + 2*miyim* \* (2 + 3*i*) = (2 + 3*miyim*) + (4*miyim* + 6*miyim*<sup>2</sup>) (2-6) + (3 ve 4) =*miyim* = -4 + 7*ediyorum*

Karmaşık sayılar alan sistemidir, ancak sıralı bir alan değil. Olduğundan gerçek sayıları ve onun alt kümeler, alan için gerçek sayıya oldukları gibi karmaşık sayılar inequalities uygulanamaz hiçbir karmaşık numaralarını sıralama yoktur.

Karmaşık bir sayıyı temsil eden üç ortak biçimleri vardır *z*:

- Kartezyen: *z* = *bir* + *BI*

- Kutupsal: *z* = *r* (cos *p* + *miyim* sin *p*)

- Üstsel: *z* = *r* \* *e*<sup>*IP*</sup>

Bu standart karmaşık bir sayıyı temsil eden içinde kullanılan terimler için şu şekilde adlandırılır:

- Gerçek Kartezyen bileşeni veya gerçek bir parçası *bir*.

- Sanal bir parçası ve sanal Kartezyen bileşeni *b*.

- Modulus veya karmaşık bir sayının mutlak değerini *r*.

- Bağımsız değişken veya aşamayı açı *p* radyan cinsinden açı.

Aksi belirtilmediği sürece, birden çok değer döndüren işlevler - π'dan büyük ve küçük bir asıl kendi bir bağımsız değişken değerini döndürmek için gerekli olan daha eşit + π veya tek değerli saklamak için. Tüm açıların radyan cinsinden ifade edilmelidir burada 2π radyan (360 derece) bir daire.

### <a name="functions"></a>İşlevler

|İşlev|Açıklama|
|-|-|
|[Abs](../standard-library/complex-functions.md#abs)|Karmaşık bir sayıyı modüllerini hesaplar.|
|[bağımsız değişken](../standard-library/complex-functions.md#arg)|Bağımsız değişken, bir karmaşık numarasından ayıklar.|
|[conj](../standard-library/complex-functions.md#conj)|Karmaşık bir sayının karmaşık çiftini döndürür.|
|[cos](../standard-library/complex-functions.md#cos)|Karmaşık bir sayının kosinüsünü döndürür.|
|[COSH](../standard-library/complex-functions.md#cosh)|Karmaşık bir sayının hiperbolik kosinüsünü döndürür.|
|[exp](../standard-library/complex-functions.md#exp)|Karmaşık bir sayıyı üstel işlevi döndürür.|
|[imag](../standard-library/complex-functions.md#imag)|Karmaşık bir sayıyı sanal bileşeninin ayıklar.|
|[log](../standard-library/complex-functions.md#log)|Karmaşık bir sayının doğal logaritmasını döndürür.|
|[log10](../standard-library/complex-functions.md#log10)|Karmaşık bir sayının 10 tabanındaki logaritmasını döndürür.|
|[Norm](../standard-library/complex-functions.md#norm)|Karmaşık bir sayıyı normalini ayıklar.|
|[Yuvarlak](../standard-library/complex-functions.md#polar)|Belirtilen modül ve bağımsız değişken için karşılık gelen, karmaşık sayıyı Kartezyen biçiminde döndürür.|
|[POW](../standard-library/complex-functions.md#pow)|Başka bir karmaşık sayı değerini karmaşık bir sayıyı bir tabanı oluşturularak elde edilen karmaşık sayıyı değerlendirir.|
|[Gerçek](../standard-library/complex-functions.md#real)|Gerçek ve karmaşık bir sayıyı bileşenini ayıklar.|
|[sin](../standard-library/complex-functions.md#sin)|Karmaşık bir sayının sinüsünü döndürür.|
|[SİNH](../standard-library/complex-functions.md#sinh)|Karmaşık bir sayının hiperbolik sinüsünü döndürür.|
|[sqrt](../standard-library/complex-functions.md#sqrt)|Karmaşık bir sayının karekökünü döndürür.|
|[tan](../standard-library/complex-functions.md#tan)|Karmaşık bir sayının tanjantını döndürür.|
|[TANH](../standard-library/complex-functions.md#tanh)|Karmaşık bir sayının hiperbolik tanjantını döndürür.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](../standard-library/complex-operators.md#op_neq)|İki karmaşık sayılar, biri veya ikisi de arasındaki eşitsizliği sınar reel ve sanal parça türünün bir alt kümesine ait olabilir.|
|[operator *](../standard-library/complex-operators.md#op_star)|İki çarpar karmaşık sayılar, biri veya ikisi de ait alt reel ve sanal parçaları için türü.|
|[operator +](../standard-library/complex-operators.md#op_add)|Alt tür reel ve sanal parçaları için iki karmaşık sayılar, biri veya ikisi de ait ekler.|
|[operator-](../standard-library/complex-operators.md#operator-)|İki çıkarır karmaşık sayılar, biri veya ikisi de ait alt reel ve sanal parçaları için türü.|
|[operator /](../standard-library/complex-operators.md#op_div)|Böler iki karmaşık sayılar, biri veya ikisi de reel ve sanal parça türünün bir alt kümesine ait olabilir.|
|[işleç <\<](../standard-library/complex-operators.md#op_lt_lt)|Karmaşık bir sayıyı ekler çıkış akışına bir şablon işlevi.|
|[operator==](../standard-library/complex-operators.md#op_eq_eq)|İki karmaşık sayılar, biri veya ikisi de arasındaki eşitliği sınar reel ve sanal parça türünün bir alt kümesine ait olabilir.|
|[İşleç >>](../standard-library/complex-operators.md#op_gt_gt)|Karmaşık bir değer girdi akışından ayıklar şablon işlevi.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[karmaşık\<çift >](../standard-library/complex-double.md)|Açıkça özel bir şablon sınıfı nesne, türü hem de sıralı bir çift depolayan bir nesneyi tanımlayan **çift**burada ilk karmaşık bir sayıyı gerçek bölümünü temsil eder ve ikinci sanal bölümü temsil eder.|
|[karmaşık\<kayan noktalı sayı >](../standard-library/complex-float.md)|Açıkça özel bir şablon sınıfı nesne, türü hem de sıralı bir çift depolayan bir nesneyi tanımlayan **float**burada ilk karmaşık bir sayıyı gerçek bölümünü temsil eder ve ikinci sanal bölümü temsil eder.|
|[karmaşık\<uzun çift >](../standard-library/complex-long-double.md)|Açıkça özel bir şablon sınıfı nesne, türü hem de sıralı bir çift depolayan bir nesneyi tanımlayan **uzun çift**burada ilk karmaşık bir sayıyı gerçek bölümünü temsil eder ve ikinci sanal bölümü temsil eder.|
|[karmaşık](../standard-library/complex-class.md)|Şablon sınıfı, karmaşık sayı sistemini temsil eder ve karmaşık aritmetik işlemleri gerçekleştirmek için kullanılan bir nesneyi tanımlar.|

### <a name="literals"></a>Sabit değerler

\<Karmaşık > Üstbilgi aşağıdakileri tanımlar [kullanıcı tanımlı değişmez değerler](../cpp/user-defined-literals-cpp.md) sıfır olan gerçek bölüm ve giriş parametresinin değeri olan sanal parça ile karmaşık bir sayıyı oluşturun.

|||
|-|-|
|`constexpr complex<long double> operator""il(long double d)`<br /><br /> `constexpr complex<long double> operator""il(unsigned long long d)`|döndürür: `complex<long double>{0.0L, static_cast<long double>(d)}`|
|`constexpr complex<double> operator""i(long double d)`<br /><br /> `constexpr complex<double> operator""i(unsigned long long d)`|Döndürür: `complex<double>{0.0, static_cast<double>(d)}`.|
|`constexpr complex<float> operator""if(long double d)`<br /><br /> `constexpr complex<float> operator""if(unsigned long long d)`|Döndürür: `complex<float>{0.0f, static_cast<float>(d)}`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
