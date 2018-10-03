---
title: numeric_limits sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- limits/std::numeric_limits
- limits/std::numeric_limits::denorm_min
- limits/std::numeric_limits::digits
- limits/std::numeric_limits::digits10
- limits/std::numeric_limits::epsilon
- limits/std::numeric_limits::has_denorm
- limits/std::numeric_limits::has_denorm_loss
- limits/std::numeric_limits::has_infinity
- limits/std::numeric_limits::has_quiet_NaN
- limits/std::numeric_limits::has_signaling_NaN
- limits/std::numeric_limits::infinity
- limits/std::numeric_limits::is_bounded
- limits/std::numeric_limits::is_exact
- limits/std::numeric_limits::is_iec559
- limits/std::numeric_limits::is_integer
- limits/std::numeric_limits::is_modulo
- limits/std::numeric_limits::is_signed
- limits/std::numeric_limits::is_specialized
- limits/std::numeric_limits::lowest
- limits/std::numeric_limits::max
- limits/std::numeric_limits::max_digits10
- limits/std::numeric_limits::max_exponent
- limits/std::numeric_limits::max_exponent10
- limits/std::numeric_limits::min
- limits/std::numeric_limits::min_exponent
- limits/std::numeric_limits::min_exponent10
- limits/std::numeric_limits::quiet_NaN
- limits/std::numeric_limits::radix
- limits/std::numeric_limits::round_error
- limits/std::numeric_limits::round_style
- limits/std::numeric_limits::signaling_NaN
- limits/std::numeric_limits::tinyness_before
- limits/std::numeric_limits::traps
dev_langs:
- C++
helpviewer_keywords:
- std::numeric_limits [C++]
- std::numeric_limits [C++], denorm_min
- std::numeric_limits [C++], digits
- std::numeric_limits [C++], digits10
- std::numeric_limits [C++], epsilon
- std::numeric_limits [C++], has_denorm
- std::numeric_limits [C++], has_denorm_loss
- std::numeric_limits [C++], has_infinity
- std::numeric_limits [C++], has_quiet_NaN
- std::numeric_limits [C++], has_signaling_NaN
- std::numeric_limits [C++], infinity
- std::numeric_limits [C++], is_bounded
- std::numeric_limits [C++], is_exact
- std::numeric_limits [C++], is_iec559
- std::numeric_limits [C++], is_integer
- std::numeric_limits [C++], is_modulo
- std::numeric_limits [C++], is_signed
- std::numeric_limits [C++], is_specialized
- std::numeric_limits [C++], lowest
- std::numeric_limits [C++], max
- std::numeric_limits [C++], max_digits10
- std::numeric_limits [C++], max_exponent
- std::numeric_limits [C++], max_exponent10
- std::numeric_limits [C++], min
- std::numeric_limits [C++], min_exponent
- std::numeric_limits [C++], min_exponent10
- std::numeric_limits [C++], quiet_NaN
- std::numeric_limits [C++], radix
- std::numeric_limits [C++], round_error
- std::numeric_limits [C++], round_style
- std::numeric_limits [C++], signaling_NaN
- std::numeric_limits [C++], tinyness_before
- std::numeric_limits [C++], traps
ms.assetid: 9e817177-0e91-48e6-b680-0531c4b26625
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 28e6b38ef02bd97bb39bdd2ec69788027dcf59e5
ms.sourcegitcommit: 1d9bd38cacbc783fccd3884b7b92062161c91c84
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/03/2018
ms.locfileid: "48235600"
---
# <a name="numericlimits-class"></a>numeric_limits Sınıfı

Şablon sınıfı, yerleşik sayısal türler aritmetik özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class numeric_limits
```

### <a name="parameters"></a>Parametreler

*Türü*<br/>
Temel öğe veri türü özellikleri güncellenmekte test veya sorgulanabilir.

## <a name="remarks"></a>Açıklamalar

Üst bilgi türleri için açık uzmanlık tanımlar **wchar_t**, **bool**, **char**, **signed char**, **işaretsiz char**, **kısa**, **işaretsiz**, **int**, **işaretsiz int**, **uzun**, **işaretsiz uzun**, **float**, **çift**, **uzun çift**, **uzun uzun**, **işaretsiz long long**, **char16_t**, ve **char32_t**. Bu bir açık uzmanlık, üye için [numeric_limits::is_specialized](#is_specialized) olduğu **true**, ve tüm ilgili üyeleri anlamlı değerlere sahiptir. Program ek açık uzmanlık sağlayabilirsiniz. Çoğu sınıf üye işlevleri tanımlamak veya olası uygulamalarını test **float**.

Rastgele bir uzmanlık için hiçbir üye anlamlı değerlere sahip. Sıfır anlamlı bir değer olmayan bir üye nesnesini depolar (veya **false**) ve anlamlı bir değer döndürmeyen bir üye işlevinin döndürdüğü `Type(0)`.

### <a name="static-functions-and-constants"></a>Statik işlevler ve sabitleri

|||
|-|-|
|[denorm_min](#denorm_min)|En küçük sıfır döndürür değeri normalleştirilmişlikten çıkarılır.|
|[basamak](#digits)|Duyarlık kaybı yaşanmadan türü temsil edebilen taban basamak sayısını döndürür.|
|[digits10](#digits10)|Duyarlık kaybı yaşanmadan türü temsil edebilen bir ondalık basamak sayısını döndürür.|
|[Epsilon](#epsilon)|Veri türü temsil edebilen 1'den büyük en küçük değeri ile 1 arasındaki farkı döndürür.|
|[has_denorm](#has_denorm)|Testleri izin verip bir tür değerleri normalleştirilmişlikten çıkarılır.|
|[has_denorm_loss](#has_denorm_loss)|Doğruluk kaybı normalleştirilmişlikten çıkarma kayıp yerine kesin olmayan bir sonucu olarak algılanan olup olmadığını sınar.|
|[has_infinity](#has_infinity)|Pozitif sonsuz temsili bir türe sahip olup olmadığını sınar.|
|[has_quiet_NaN](#has_quiet_nan)|Nonsignaling olan bir sayı değil (NAN) bir sessiz temsili bir türe sahip olup olmadığını sınar.|
|[has_signaling_NaN](#has_signaling_nan)|Bir tür sinyal sayı olmayan (NAN) bir gösterimi olup olmadığını test eder.|
|[sonsuz](#infinity)|Pozitif sonsuz varsa türünün temsili.|
|[is_bounded](#is_bounded)|Bir tür olarak temsil değerleri kümesi sınırlı olup olmadığını sınar.|
|[is_exact](#is_exact)|Test türü üzerinde yapılan hesaplamaları yuvarlama hataları ücretsizdir.|
|[is_iec559](#is_iec559)|Bir tür IEC 559 standartlara uygun olmadığını sınar.|
|[is_integer](#is_integer)|Bir tamsayı temsili bir türe sahip olmadığını sınar.|
|[is_modulo](#is_modulo)|Bir tür sahipse, testleri bir modül gösterimi.|
|[is_signed](#is_signed)|İmzalı bir gösterimi bir türe sahip olmadığını sınar.|
|[is_specialized](#is_specialized)|Şablon sınıfı içinde tanımlanan bir açık özelleştirme bir türe sahip olmadığını test eder `numeric_limits`.|
|[En düşük](#lowest)|En negatif sonlu değeri döndürür.|
|[en fazla](#max)|Bir tür için maksimum sonlu değeri döndürür.|
|[max_digits10](#max_digits10)|İki ayrı türü değerleri farklı ondalık gösterimlerini sağlamak için gerekli ondalık basamak sayısını döndürür.|
|[max_exponent](#max_exponent)|Taban sınıfın, gücünü ortaya çıktığında, kayan nokta türü sınırlı bir değeri temsil edebilir en fazla pozitif tam sayı üssü döndürür.|
|[max_exponent10](#max_exponent10)|Bir taban on gücü için harekete geçirildiğinde, kayan nokta türü sınırlı bir değeri temsil edebilir en fazla pozitif tam sayı üssü döndürür.|
|[Min](#min)|Bir tür için en düşük normalleştirilmiş değerini döndürür.|
|[min_exponent](#min_exponent)|Taban sınıfın, gücünü ortaya çıktığında, kayan nokta türü sınırlı bir değeri temsil edebilir en büyük negatif tam sayı üs döndürür.|
|[min_exponent10](#min_exponent10)|On sınıfın gücü için oluştuğunda, kayan nokta türü sınırlı bir değeri temsil edebilir en büyük negatif tam sayı üs döndürür.|
|[quiet_NaN](#quiet_nan)|Sessiz bir gösterimi türü için sayı olmayan (NAN) döndürür.|
|[radix](#radix)|İntegral taban döndürür taban bir türü gösterimi için kullanılan, olarak adlandırılır.|
|[round_error](#round_error)|Hata türü için izin verilecek en fazla döndürür.|
|[round_style](#round_style)|Bir kayan nokta değeri tamsayıya yuvarlama uygulaması seçim yapabileceği çeşitli yöntemleri tanımlayan bir değer döndürür.|
|[signaling_NaN](#signaling_nan)|Bir sayı değil (NAN) sinyal temsilini türünü döndürür.|
|[tinyness_before](#tinyness_before)|Bir tür değeri normalleştirilmiş bir değer olarak yuvarlama önce temsil etmek için çok küçük olduğunu anlayabilirsiniz olup olmadığını sınar.|
|[Tuzaklar](#traps)|Test türü için aritmetik özel durumları yakalama, raporlar uygulanır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sınırları >

**Namespace:** std

## <a name="denorm_min"></a>  numeric_limits::denorm_min

En küçük sıfır döndürür değeri normalleştirilmişlikten çıkarılır.

```cpp
static constexpr Type denorm_min() throw();
```

### <a name="return-value"></a>Dönüş Değeri

En küçük sıfır olmayan normalleştirilmişlikten çıkarılmış değeri.

### <a name="remarks"></a>Açıklamalar

**uzun çift** aynı **çift** C++ derleyicisi için.

İşlevi aynı türü için en düşük değerini döndürür olarak [min](#min) varsa [has_denorm](#has_denorm) eşit değildir `denorm_present`.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_denorm_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The smallest nonzero denormalized value" << endl
        << "for float objects is: "
        << numeric_limits<float>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for double objects is: "
        << numeric_limits<double>::denorm_min( ) << endl;
   cout << "The smallest nonzero denormalized value" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::denorm_min( ) << endl;

   // A smaller value will round to zero
   cout << numeric_limits<float>::denorm_min( )/2 <<endl;
   cout << numeric_limits<double>::denorm_min( )/2 <<endl;
   cout << numeric_limits<long double>::denorm_min( )/2 <<endl;
}
```

```Output
The smallest nonzero denormalized value
for float objects is: 1.4013e-045
The smallest nonzero denormalized value
for double objects is: 4.94066e-324
The smallest nonzero denormalized value
for long double objects is: 4.94066e-324
0
0
0
```

## <a name="digits"></a>  numeric_limits::Digits

Duyarlık kaybı yaşanmadan türü temsil edebilen taban basamak sayısını döndürür.

```cpp
static constexpr int digits = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Duyarlık kaybı yaşanmadan türü temsil edebilen taban basamak sayısı.

### <a name="remarks"></a>Açıklamalar

Üye türü önceden tanımlanmış tamsayı türünün herhangi bir imza biti dışında bit sayısı kadar olan değişiklik temsil edebilen taban basamak sayısı veya önceden tanımlanmış bir kayan nokta türü için Mantis basamak sayısını depolar.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_digits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits <<endl;
   cout << numeric_limits<double>::digits <<endl;
   cout << numeric_limits<long double>::digits <<endl;
   cout << numeric_limits<int>::digits <<endl;
   cout << numeric_limits<__int64>::digits <<endl;
}
```

```Output
24
53
53
31
63
```

## <a name="digits10"></a>  numeric_limits::digits10

Duyarlık kaybı yaşanmadan türü temsil edebilen bir ondalık basamak sayısını döndürür.

```cpp
static constexpr int digits10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Duyarlık kaybı yaşanmadan türü temsil edebilen bir ondalık basamak sayısı.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_digits10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::digits10 <<endl;
   cout << numeric_limits<double>::digits10 <<endl;
   cout << numeric_limits<long double>::digits10 <<endl;
   cout << numeric_limits<int>::digits10 <<endl;
   cout << numeric_limits<__int64>::digits10 <<endl;
   float f = (float)99999999;
   cout.precision ( 10 );
   cout << "The float is; " << f << endl;
}
```

```Output
6
15
15
9
18
The float is; 100000000
```

## <a name="epsilon"></a>  numeric_limits::Epsilon

İşlevi 1 ve en küçük değeri arasındaki fark için veri türünü gösterilebilir 1'den büyük olarak döndürür.

```cpp
static constexpr Type epsilon() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Veri türü gösterilebilir 1'den büyük en küçük değeri ile 1 arasındaki fark.

### <a name="remarks"></a>Açıklamalar

Değer flt_epsılon türüdür **float**. `epsilon` bir tür için en küçük pozitif kayan noktalı sayı *N* şekilde *N* + `epsilon` + *N* gösterilebilir olduğu.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_epsilon.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for float objects is: "
        << numeric_limits<float>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for double objects is: "
        << numeric_limits<double>::epsilon( ) << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1" << endl
        << "for long double objects is: "
        << numeric_limits<long double>::epsilon( ) << endl;
}
```

```Output
The difference between 1 and the smallest value greater than 1
for float objects is: 1.19209e-007
The difference between 1 and the smallest value greater than 1
for double objects is: 2.22045e-016
The difference between 1 and the smallest value greater than 1
for long double objects is: 2.22045e-016
```

## <a name="has_denorm"></a>  numeric_limits::has_denorm

Testleri izin verip bir tür değerleri normalleştirilmişlikten çıkarılır.

```cpp
static constexpr float_denorm_style has_denorm = denorm_absent;
```

### <a name="return-value"></a>Dönüş Değeri

Bir sabit listesi değeri türü **const**`float_denorm_style`gösteren olup türü normalleştirilmişlikten çıkarılmış değerlere izin verir.

### <a name="remarks"></a>Açıklamalar

Üye depoları `denorm_present` normal dışı bir kayan nokta türü değerleri için etkili bir şekilde üs bit değişken bir sayı.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_has_denorm.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects allow denormalized values: "
        << numeric_limits<float>::has_denorm
        << endl;
   cout << "Whether double objects allow denormalized values: "
        << numeric_limits<double>::has_denorm
        << endl;
   cout << "Whether long int objects allow denormalized values: "
        << numeric_limits<long int>::has_denorm
        << endl;
}
```

```Output
Whether float objects allow denormalized values: 1
Whether double objects allow denormalized values: 1
Whether long int objects allow denormalized values: 0
```

## <a name="has_denorm_loss"></a>  numeric_limits::has_denorm_loss

Doğruluk kaybı normalleştirilmişlikten çıkarma kayıp yerine kesin olmayan bir sonucu olarak algılanan olup olmadığını sınar.

```cpp
static constexpr bool has_denorm_loss = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** doğruluk kaybı normalleştirilmişlikten çıkarma zarar; algılanırsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

True değeri normalleştirilmişlikten çıkarılmış bir sonucu olarak (çok normalleştirilmiş bir değer olarak temsil etmek için küçük) teslim edilir çünkü bölümünü kesin değilse veya doğruluğu kaybetti olup olmadığını belirleyen bir tür için üye depolar (aynı sonucunda üs sınırlamaları için konu yok Aralık ve duyarlık) bazı sonuçlarını etkileyebilecek IEC 559 kayan nokta ifadeleri bir seçenek.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_has_denorm_loss.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects can detect denormalized loss: "
        << numeric_limits<float>::has_denorm_loss
        << endl;
   cout << "Whether double objects can detect denormalized loss: "
        << numeric_limits<double>::has_denorm_loss
        << endl;
   cout << "Whether long int objects can detect denormalized loss: "
        << numeric_limits<long int>::has_denorm_loss
        << endl;
}
```

```Output
Whether float objects can detect denormalized loss: 1
Whether double objects can detect denormalized loss: 1
Whether long int objects can detect denormalized loss: 0
```

## <a name="has_infinity"></a>  numeric_limits::has_infinity

Pozitif sonsuz temsili bir türe sahip olup olmadığını sınar.

```cpp
static constexpr bool has_infinity = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türü, Pozitif sonsuz; temsili varsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Üyeyi döndürür **true** varsa [is_iec559](#is_iec559) olduğu **true**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_has_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have infinity: "
        << numeric_limits<float>::has_infinity
        << endl;
   cout << "Whether double objects have infinity: "
        << numeric_limits<double>::has_infinity
        << endl;
   cout << "Whether long int objects have infinity: "
        << numeric_limits<long int>::has_infinity
        << endl;
}
```

```Output
Whether float objects have infinity: 1
Whether double objects have infinity: 1
Whether long int objects have infinity: 0
```

## <a name="has_quiet_nan"></a>  numeric_limits::has_quiet_NaN

Nonsignaling olan bir sayı değil (NAN) bir sessiz temsili bir türe sahip olup olmadığını sınar.

```cpp
static constexpr bool has_quiet_NaN = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa **türü** sessiz bir NAN için; bir gösterimi içeriyor **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Sessiz bir NAN değil, bir ifadede varlığını işaret etmiyor numarası, kodlama ' dir. Dönüş değeri **true** varsa [is_iec559](#is_iec559) geçerlidir.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_has_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have quiet_NaN: "
        << numeric_limits<float>::has_quiet_NaN
        << endl;
   cout << "Whether double objects have quiet_NaN: "
        << numeric_limits<double>::has_quiet_NaN
        << endl;
   cout << "Whether long int objects have quiet_NaN: "
        << numeric_limits<long int>::has_quiet_NaN
        << endl;
}
```

```Output
Whether float objects have quiet_NaN: 1
Whether double objects have quiet_NaN: 1
Whether long int objects have quiet_NaN: 0
```

## <a name="has_signaling_nan"></a>  numeric_limits::has_signaling_NaN

Bir tür sinyal sayı olmayan (NAN) bir gösterimi olup olmadığını test eder.

```cpp
static constexpr bool has_signaling_NaN = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türü; bir sinyal NAN temsili varsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bir sinyal NAN bir bildiren bir ifadede varlığını sayı değil, kodlama ' dir. Dönüş değeri **true** varsa [is_iec559](#is_iec559) geçerlidir.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_has_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signaling_NaN: "
        << numeric_limits<float>::has_signaling_NaN
        << endl;
   cout << "Whether double objects have a signaling_NaN: "
        << numeric_limits<double>::has_signaling_NaN
        << endl;
   cout << "Whether long int objects have a signaling_NaN: "
        << numeric_limits<long int>::has_signaling_NaN
        << endl;
}
```

```Output
Whether float objects have a signaling_NaN: 1
Whether double objects have a signaling_NaN: 1
Whether long int objects have a signaling_NaN: 0
```

## <a name="infinity"></a>  numeric_limits::infinity

Pozitif sonsuz varsa türünün temsili.

```cpp
static constexpr Type infinity() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Pozitif sonsuz varsa türünün temsili.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri anlamlı yalnızca [has_infinity](#has_infinity) olduğu **true**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_infinity.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << numeric_limits<float>::has_infinity <<endl;
   cout << numeric_limits<double>::has_infinity<<endl;
   cout << numeric_limits<long double>::has_infinity <<endl;
   cout << numeric_limits<int>::has_infinity <<endl;
   cout << numeric_limits<__int64>::has_infinity <<endl;

   cout << "The representation of infinity for type float is: "
        << numeric_limits<float>::infinity( ) <<endl;
   cout << "The representation of infinity for type double is: "
        << numeric_limits<double>::infinity( ) <<endl;
   cout << "The representation of infinity for type long double is: "
        << numeric_limits<long double>::infinity( ) <<endl;
}
```

```Output
1
1
1
0
0
The representation of infinity for type float is: inf
The representation of infinity for type double is: inf
The representation of infinity for type long double is: inf
```

## <a name="is_bounded"></a>  numeric_limits::is_bounded

Bir tür olarak temsil değerleri kümesi sınırlı olup olmadığını sınar.

```cpp
static constexpr bool is_bounded = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türünün temsil edilebilir değerler; sınırlanmış bir dizi varsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış tüm türleri temsil edilebilir değerler sınırlanmış bir dizi ve dönüş **true**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_is_bounded.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have bounded set "
        << "of representable values: "
        << numeric_limits<float>::is_bounded
        << endl;
   cout << "Whether double objects have bounded set "
        << "of representable values: "
        << numeric_limits<double>::is_bounded
        << endl;
   cout << "Whether long int objects have bounded set "
        << "of representable values: "
        << numeric_limits<long int>::is_bounded
        << endl;
   cout << "Whether unsigned char objects have bounded set "
        << "of representable values: "
        << numeric_limits<unsigned char>::is_bounded
        << endl;
}
```

```Output
Whether float objects have bounded set of representable values: 1
Whether double objects have bounded set of representable values: 1
Whether long int objects have bounded set of representable values: 1
Whether unsigned char objects have bounded set of representable values: 1
```

## <a name="is_exact"></a>  numeric_limits::is_exact

Test türü üzerinde yapılan hesaplamaları yuvarlama hataları ücretsizdir.

```cpp
static constexpr bool is_exact = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hesaplamaları yuvarlama hataları; biri boş ise **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Tüm önceden tanımlanmış bir tam sayı türleri tam temsiller için değerleri ve dönüş **false**. Sabit nokta veya rasyonel gösterimi de tam olarak kabul edilir, ancak bir kayan nokta gösterimi değil.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_is_exact.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<float>::is_exact
        << endl;
   cout << "Whether double objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<double>::is_exact
        << endl;
   cout << "Whether long int objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<long int>::is_exact
        << endl;
   cout << "Whether unsigned char objects have calculations "
        << "free of rounding errors: "
        << numeric_limits<unsigned char>::is_exact
        << endl;
}
```

```Output
Whether float objects have calculations free of rounding errors: 0
Whether double objects have calculations free of rounding errors: 0
Whether long int objects have calculations free of rounding errors: 1
Whether unsigned char objects have calculations free of rounding errors: 1
```

## <a name="is_iec559"></a>  numeric_limits::is_iec559

Bir tür IEC 559 standartlara uygun olmadığını sınar.

```cpp
static constexpr bool is_iec559 = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türü IEC 559 standartlarına; uyuyorsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

IEC 559 uluslararası bir standart kayan nokta değerlerini temsil eden ve olarak da bilinen IEEE 754 ABD.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_is_iec559.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects conform to iec559 standards: "
        << numeric_limits<float>::is_iec559
        << endl;
   cout << "Whether double objects conform to iec559 standards: "
        << numeric_limits<double>::is_iec559
        << endl;
   cout << "Whether int objects conform to iec559 standards: "
        << numeric_limits<int>::is_iec559
        << endl;
   cout << "Whether unsigned char objects conform to iec559 standards: "
        << numeric_limits<unsigned char>::is_iec559
        << endl;
}
```

```Output
Whether float objects conform to iec559 standards: 1
Whether double objects conform to iec559 standards: 1
Whether int objects conform to iec559 standards: 0
Whether unsigned char objects conform to iec559 standards: 0
```

## <a name="is_integer"></a>  numeric_limits::is_integer

Bir tamsayı temsili bir türe sahip olmadığını sınar.

```cpp
static constexpr bool is_integer = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türü bir tamsayı gösterimi; varsa **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Tüm önceden tanımlanmış tamsayı türlerinin bir tamsayı gösterimi yoktur.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_is_integer.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an integral representation: "
        << numeric_limits<float>::is_integer
        << endl;
   cout << "Whether double objects have an integral representation: "
        << numeric_limits<double>::is_integer
        << endl;
   cout << "Whether int objects have an integral representation: "
        << numeric_limits<int>::is_integer
        << endl;
   cout << "Whether unsigned char objects have an integral representation: "
        << numeric_limits<unsigned char>::is_integer
        << endl;
}
```

```Output
Whether float objects have an integral representation: 0
Whether double objects have an integral representation: 0
Whether int objects have an integral representation: 1
Whether unsigned char objects have an integral representation: 1
```

## <a name="is_modulo"></a>  numeric_limits::is_modulo

Olmadığını test eder bir **türü** sahip bir modül gösterimi.

```cpp
static constexpr bool is_modulo = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türündeyse bir gösterimi; modül **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bir gösterimi modül tüm sonuçları bir değer azalır burada bir gösterimi olan. Tüm önceden tanımlanmış bir işaretsiz tamsayı türlerine sahip bir modül gösterimi.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_is_modulo.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a modulo representation: "
        << numeric_limits<float>::is_modulo
        << endl;
   cout << "Whether double objects have a modulo representation: "
        << numeric_limits<double>::is_modulo
        << endl;
   cout << "Whether signed char objects have a modulo representation: "
        << numeric_limits<signed char>::is_modulo
        << endl;
   cout << "Whether unsigned char objects have a modulo representation: "
        << numeric_limits<unsigned char>::is_modulo
        << endl;
}
```

```Output
Whether float objects have a modulo representation: 0
Whether double objects have a modulo representation: 0
Whether signed char objects have a modulo representation: 1
Whether unsigned char objects have a modulo representation: 1
```

## <a name="is_signed"></a>  numeric_limits::is_signed

İmzalı bir gösterimi bir türe sahip olmadığını sınar.

```cpp
static constexpr bool is_signed = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** imzalı bir gösterimi; türündeyse **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Bu durum önceden tanımlanmış tüm kayan nokta ve imzalı tamsayı türleri için imzalı bir gösterimi olan bir türü için true üye depolar.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_is_signaled.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have a signed representation: "
        << numeric_limits<float>::is_signed
        << endl;
   cout << "Whether double objects have a signed representation: "
        << numeric_limits<double>::is_signed
        << endl;
   cout << "Whether signed char objects have a signed representation: "
        << numeric_limits<signed char>::is_signed
        << endl;
   cout << "Whether unsigned char objects have a signed representation: "
        << numeric_limits<unsigned char>::is_signed
        << endl;
}
```

```Output
Whether float objects have a signed representation: 1
Whether double objects have a signed representation: 1
Whether signed char objects have a signed representation: 1
Whether unsigned char objects have a signed representation: 0
```

## <a name="is_specialized"></a>  numeric_limits::is_specialized

Şablon sınıfı içinde tanımlanan bir açık özelleştirme bir türe sahip olmadığını test eder `numeric_limits`.

```cpp
static constexpr bool is_specialized = false;
```

### <a name="return-value"></a>Dönüş Değeri

**true** bir açık özelleştirme; Şablon sınıfı içinde tanımlanan tür sahipse, **false** Aksi takdirde.

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için tanımlanmış bir açık özelleştirme işaretçileri dışındaki tüm skaler türleri sahip `numeric_limits`.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_is_specialized.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float>::is_specialized
        << endl;
   cout << "Whether float* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<float*>::is_specialized
        << endl;
   cout << "Whether int objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int>::is_specialized
        << endl;
   cout << "Whether int* objects have an explicit "
        << "specialization in the class: "
        << numeric_limits<int*>::is_specialized
        << endl;
}
```

```Output
Whether float objects have an explicit specialization in the class: 1
Whether float* objects have an explicit specialization in the class: 0
Whether int objects have an explicit specialization in the class: 1
Whether int* objects have an explicit specialization in the class: 0
```

## <a name="lowest"></a>  numeric_limits::lowest

En negatif sonlu değeri döndürür.

```cpp
static constexpr Type lowest() throw();
```

### <a name="return-value"></a>Dönüş Değeri

En negatif sonlu değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Türü için en negatif sonlu değeri döndürür (genelde `min()` tamsayı türleri için ve `-max()` kayan nokta türleri için). Dönüş değeri anlamlı varsa `is_bounded` olduğu **true**.

## <a name="max"></a>  numeric_limits::Max

Bir tür için maksimum sonlu değeri döndürür.

```cpp
static constexpr Type max() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir tür için maksimum sınırlı değeri.

### <a name="remarks"></a>Açıklamalar

Maksimum sonlu değeri INT_MAX için türdür **int** ve türünün FLT_MAX **float**. Dönüş değeri anlamlı varsa [is_bounded](#is_bounded) olduğu **true**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_max.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main() {
   cout << "The maximum value for type float is:  "
        << numeric_limits<float>::max( )
        << endl;
   cout << "The maximum value for type double is:  "
        << numeric_limits<double>::max( )
        << endl;
   cout << "The maximum value for type int is:  "
        << numeric_limits<int>::max( )
        << endl;
   cout << "The maximum value for type short int is:  "
        << numeric_limits<short int>::max( )
        << endl;
}
```

## <a name="max_digits10"></a>  numeric_limits::max_digits10

İki ayrı türü değerleri farklı ondalık gösterimleri sahip olduğunuzdan emin olmak için gerekli ondalık basamak sayısını döndürür.

```cpp
static constexpr int max_digits10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İki ayrı türü değerleri farklı ondalık gösterimleri olduğundan emin olmak için gerekli olan ondalık basamak sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye türü iki farklı değerleri farklı ondalık gösterimleri sahip olduğunuzdan emin olmak için gerekli ondalık basamak sayısı yer depolar.

## <a name="max_exponent"></a>  numeric_limits::max_exponent

Taban sınıfın, gücünü ortaya çıktığında, kayan nokta türü sınırlı bir değeri temsil edebilir en fazla pozitif tam sayı üssü döndürür.

```cpp
static constexpr int max_exponent = 0;
```

### <a name="return-value"></a>Dönüş Değeri

En fazla integral taban tabanlı üs gösterilebilir türü.

### <a name="remarks"></a>Açıklamalar

Kayan nokta türleri için anlamlı dönüş üye işlevi. `max_exponent` Türü için değer FLT_MAX_EXP **float**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_max_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum radix-based exponent for type float is:  "
        << numeric_limits<float>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type double is:  "
        << numeric_limits<double>::max_exponent
        << endl;
   cout << "The maximum radix-based exponent for type long double is:  "
        << numeric_limits<long double>::max_exponent
        << endl;
}
```

```Output
The maximum radix-based exponent for type float is:  128
The maximum radix-based exponent for type double is:  1024
The maximum radix-based exponent for type long double is:  1024
```

## <a name="max_exponent10"></a>  numeric_limits::max_exponent10

Bir taban on gücü için harekete geçirildiğinde, kayan nokta türü sınırlı bir değeri temsil edebilir en fazla pozitif tam sayı üssü döndürür.

```cpp
static constexpr int max_exponent10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

En fazla integral taban 10 üs gösterilebilir türü.

### <a name="remarks"></a>Açıklamalar

Kayan nokta türleri için anlamlı dönüş üye işlevi. `max_exponent` Türü için değer FLT_MAX_10 **float**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_max_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum base 10 exponent for type float is:  "
           << numeric_limits<float>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type double is:  "
           << numeric_limits<double>::max_exponent10
           << endl;
   cout << "The maximum base 10 exponent for type long double is:  "
           << numeric_limits<long double>::max_exponent10
           << endl;
}
```

```Output
The maximum base 10 exponent for type float is:  38
The maximum base 10 exponent for type double is:  308
The maximum base 10 exponent for type long double is:  308
```

## <a name="min"></a>  numeric_limits::Min

Bir tür için en düşük normalleştirilmiş değerini döndürür.

```cpp
static constexpr Type min() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Türü için en düşük normalleştirilmiş değeri.

### <a name="remarks"></a>Açıklamalar

En düşük normalleştirilmiş değeri ınt_mın için türüdür **int** ve türünün flt_mın **float**. Dönüş değeri anlamlı varsa [is_bounded](#is_bounded) olduğu **true** veya [is_signed](#is_signed) olduğu **false**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum value for type float is:  "
        << numeric_limits<float>::min( )
        << endl;
   cout << "The minimum value for type double is:  "
        << numeric_limits<double>::min( )
        << endl;
   cout << "The minimum value for type int is:  "
        << numeric_limits<int>::min( )
        << endl;
   cout << "The minimum value for type short int is:  "
        << numeric_limits<short int>::min( )
        << endl;
}
```

```Output
The minimum value for type float is:  1.17549e-038
The minimum value for type double is:  2.22507e-308
The minimum value for type int is:  -2147483648
The minimum value for type short int is:  -32768
```

## <a name="min_exponent"></a>  numeric_limits::min_exponent

Taban sınıfın, gücünü ortaya çıktığında, kayan nokta türü sınırlı bir değeri temsil edebilir en büyük negatif tam sayı üs döndürür.

```cpp
static constexpr int min_exponent = 0;
```

### <a name="return-value"></a>Dönüş Değeri

En düşük integral taban tabanlı üs gösterilebilir türü.

### <a name="remarks"></a>Açıklamalar

Kayan nokta türleri için anlamlı üye işlevidir. `min_exponent` Türü için değer flt_mın_exp **float**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_min_exponent.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum radix-based exponent for type float is:  "
        << numeric_limits<float>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type double is:  "
        << numeric_limits<double>::min_exponent
        << endl;
   cout << "The minimum radix-based exponent for type long double is:  "
         << numeric_limits<long double>::min_exponent
        << endl;
}
```

```Output
The minimum radix-based exponent for type float is:  -125
The minimum radix-based exponent for type double is:  -1021
The minimum radix-based exponent for type long double is:  -1021
```

## <a name="min_exponent10"></a>  numeric_limits::min_exponent10

On sınıfın gücü için oluştuğunda, kayan nokta türü sınırlı bir değeri temsil edebilir en büyük negatif tam sayı üs döndürür.

```cpp
static constexpr int min_exponent10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

En az integral taban 10 üs gösterilebilir türü.

### <a name="remarks"></a>Açıklamalar

Kayan nokta türleri için anlamlı üye işlevidir. `min_exponent10` Türü için değer flt_mın_10_exp **float**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_min_exponent10.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The minimum base 10 exponent for type float is:  "
        << numeric_limits<float>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type double is:  "
        << numeric_limits<double>::min_exponent10
        << endl;
   cout << "The minimum base 10 exponent for type long double is:  "
        << numeric_limits<long double>::min_exponent10
        << endl;
}
```

```Output
The minimum base 10 exponent for type float is:  -37
The minimum base 10 exponent for type double is:  -307
The minimum base 10 exponent for type long double is:  -307
```

## <a name="quiet_nan"></a>  numeric_limits::quiet_NaN

Sessiz bir gösterimi türü için sayı olmayan (NAN) döndürür.

```cpp
static constexpr Type quiet_NaN() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Sessiz bir NAN türünün temsili.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri anlamlı yalnızca [has_quiet_NaN](#has_quiet_nan) olduğu **true**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_quiet_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The quiet NaN for type float is:  "
        << numeric_limits<float>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type int is:  "
        << numeric_limits<int>::quiet_NaN( )
        << endl;
   cout << "The quiet NaN for type long double is:  "
        << numeric_limits<long double>::quiet_NaN( )
        << endl;
}
```

```Output
The quiet NaN for type float is:  1.#QNAN
The quiet NaN for type int is:  0
The quiet NaN for type long double is:  1.#QNAN
```

## <a name="radix"></a>  numeric_limits::radix

İntegral taban döndürür taban bir türü gösterimi için kullanılan, olarak adlandırılır.

```cpp
static constexpr int radix = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Türünün temsili için tam sayı tabanı.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış bir kayan nokta türleri için önceden tanımlanmış tamsayı türleri ve yükseltildiği üs temel veya flt_radıx, 2 tabanıdır.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_radix.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The base for type float is:  "
        << numeric_limits<float>::radix
        << endl;
   cout << "The base for type int is:  "
        << numeric_limits<int>::radix
        << endl;
   cout << "The base for type long double is:  "
        << numeric_limits<long double>::radix
        << endl;
}
```

```Output
The base for type float is:  2
The base for type int is:  2
The base for type long double is:  2
```

## <a name="round_error"></a>  numeric_limits::round_error

Hata türü için izin verilecek en fazla döndürür.

```cpp
static constexpr Type round_error() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Hata türü için izin verilecek en fazla.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_round_error.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The maximum rounding error for type float is:  "
        << numeric_limits<float>::round_error( )
        << endl;
   cout << "The maximum rounding error for type int is:  "
        << numeric_limits<int>::round_error( )
        << endl;
   cout << "The maximum rounding error for type long double is:  "
        << numeric_limits<long double>::round_error( )
        << endl;
}
```

```Output
The maximum rounding error for type float is:  0.5
The maximum rounding error for type int is:  0
The maximum rounding error for type long double is:  0.5
```

## <a name="round_style"></a>  numeric_limits::round_style

Bir kayan nokta değeri tamsayıya yuvarlama uygulaması seçim yapabileceği çeşitli yöntemleri tanımlayan bir değer döndürür.

```cpp
static constexpr float_round_style round_style = round_toward_zero;
```

### <a name="return-value"></a>Dönüş Değeri

Bir değer `float_round_style` stil yuvarlama açıklayan sabit listesi.

### <a name="remarks"></a>Açıklamalar

Üye bir kayan nokta değeri tamsayıya yuvarlama uygulaması seçim yapabileceği çeşitli yöntemleri tanımlayan bir değeri depolar.

Yuvarlak stili, bu uygulama, bu nedenle bile programın farklı bir yuvarlama modu ile başlar, bu değer değişmez kodlanmış zordur.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_round_style.cpp
// compile with: /EHsc
#include <iostream>
#include <float.h>
#include <limits>

using namespace std;

int main( )
{
   cout << "The rounding style for a double type is: "
        << numeric_limits<double>::round_style << endl;
   _controlfp_s(NULL,_RC_DOWN,_MCW_RC );
   cout << "The rounding style for a double type is now: "
        << numeric_limits<double>::round_style << endl;
   cout << "The rounding style for an int type is: "
        << numeric_limits<int>::round_style << endl;
}
```

```Output
The rounding style for a double type is: 1
The rounding style for a double type is now: 1
The rounding style for an int type is: 0
```

## <a name="signaling_nan"></a>  numeric_limits::signaling_NaN

Bir sayı değil (NAN) sinyal temsilini türünü döndürür.

```cpp
static constexpr Type signaling_NaN() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir sinyal NAN türünün temsili.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri anlamlı yalnızca [has_signaling_NaN](#has_signaling_nan) olduğu **true**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_signaling_nan.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The signaling NaN for type float is:  "
        << numeric_limits<float>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type int is:  "
        << numeric_limits<int>::signaling_NaN( )
        << endl;
   cout << "The signaling NaN for type long double is:  "
        << numeric_limits<long double>::signaling_NaN( )
        << endl;
}
```

## <a name="tinyness_before"></a>  numeric_limits::tinyness_before

Bir tür değeri normalleştirilmiş bir değer olarak yuvarlama önce temsil etmek için çok küçük olduğunu anlayabilirsiniz olup olmadığını sınar.

```cpp
static constexpr bool tinyness_before = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** tür yuvarlama önce; küçük değerleri algılayabiliyorsa **false** erişilemiyorsa.

### <a name="remarks"></a>Açıklamalar

Tinyness algılayabilir türleri IEC 559 kayan nokta ifadeleri ile bir seçenek olarak dahil edilen ve uygulanması bazı sonuçları etkileyebilir.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_tinyness_before.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types can detect tinyness before rounding: "
        << numeric_limits<float>::tinyness_before
        << endl;
   cout << "Whether double types can detect tinyness before rounding: "
        << numeric_limits<double>::tinyness_before
        << endl;
   cout << "Whether long int types can detect tinyness before rounding: "
        << numeric_limits<long int>::tinyness_before
        << endl;
   cout << "Whether unsigned char types can detect tinyness before rounding: "
        << numeric_limits<unsigned char>::tinyness_before
        << endl;
}
```

```Output
Whether float types can detect tinyness before rounding: 1
Whether double types can detect tinyness before rounding: 1
Whether long int types can detect tinyness before rounding: 0
Whether unsigned char types can detect tinyness before rounding: 0
```

## <a name="traps"></a>  numeric_limits::traps

Test türü için aritmetik özel durumları yakalama, raporlar uygulanır.

```cpp
static constexpr bool traps = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türü; yakalama uygulanmışsa **false** değilse.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_traps.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "Whether float types have implemented trapping: "
        << numeric_limits<float>::traps
        << endl;
   cout << "Whether double types have implemented trapping: "
        << numeric_limits<double>::traps
        << endl;
   cout << "Whether long int types have implemented trapping: "
        << numeric_limits<long int>::traps
        << endl;
   cout << "Whether unsigned char types have implemented trapping: "
        << numeric_limits<unsigned char>::traps
        << endl;
}
```

```Output
Whether float types have implemented trapping: 1
Whether double types have implemented trapping: 1
Whether long int types have implemented trapping: 0
Whether unsigned char types have implemented trapping: 0
```

## <a name="see-also"></a>Ayrıca bkz.

[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
