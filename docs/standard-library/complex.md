---
title: '&lt;complex &gt;'
ms.date: 11/04/2016
f1_keywords:
- <complex>
- std::<complex>
helpviewer_keywords:
- complex header
ms.assetid: 5e728995-3059-496a-9ce9-61d1bfbe4f2b
ms.openlocfilehash: 071e9369cdd0469d8ddc1c6649a3801732d8e23f
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72688214"
---
# <a name="ltcomplexgt"></a>&lt;complex &gt;

Kapsayıcı sınıfı şablonu `complex` ve destekleyici şablonlarını tanımlar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi**: \<complex >

**Ad alanı:** std

## <a name="remarks"></a>Açıklamalar

Karmaşık bir sayı, gerçek sayıların sıralı bir çiftidir. Yalnızca geometrik olarak, karmaşık düzlem gerçek ve iki boyutlu düzledir. Gerçek düzleden ayırt eden karmaşık düzlemin özel nitelikleri, ek bir cebirsel yapısına sahip olmasından kaynaklanır. Bu cebirsel yapısında iki temel işlem vardır:

- Toplama (*a*, *b*) + (*c*, *d*) = (*a*  + *c*, *b*  + *d*) olarak tanımlandı

- (*A*, *b*) \* (*c*, *d*) olarak tanımlanan çarpma = (*AC*  - *BD*, *ad*  + *BC*)

Karmaşık ek ve karmaşık çarpma işlemlerine sahip karmaşık sayıların kümesi, standart cebirsel Sense içindeki bir alandır:

- Toplama ve çarpma işlemleri, tam olarak gerçek sayı alanı üzerinde gerçek ekleme ve çarpma ile aynı şekilde, ek olarak, aynı şekilde dağıtılır ve çarpıcı olur.

- Karmaşık sayı (0, 0), eklenebilir kimliktir ve (1, 0), çarpma kimliğidir.

- Karmaşık bir sayı (*a*, *b*) için ek ters çevirme, (0,*0) hariç*olmak üzere bu tür karmaşık sayılar için çarpma tersidir

   (*a* */(* <sup>2</sup>  + *b*<sup>2</sup>),-*b*/(<sup>2</sup>  + *b*<sup>2</sup>)))

Z  =  z = (*a*, *b*) biçiminde bir *karmaşık sayıyı temsil* ederek *z* 'yi*bir*  + *bı*, *burada*<sup>2</sup> =-1 olduğunda, gerçek sayıların kümesinin algebi 'nin kuralları karmaşık kümesine uygulanabilir sayılar ve bileşenleri. Örneğin:

   (1 + 2*ı*) \* (2 + 3*ı*) = 1 \* (2 *+ 3 ı*) + 2*ı* \* (2 *+ 3 ı) =* (2 + 3*ı*) + (4*i* + 6*ı*<sup>2</sup>) = (2-6) + (3 + 4)*i* =-4 + 7*ı*

Karmaşık sayıların sistemi bir alandır, ancak sıralı bir alan değildir. Gerçek sayıların ve alt kümelerinin alanı için olduğu gibi karmaşık sayıların sıralaması yoktur; bu nedenle, gerçek sayılara göre karmaşık sayılara uygulanamaz.

Bir karmaşık sayı olan *z*'yi temsil eden üç ortak biçim vardır:

- Kartezyen: *z*  = *a*  + *bı*

- Kutupsal: *z*  = *r* (cos *p*  + *i* te *p*)

- Üstel: *z*  = *r* \* *e*<sup>*IP*</sup>

Karmaşık bir sayının bu standart temsillerinde kullanılan terimler şu şekilde adlandırılır:

- Gerçek Kartezyen bileşen veya gerçek bölüm *a*.

- Sanal Kartezyen bileşeni veya sanal bölüm *b*.

- Bir karmaşık sayının mod veya mutlak değeri *r*.

- Radyan *cinsinden bağımsız* değişken veya aşama açısı.

Aksi belirtilmediği takdirde, birden çok değer döndürebilmesine olanak veren işlevler, tek değerli tutmak için-π ' dan büyük ve + π ' den küçük veya buna eşit olan bağımsız değişkenlerin bir asıl değerini döndürmesi gerekir. Tüm açıların radyan cinsinden ifade edilmesi gerekir, burada bir daire içinde 2π radyan (360 derece) bulunur.

## <a name="members"></a>Üyeler

### <a name="functions"></a>İşlevler

|||
|-|-|
|[mutlak](../standard-library/complex-functions.md#abs)|Karmaşık bir sayının mod sayısını hesaplar.|
|[acos](../standard-library/complex-functions.md#acos)||
|[acosh](../standard-library/complex-functions.md#acosh)||
|[değişkeni](../standard-library/complex-functions.md#arg)|Bağımsız değişkeni karmaşık bir sayıdan ayıklar.|
|[Asin](../standard-library/complex-functions.md#asin)||
|[ASİNH](../standard-library/complex-functions.md#asinh)||
|[atan](../standard-library/complex-functions.md#atan)||
|[ATANH](../standard-library/complex-functions.md#atanh)||
|[conj](../standard-library/complex-functions.md#conj)|Karmaşık bir sayının karmaşık eşleniğini döndürür.|
|[cos](../standard-library/complex-functions.md#cos)|Karmaşık bir sayının kosinüsünü döndürür.|
|[Cosh](../standard-library/complex-functions.md#cosh)|Karmaşık bir sayının hiperbolik kosinüsünü döndürür.|
|[exp](../standard-library/complex-functions.md#exp)|Karmaşık bir sayının üstel fonksiyonunu döndürür.|
|[imag](../standard-library/complex-functions.md#imag)|Karmaşık bir sayının sanal bileşenini ayıklar.|
|[açmasını](../standard-library/complex-functions.md#log)|Karmaşık bir sayının doğal logaritmasını döndürür.|
|[log10](../standard-library/complex-functions.md#log10)|Karmaşık bir sayının 10 tabanında logaritmasını döndürür.|
|[eklenmeli](../standard-library/complex-functions.md#norm)|Karmaşık bir sayının norm sayısını ayıklar.|
|[çizgili](../standard-library/complex-functions.md#polar)|Kartezyen biçiminde, belirtilen mod ve bağımsız değişkene karşılık gelen karmaşık sayıyı döndürür.|
|[POW](../standard-library/complex-functions.md#pow)|Karmaşık bir sayı olan bir tabanı başka bir karmaşık sayının gücüne yükselterek elde edilen karmaşık sayıyı değerlendirir.|
|[PROJ](../standard-library/complex-functions.md#proj)||
|[gerçek](../standard-library/complex-functions.md#real)|Karmaşık bir sayının gerçek bileşenini ayıklar.|
|[sin](../standard-library/complex-functions.md#sin)|Karmaşık bir sayının sinüsünü döndürür.|
|[sinh](../standard-library/complex-functions.md#sinh)|Karmaşık bir sayının hiperbolik sinüsünü döndürür.|
|[k](../standard-library/complex-functions.md#sqrt)|Karmaşık bir sayının kare kökünü döndürür.|
|[Başlangıçtan](../standard-library/complex-functions.md#tan)|Karmaşık bir sayının tanjantını döndürür.|
|[tanh](../standard-library/complex-functions.md#tanh)|Karmaşık bir sayının hiperbolik tanjantını döndürür.|

### <a name="operators"></a>İşleçler

|||
|-|-|
|[operator!=](../standard-library/complex-operators.md#op_neq)|İki karmaşık sayı arasında eşitsizlik için, biri veya her ikisi de gerçek ve sanal parçalar için türün alt kümesine ait olabilir.|
|[işlecinde](../standard-library/complex-operators.md#op_star)|, Biri veya her ikisi de gerçek ve sanal parçalar için türün alt kümesine ait olabilen iki karmaşık sayıyı çarpar.|
|[işleç +](../standard-library/complex-operators.md#op_add)|, Biri veya her ikisi de gerçek ve sanal parçalar için türün alt kümesine ait olabilen iki karmaşık sayı ekler.|
|[işlecinde](../standard-library/complex-operators.md#operator-)|, Bir veya her ikisini de gerçek ve sanal parçalar için türün alt kümesine ait olabilen iki karmaşık sayıyı çıkartır.|
|[işlecinde](../standard-library/complex-operators.md#op_div)|İki karmaşık sayıyı, birini veya her ikisini de gerçek ve sanal parçalar için türün alt kümesine ait olabilir.|
|[işleç < \<](../standard-library/complex-operators.md#op_lt_lt)|Çıkış akışına karmaşık bir sayı ekleyen bir şablon işlevi.|
|[işleç = =](../standard-library/complex-operators.md#op_eq_eq)|İki karmaşık sayı arasındaki eşitlik için bir veya her ikisinin de gerçek ve sanal parçalar için türün alt kümesine ait olabileceğini sınar.|
|[işleç > >](../standard-library/complex-operators.md#op_gt_gt)|Giriş akışından karmaşık bir değer çıkaran bir şablon işlevi.|

### <a name="classes"></a>Sınıflar

|||
|-|-|
|[karmaşık \<double >](../standard-library/complex-double.md)|Açıkça özelleştirilmiş sınıf şablonu, her ikisi de, her ikisi de karmaşık bir sayının gerçek bölümünü temsil eden ve ikincisi sanal parçayı temsil eden **Double**türü bir nesne çifti depolayan bir nesneyi tanımlar.|
|[karmaşık \<float >](../standard-library/complex-float.md)|Açıkça özelleştirilmiş sınıf şablonu, her ikisi de float türünde, her ikisi de karmaşık bir sayının gerçek bölümünü temsil eden ve ikincisi sanal parçayı temsil eden **kayan**bir nesne çifti depolayan bir nesneyi tanımlar.|
|[karmaşık \<long Double >](../standard-library/complex-long-double.md)|Açıkça özelleştirilmiş sınıf şablonu, her ikisi de **Long Double**türünde, her ikisi de karmaşık bir sayının gerçek kısmını temsil eden ve ikinci sanal parçayı temsil eden bir nesne çifti depolayan bir nesneyi tanımlar.|
|[ş](../standard-library/complex-class.md)|Sınıf şablonu, karmaşık sayı sistemini temsil etmek için kullanılan bir nesneyi tanımlar ve karmaşık aritmetik işlemler gerçekleştirir.|

### <a name="literals"></a>Sabit değerler

@No__t_0complex > üst bilgisi, gerçek bölüm sıfır ve sanal bölüm giriş parametresinin değeri olan karmaşık bir sayı oluşturan [Kullanıcı tanımlı aşağıdaki sabit değerleri](../cpp/user-defined-literals-cpp.md) tanımlar.

|||
|-|-|
|`constexpr complex<long double> operator""il(long double d)`<br />`constexpr complex<long double> operator""il(unsigned long long d)`|Şunu döndürür: `complex<long double>{0.0L, static_cast<long double>(d)}`|
|`constexpr complex<double> operator""i(long double d)`<br />`constexpr complex<double> operator""i(unsigned long long d)`|Döndürür: `complex<double>{0.0, static_cast<double>(d)}`.|
|`constexpr complex<float> operator""if(long double d)`<br />`constexpr complex<float> operator""if(unsigned long long d)`|Döndürür: `complex<float>{0.0f, static_cast<float>(d)}`.|

## <a name="see-also"></a>Ayrıca bkz.

[Üst bilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
