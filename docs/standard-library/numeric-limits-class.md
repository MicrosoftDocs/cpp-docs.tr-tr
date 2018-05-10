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
ms.openlocfilehash: 73c8d98157e81f087bf382c3733a2ade909349a6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="numericlimits-class"></a>numeric_limits Sınıfı

Şablon sınıfı yerleşik sayısal türler aritmetik özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
class numeric_limits
```

### <a name="parameters"></a>Parametreler

`Type` Temel öğesi veri türü özellikleri olan test veya sorgulanan.

## <a name="remarks"></a>Açıklamalar

Üst bilgi türleri için açık özelleştirmeleri tanımlar `wchar_t`, `bool`, `char`, `signed char`, `unsigned char`, `short`, `unsigned short`, `int`, `unsigned int`, `long`, `unsigned long`, `float`, `double`, `long double` **,** `long long`, `unsigned long long`, `char16_t`, ve `char32_t`. Bu açık özelleştirmeleri üye için [numeric_limits::is_specialized](#is_specialized) olan `true`, ve tüm ilgili üyeleri anlamlı değerlere sahip. Program ek açık özelleştirmeleri sağlayabilir. Çoğu üye işlevleri sınıfının açıklamak veya olası uygulamaları test `float`.

Rastgele bir uzmanlık için hiçbir üye anlamlı değerlere sahiptir. Anlamlı bir değere sahip olmayan bir üye nesnesini sıfır depolar (veya `false`) ve anlamlı bir değer döndürmeyen bir üye işlevinin döndürdüğü `Type(0)`.

### <a name="static-functions-and-constants"></a>Statik işlevler ve sabitleri

|||
|-|-|
|[denorm_min](#denorm_min)|En küçük sıfır olmayan döndürür değeri normal dışı.|
|[basamak](#digits)|Türü duyarlık kaybı olmadan gösterebilir taban basamak sayısını döndürür.|
|[digits10](#digits10)|Türü duyarlık kaybı olmadan gösterebilir ondalık basamak sayısını döndürür.|
|[Epsilon](#epsilon)|1 ve en küçük değeri arasındaki farkı veri türünü temsil eden 1'den büyük döndürür.|
|[has_denorm](#has_denorm)|Testleri bir türü izin verip değerleri normal dışı.|
|[has_denorm_loss](#has_denorm_loss)|Doğruluk kaybı denormalization kaybı olarak yerine kesin olmayan bir sonucu olarak algılanır olup olmadığını sınar.|
|[has_infinity](#has_infinity)|Pozitif sonsuzluk temsili bir türe sahip olup olmadığını sınar.|
|[has_quiet_NaN](#has_quiet_nan)|Nonsignaling olan bir sayı değil (NAN) bir sessiz temsili bir türe sahip olup olmadığını sınar.|
|[has_signaling_NaN](#has_signaling_nan)|Sayı olmayan (NAN) sinyal temsili bir türe sahip olup olmadığını sınar.|
|[Sonsuz](#infinity)|Varsa bir tür için pozitif sonsuzluk gösterimi.|
|[is_bounded](#is_bounded)|Testleri bir türü temsil değerleri kümesi sınırlıdır.|
|[is_exact](#is_exact)|Bir tür üzerinde yapılan hesaplamaları olduğunda yuvarlama hatalarının testleri boş.|
|[is_iec559](#is_iec559)|Bir tür IEC 559 standartlara uygun sağlayıp sağlamadığını test.|
|[is_integer](#is_integer)|Testleri bir tamsayı temsili bir türe sahip.|
|[is_modulo](#is_modulo)|Bir türü varsa testleri bir gösterimi modül.|
|[is_signed](#is_signed)|Testleri imzalı temsili bir türe sahip.|
|[is_specialized](#is_specialized)|Bir şablon sınıfında tanımlanan bir açık uzmanlık türündeyse testleri `numeric_limits`.|
|[En düşük](#lowest)|En negatif sonlu değeri döndürür.|
|[max](#max)|Bir türe ilişkin maksimum sınırlı değeri döndürür.|
|[max_digits10](#max_digits10)|İki ayrı türü değerleri ayrı ondalık Beyanları olmasını sağlamak için gereken ondalık basamak sayısını döndürür.|
|[max_exponent](#max_exponent)|Sayı tabanını tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir en büyük pozitif tam sayı üs döndürür.|
|[max_exponent10](#max_exponent10)|On tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir en büyük pozitif tam sayı üs döndürür.|
|[Min](#min)|Bir türe ilişkin minimum normalleştirilmiş değeri döndürür.|
|[min_exponent](#min_exponent)|Sayı tabanını tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir maksimum negatif tam sayı üs döndürür.|
|[min_exponent10](#min_exponent10)|On tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir maksimum negatif tam sayı üs döndürür.|
|[quiet_NaN](#quiet_nan)|Bir sessiz gösterimini sayı olmayan (NAN) türü döndürür.|
|[radix](#radix)|İntegral taban döndürür taban bir türü gösterimi için kullanılan, olarak adlandırılır.|
|[round_error](#round_error)|Hata türü için izin verilecek en fazla döndürür.|
|[round_style](#round_style)|Kayan nokta değer bir tamsayı değerine yuvarlama uygulaması seçebileceğiniz çeşitli yöntemleri açıklayan bir değer döndürür.|
|[signaling_NaN](#signaling_nan)|Sayı olmayan (NAN) sinyal temsilini türü döndürür.|
|[tinyness_before](#tinyness_before)|Bir tür değeri yuvarlama önce normalleştirilmiş değeri olarak göstermek için çok küçük olduğunu anlayabilirsiniz olup olmadığını sınar.|
|[Tuzaklar](#traps)|Testleri olup, yakalama aritmetik özel durumları raporları için bir tür uygulanır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<sınırları >

**Namespace:** std

## <a name="denorm_min"></a>  numeric_limits::denorm_min

En küçük sıfır olmayan döndürür değeri normal dışı.

```cpp
static Type denorm_min() throw();
```

### <a name="return-value"></a>Dönüş Değeri

En küçük sıfır olmayan Normalleştirilmemiş değeri.

### <a name="remarks"></a>Açıklamalar

`long double` aynı **çift** C++ derleyicisi'ne yönelik.

Aynı tür için en düşük değer işlevi döndürür olarak [min](#min) varsa [has_denorm](#has_denorm) eşit değil **denorm_present**.

### <a name="example"></a>Örnek

```cpp
// numeric_limits_denorm_min.cpp
// compile with: /EHsc
#include <iostream>
#include <limits>

using namespace std;

int main( )
{
   cout << "The smallest nonzero denormalized value\n for float "
        << "objects is: " << numeric_limits<float>::denorm_min( )
        << endl;
   cout << "The smallest nonzero denormalized value\n for double "
        << "objects is: " << numeric_limits<double>::denorm_min( )
        << endl;
   cout << "The smallest nonzero denormalized value\n for long double "
        << "objects is: " << numeric_limits<long double>::denorm_min( )
        << endl;

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

Türü duyarlık kaybı olmadan gösterebilir taban basamak sayısını döndürür.

```cpp
static const int digits = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Türü duyarlık kaybı olmadan gösterebilir taban basamak sayısı.

### <a name="remarks"></a>Açıklamalar

Üye türü önceden tanımlanmış tamsayı türü için hiçbir oturum bit dışında BITS sayısı olan değişiklik gösterebilir taban basamak sayısı veya önceden tanımlanmış bir kayan nokta türü için Mantis basamak sayısı depolar.

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

Türü duyarlık kaybı olmadan gösterebilir ondalık basamak sayısını döndürür.

```cpp
static const int digits10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Türü duyarlık kaybı olmadan gösterebilir ondalık basamak sayısı.

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

İşlevi 1 ve en küçük değeri arasındaki farkı veri türü için gösterilebilir 1'den büyük olarak döndürür.

```cpp
static Type epsilon() throw();
```

### <a name="return-value"></a>Dönüş Değeri

1 ve veri türü için gösterilebilir 1'den büyük en küçük değeri arasındaki fark.

### <a name="remarks"></a>Açıklamalar

Değer türü için flt_epsılon **float**. `epsilon` en küçük pozitif kayan noktalı sayı türüdür için *N* şekilde *N* + `epsilon` + *N* gösterilebilir değil.

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
        << "value greater than 1\n for float objects is: "
        << numeric_limits<float>::epsilon( )
        << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1\n for double objects is: "
        << numeric_limits<double>::epsilon( )
        << endl;
   cout << "The difference between 1 and the smallest "
        << "value greater than 1\n for long double objects is: "
        << numeric_limits<long double>::epsilon( )
        << endl;
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

Testleri bir türü izin verip değerleri normal dışı.

```cpp
static const float_denorm_style has_denorm = denorm_absent;
```

### <a name="return-value"></a>Dönüş Değeri

Bir numaralandırma değeri türü **const**`float_denorm_style`, belirten olup türü Normalleştirilmemiş değerlere izin verir.

### <a name="remarks"></a>Açıklamalar

Üye depoları **denorm_present** normal dışı bir kayan nokta türü değerleri için etkili bir şekilde üs BITS değişken sayısı.

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

Doğruluk kaybı denormalization kaybı olarak yerine kesin olmayan bir sonucu olarak algılanır olup olmadığını sınar.

```cpp
static const bool has_denorm_loss = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** doğruluğu kaybı denormalization kaybedilmiş; algılanırsa, **false** değilse.

### <a name="remarks"></a>Açıklamalar

True değeri doğruluğu Normalleştirilmemiş bir sonucu olarak (çok normalleştirilmiş değeri olarak göstermek için küçük) teslim edilir veya kesin olmayan nedeniyle kesildi olup olmadığını belirleyen bir tür için üye depolar (aynı sonucunda üs sınırlamaları edilmez Aralık ve kesinliği) bazı sonuçlarını etkileyebilecek IEC 559 kayan nokta temsili bir seçenek.

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

Pozitif sonsuzluk temsili bir türe sahip olup olmadığını sınar.

```cpp
static const bool has_infinity = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** pozitif sonsuzluk; temsili türündeyse **false** değilse.

### <a name="remarks"></a>Açıklamalar

Üye döndürür **true** varsa [is_iec559](#is_iec559) olan **doğru**.

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
static const bool has_quiet_NaN = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** varsa **türü** sessiz NAN; temsili sahip **false** değilse.

### <a name="remarks"></a>Açıklamalar

Sessiz NAN bir deyimde varlığını işaret etmiyor olmayan bir sayı kodlama ' dir. Dönüş değeri **true** varsa [is_iec559](#is_iec559) doğrudur.

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

Sayı olmayan (NAN) sinyal temsili bir türe sahip olup olmadığını sınar.

```cpp
static const bool has_signaling_NaN = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** sinyal NAN; temsili türündeyse **false** değilse.

### <a name="remarks"></a>Açıklamalar

Sinyal NAN bir deyimde varlığını sinyalleri olmayan bir sayı kodlama ' dir. Dönüş değeri **true** varsa [is_iec559](#is_iec559) doğrudur.

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

Varsa bir tür için pozitif sonsuzluk gösterimi.

```cpp
static Type infinity() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Varsa bir tür için pozitif sonsuzluk gösterimi.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri anlamlıdır yalnızca [has_infinity](#has_infinity) olan **doğru**.

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

Testleri bir türü temsil değerleri kümesi sınırlıdır.

```cpp
static const bool is_bounded = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** gösterilebilir değerleri; sınırlanmış bir dizi türündeyse **false** değilse.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış tüm türleri gösterilebilir değerleri sınırlanmış bir dizi ve dönmek **doğru**.

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

Bir tür üzerinde yapılan hesaplamaları olduğunda yuvarlama hatalarının testleri boş.

```cpp
static const bool is_exact = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** hesaplamaları hataları; yuvarlama boş olması durumunda **false** değilse.

### <a name="remarks"></a>Açıklamalar

Tüm önceden tanımlanmış tamsayı türleri değerleri için tam Beyanları ve dönüş **false**. Sabit noktalı veya rasyonel gösterimi de tam olarak kabul edilir, ancak bir kayan nokta temsili değildir.

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

Bir tür IEC 559 standartlara uygun sağlayıp sağlamadığını test.

```cpp
static const bool is_iec559 = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türü IEC 559 standartlarına; uyuyorsa **false** değilse.

### <a name="remarks"></a>Açıklamalar

IEC 559 kayan nokta değerlerini temsil eden bir uluslararası standart ve olarak da bilinen IEEE 754 ABD.

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

Testleri bir tamsayı temsili bir türe sahip.

```cpp
static const bool is_integer = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** bir tamsayı temsili; türündeyse **false** değilse.

### <a name="remarks"></a>Açıklamalar

Tüm önceden tanımlanmış tamsayı türleri bir tamsayı temsili sahip.

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

Testleri bir **türü** sahip bir modül gösterimi.

```cpp
static const bool is_modulo = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** türündeyse bir gösterimi; modül **false** değilse.

### <a name="remarks"></a>Açıklamalar

Gösterimi modulo açık bir gösterimi tüm sonuçları bazı değeri burada azaltılır. Tüm önceden tanımlanmış işaretsiz tamsayı türlerine sahip bir modül gösterimi.

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

Testleri imzalı temsili bir türe sahip.

```cpp
static const bool is_signed = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** imzalı gösterimi; türündeyse **false** değilse.

### <a name="remarks"></a>Açıklamalar

Üye tüm önceden tanımlanmış kayan nokta ve imzalı tamsayı türleri için geçerli bir imzalı gösterimi olan bir türü için true depolar.

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

Bir şablon sınıfında tanımlanan bir açık uzmanlık türündeyse testleri `numeric_limits`.

```cpp
static const bool is_specialized = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** şablonu sınıfında; tanımlanmış bir açık uzmanlık türündeyse **false** değilse.

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı için tanımlanmış bir açık uzmanlık işaretçileri dışındaki tüm skaler türlerine sahip `numeric_limits`.

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
static Type lowest() throw();
```

### <a name="return-value"></a>Dönüş Değeri

En negatif sonlu değeri döndürür.

### <a name="remarks"></a>Açıklamalar

Türü için en negatif sınırlı değeri döndürür (normalde `min()` tamsayı türleri ve `-max()` kayan nokta türleri için). Dönüş değeri anlamlıdır varsa `is_bounded` olan `true`.

## <a name="max"></a>  numeric_limits::Max

Bir türe ilişkin maksimum sınırlı değeri döndürür.

```cpp
static Type max() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Bir türe ilişkin maksimum sınırlı değeri.

### <a name="remarks"></a>Açıklamalar

En büyük sınırlı değer INT_MAX türüdür `int` ve FLT_MAX türü için **float**. Dönüş değeri anlamlıdır varsa [is_bounded](#is_bounded) olan **doğru**.

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

Türünde iki farklı değerler ayrı ondalık Beyanları sahip olduğunuzdan emin olmak için gerekli ondalık basamak sayısını döndürür.

```cpp
static int max_digits10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

İki ayrı türü değerleri ayrı ondalık Beyanları olduğundan emin olmak için gerekli olan ondalık basamak sayısını döndürür.

### <a name="remarks"></a>Açıklamalar

Üye türü iki farklı değerleri ayrı ondalık Beyanları sahip olduğunuzdan emin olmak için gerekli ondalık basamak sayısı depolar.

## <a name="max_exponent"></a>  numeric_limits::max_exponent

Sayı tabanını tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir en büyük pozitif tam sayı üs döndürür.

```cpp
static const int max_exponent = 0;
```

### <a name="return-value"></a>Dönüş Değeri

En büyük tam sayı taban tabanlı üs gösterilebilir türüne göre.

### <a name="remarks"></a>Açıklamalar

Üye işlevi dönüş yalnızca kayan nokta türleri için anlamlıdır. `max_exponent` FLT_MAX_EXP türüyle ilgili değer **float**.

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

On tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir en büyük pozitif tam sayı üs döndürür.

```cpp
static const int max_exponent10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

En büyük tam sayı temel 10 üs gösterilebilir türüne göre.

### <a name="remarks"></a>Açıklamalar

Üye işlevi dönüş yalnızca kayan nokta türleri için anlamlıdır. `max_exponent` FLT_MAX_10 türüyle ilgili değer **float**.

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

Bir türe ilişkin minimum normalleştirilmiş değeri döndürür.

```cpp
static Type min() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Türü için en düşük normalleştirilmiş değeri.

### <a name="remarks"></a>Açıklamalar

Minimum normalleştirilmiş değeri ınt_mın türüdür `int` ve flt_mın türü için `float`. Dönüş değeri anlamlıdır varsa [is_bounded](#is_bounded) olan `true` veya [is_signed](#is_signed) olan `false`.

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

Sayı tabanını tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir maksimum negatif tam sayı üs döndürür.

```cpp
static const int min_exponent = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Minimum integral taban tabanlı üs gösterilebilir türüne göre.

### <a name="remarks"></a>Açıklamalar

Üye işlevi yalnızca kayan nokta türleri için anlamlıdır. `min_exponent` Flt_mın_exp türüyle ilgili değer **float**.

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

On tabanının, güç oluştuğunda kayan nokta türü sınırlı bir değer olarak gösterebilir maksimum negatif tam sayı üs döndürür.

```cpp
static const int min_exponent10 = 0;
```

### <a name="return-value"></a>Dönüş Değeri

En küçük tamsayı temel 10 üs gösterilebilir türüne göre.

### <a name="remarks"></a>Açıklamalar

Üye işlevi yalnızca kayan nokta türleri için anlamlıdır. `min_exponent10` Flt_mın_10_exp türüyle ilgili değer **float**.

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

Bir sessiz gösterimini sayı olmayan (NAN) türü döndürür.

```cpp
static Type quiet_NaN() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Türü için sessiz NAN gösterimi.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri anlamlıdır yalnızca [has_quiet_NaN](#has_quiet_nan) olan **doğru**.

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
static const int radix = 0;
```

### <a name="return-value"></a>Dönüş Değeri

Tam sayı tabanı türü gösterimi için kullanılır.

### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış kayan nokta türleri için önceden tanımlanmış tamsayı türleri ve üs yükseltildiği temel veya flt_radıx, 2 tabanıdır.

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
static Type round_error() throw();
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

Kayan nokta değer bir tamsayı değerine yuvarlama uygulaması seçebileceğiniz çeşitli yöntemleri açıklayan bir değer döndürür.

```cpp
static const float_round_style round_style = round_toward_zero;
```

### <a name="return-value"></a>Dönüş Değeri

Arasında bir değer `float_round_style` yuvarlama açıklar numaralandırma stili.

### <a name="remarks"></a>Açıklamalar

Üye bir tamsayı değeri kayan noktalı bir sayıyı yuvarlama uygulaması seçebileceğiniz çeşitli yöntemleri açıklayan bir değerini depolar.

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

Sayı olmayan (NAN) sinyal temsilini türü döndürür.

```cpp
static Type signaling_NaN() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Türü için sinyal NAN gösterimi.

### <a name="remarks"></a>Açıklamalar

Dönüş değeri anlamlıdır yalnızca [has_signaling_NaN](#has_signaling_nan) olan **doğru**.

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

Bir tür değeri yuvarlama önce normalleştirilmiş değeri olarak göstermek için çok küçük olduğunu anlayabilirsiniz olup olmadığını sınar.

```cpp
static const bool tinyness_before = false;
```

### <a name="return-value"></a>Dönüş Değeri

`true` Yuvarlama önce küçük değerleri türü tespit edebilirsiniz `false` başaramazsa.

### <a name="remarks"></a>Açıklamalar

Tinyness algılayabilir türleri IEC 559 kayan nokta temsili bir seçenek olarak dahil ve kendi uygulama bazı sonuçları etkileyebilir.

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

Testleri olup, yakalama aritmetik özel durumları raporları için bir tür uygulanır.

```cpp
static const bool traps = false;
```

### <a name="return-value"></a>Dönüş Değeri

**doğru** yakalama türü; uygulanırsa **false** değilse.

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
