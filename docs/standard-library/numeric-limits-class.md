---
title: numeric_limits Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 5373bd6a99605f5a63fb6aa2ed6de50c12b1c8f1
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78876041"
---
# <a name="numeric_limits-class"></a>numeric_limits Sınıfı

Sınıf şablonu, yerleşik sayısal türlerin aritmetik özelliklerini açıklar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class Type>
    class numeric_limits
```

### <a name="parameters"></a>Parametreler

*Tür*\
Özellikleri test edilmiş ya da sorgulanan veya ayarlanan temel öğe veri türü. *Tür* Ayrıca **const**, **volatile**veya **const geçici**olarak da yapılandırılabilir.

## <a name="remarks"></a>Açıklamalar

Üst bilgi **wchar_t**, **bool**, **char**, **imzalanmış char**, **işaretsiz char**, **Short**, **işaretsiz Short**, **int**, **işaretsiz int**, **long**, **işaretsiz Long**, **float**, **Double**, **Long Double**, **Long Long**, **unsigned long long**, **char16_t**ve **char32_t**türleri için açık uzmanlık tanımlar. Bu açık uzmanlık için, üye [numeric_limits:: is_specialized](#is_specialized) **true**ve ilgili tüm üyelerin anlamlı değerleri vardır. Program ek açık uzmanlık sağlayabilir. Sınıfının birçok üye işlevi, **kayan**nesnelerin olası uygulamalarını betimler veya test et.

Rastgele bir özelleşme için hiçbir üyenin anlamlı değerleri yoktur. Anlamlı bir değere sahip olmayan bir üye nesnesi sıfır (veya **yanlış**) ve anlamlı bir değer döndürmeyen bir üye işlevi `Type(0)`döndürür.

## <a name="static-functions-and-constants"></a>Statik Işlevler ve sabitler

|||
|-|-|
|[denorm_min](#denorm_min)|Sıfır dışında Normalleştirilmemiş değeri döndürür.|
|[54](#digits)|Türün duyarlık kaybı olmadan temsil etmesi için kullanılan sayı sayısını döndürür.|
|[digits10](#digits10)|Türün duyarlık kaybı olmadan temsil edilebilmesi için ondalık basamakların sayısını döndürür.|
|[Upsilon](#epsilon)|1 ile veri türünün temsil edilebilmesi için 1 ' den büyük olan en küçük değer arasındaki farkı döndürür.|
|[has_denorm](#has_denorm)|Bir türün Normalleştirilmemiş değerlerin izin verip içermediğini sınar.|
|[has_denorm_loss](#has_denorm_loss)|Doğruluk kaybı olup olmadığını test etmek yerine kesin olmayan bir kayıp olarak algılanıp algılanmadığını sınar.|
|[has_infinity](#has_infinity)|Bir türün pozitif sonsuzluk gösterimine sahip olup olmadığını sınar.|
|[has_quiet_NaN](#has_quiet_nan)|Bir türün, sessiz olmayan bir sayı (NAN) için bir gösterimine sahip olup olmadığını test eder ve sinyal vermez.|
|[has_signaling_NaN](#has_signaling_nan)|Bir türün sinyal için bir sayı değil (NAN) bir gösterimine sahip olup olmadığını sınar.|
|[sonsuz](#infinity)|Varsa, bir tür için pozitif sonsuzluk temsili.|
|[is_bounded](#is_bounded)|Bir türün temsil edilebilmesi için değer kümesinin sınırlı olup olmadığını test eder.|
|[is_exact](#is_exact)|Bir tür üzerinde yapılan hesaplamaların yuvarlama hatalarının boş olup olmadığını sınar.|
|[is_iec559](#is_iec559)|Bir türün ıEC 559 standartlarına uygun olup olmadığını sınar.|
|[is_integer](#is_integer)|Bir türün tamsayı gösterimine sahip olup olmadığını sınar.|
|[is_modulo](#is_modulo)|Bir türün bir modül gösterimine sahip olup olmadığını sınar.|
|[is_signed](#is_signed)|Bir türün işaretli bir temsili olup olmadığını sınar.|
|[is_specialized](#is_specialized)|Bir türün, Sınıf şablonunda `numeric_limits`tanımlanmış bir açık özelleşmeye sahip olup olmadığını sınar.|
|[Minimum](#lowest)|En negatif sonlu değeri döndürür.|
|[Biçimlendir](#max)|Bir tür için en fazla sonlu değeri döndürür.|
|[max_digits10](#max_digits10)|Türün iki farklı değerinin farklı ondalık gösterimlerine sahip olduğundan emin olmak için gereken ondalık basamak sayısını döndürür.|
|[max_exponent](#max_exponent)|Bu kuvvete bir taban tabanı oluşturulduğunda kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en fazla pozitif integral üstel değeri döndürür.|
|[max_exponent10](#max_exponent10)|Bir taban on bu kuvvete döndürüldüğünde kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en büyük pozitif integral üstel değeri döndürür.|
|[Min](#min)|Bir tür için en küçük normalleştirilmiş değeri döndürür.|
|[min_exponent](#min_exponent)|Bu kuvvete bir taban tabanı oluşturulduğunda kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en büyük negatif integral üstel değeri döndürür.|
|[min_exponent10](#min_exponent10)|On 'un bir tabanı bu kuvvete oluşturulduğunda kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en büyük negatif integral üssün birini döndürür.|
|[quiet_NaN](#quiet_nan)|Tür için sessiz sayı değil (NAN) gösterimini döndürür.|
|[taban](#radix)|Bir türün temsili için kullanılan, Radix olarak adlandırılan integral tabanını döndürür.|
|[round_error](#round_error)|Tür için en fazla yuvarlama hatası döndürür.|
|[round_style](#round_style)|Bir uygulamanın kayan nokta değerini bir tamsayı değerine yuvarlamak için seçebileceği çeşitli yöntemleri açıklayan bir değer döndürür.|
|[signaling_NaN](#signaling_nan)|Tür için bir sinyal (NAN) olarak bir sinyal gösterimini döndürür.|
|[tinyness_before](#tinyness_before)|Bir türün, yuvarlama yapmadan önce normalleştirilmiş bir değer olarak temsil edilebilmesi için çok küçük olup olmadığını test eder.|
|[tuzak](#traps)|Aritmetik özel durumlarla rapor veren yakalamaya bir tür için uygulanıp uygulanmadığını sınar.|

### <a name="denorm_min"></a>denorm_min

Sıfır dışında Normalleştirilmemiş değeri döndürür.

```cpp
static constexpr Type denorm_min() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Sıfırdan büyük olmayan en küçük değer.

#### <a name="remarks"></a>Açıklamalar

**Long Double** , C++ derleyici için **Double** ile aynıdır.

İşlevi, türü için en küçük değeri döndürür, bu, [has_denorm](#has_denorm) `denorm_present`eşit değilse [Min](#min) ile aynıdır.

#### <a name="example"></a>Örnek

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

### <a name="digits"></a>54

Türün duyarlık kaybı olmadan temsil etmesi için kullanılan sayı sayısını döndürür.

```cpp
static constexpr int digits = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türün duyarlık kaybı olmadan temsil etmesi için kullanılan sayı.

#### <a name="remarks"></a>Açıklamalar

Üye, türün değişiklik yapılmadan temsil edilebilmesi için, önceden tanımlanmış bir tamsayı türü için herhangi bir imza bitden başka bit sayısı veya önceden tanımlanmış bir kayan nokta türü için Mantis basamak sayısı olan değer olmadan temsil edebilir.

#### <a name="example"></a>Örnek

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

### <a name="digits10"></a>digits10

Türün duyarlık kaybı olmadan temsil edilebilmesi için ondalık basamakların sayısını döndürür.

```cpp
static constexpr int digits10 = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türün duyarlık kaybı olmadan temsil etmesi için ondalık basamakların sayısı.

#### <a name="example"></a>Örnek

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

### <a name="epsilon"></a>Upsilon

İşlevi, 1 ile veri türü için gösterilebilir olan 1 ' den büyük en küçük değer arasındaki farkı döndürür.

```cpp
static constexpr Type epsilon() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

1 ile en küçük değer arasındaki fark, veri türü için gösterilebilir tablo olan 1 ' den büyük.

#### <a name="remarks"></a>Açıklamalar

Değer **float**türü için FLT_EPSILON. bir tür için `epsilon`, en küçük pozitif kayan nokta sayısıdır *n* * + `epsilon`*  + *n* gösterilemeyen tablo.

#### <a name="example"></a>Örnek

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

### <a name="has_denorm"></a>has_denorm

Bir türün Normalleştirilmemiş değerlerin izin verip içermediğini sınar.

```cpp
static constexpr float_denorm_style has_denorm = denorm_absent;
```

#### <a name="return-value"></a>Dönüş Değeri

Türün Normalleştirilmemiş değerlere izin verip içermediğini gösteren **const**`float_denorm_style`türünde bir sabit listesi değeri.

#### <a name="remarks"></a>Açıklamalar

Üye, daha fazla sayıda üs bit, etkin olmayan değerler içeren kayan noktalı bir tür için `denorm_present` depolar.

#### <a name="example"></a>Örnek

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

### <a name="has_denorm_loss"></a>has_denorm_loss

Doğruluk kaybı olup olmadığını test etmek yerine kesin olmayan bir kayıp olarak algılanıp algılanmadığını sınar.

```cpp
static constexpr bool has_denorm_loss = false;
```

#### <a name="return-value"></a>Dönüş Değeri

doğruluk kaybı, Normalleştirilmemiş bir kayıp olarak algılanırsa **doğru** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Üye, bir değerin kesinlik kaybı olup olmadığını belirleyen bir tür için true olarak saklanır (normalleştirilmiş bir değer olarak temsil edilebilmesi için çok küçük) ya da tam olmadığından (bir sonuçtan büyük bir kısıtlama kısıtlamalarına tabi olmadığı için de aynı değildir). Aralık ve duyarlık), bazı sonuçları etkileyebilecek ıEC 559 kayan nokta temsillerine sahip bir seçenek.

#### <a name="example"></a>Örnek

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

### <a name="has_infinity"></a>has_infinity

Bir türün pozitif sonsuzluk gösterimine sahip olup olmadığını sınar.

```cpp
static constexpr bool has_infinity = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün pozitif sonsuz için bir temsili varsa **true** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

[İs_iec559](#is_iec559) **true**ise üye **true** döndürür.

#### <a name="example"></a>Örnek

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

### <a name="has_quiet_nan"></a>has_quiet_NaN

Bir türün, sessiz olmayan bir sayı (NAN) için bir gösterimine sahip olup olmadığını test eder ve sinyal vermez.

```cpp
static constexpr bool has_quiet_NaN = false;
```

#### <a name="return-value"></a>Dönüş Değeri

**türün** BIR sessiz Nan gösterimi varsa **doğru** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Sessiz NAN bir sayı değil, bir ifadede varlığını işaret eden bir kodlamadır. [İs_iec559](#is_iec559) true ise, dönüş değeri **true** olur.

#### <a name="example"></a>Örnek

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

### <a name="has_signaling_nan"></a>has_signaling_NaN

Bir türün sinyal için bir sayı değil (NAN) bir gösterimine sahip olup olmadığını sınar.

```cpp
static constexpr bool has_signaling_NaN = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün sinyal NAN için bir temsili varsa **true** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Bir sinyal NAN bir sayı değil, bir ifadede varlığını işaret eden bir kodlamadır. [İs_iec559](#is_iec559) true ise, dönüş değeri **true** olur.

#### <a name="example"></a>Örnek

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

### <a name="infinity"></a>sonsuz

Varsa, bir tür için pozitif sonsuzluk temsili.

```cpp
static constexpr Type infinity() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Varsa, bir tür için pozitif sonsuzluk temsili.

#### <a name="remarks"></a>Açıklamalar

Dönüş değeri yalnızca [has_infinity](#has_infinity) **true**olduğunda anlamlı olur.

#### <a name="example"></a>Örnek

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

### <a name="is_bounded"></a>is_bounded

Bir türün temsil edilebilmesi için değer kümesinin sınırlı olup olmadığını test eder.

```cpp
static constexpr bool is_bounded = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün sınırlanmış bir gösterilemez tablo değeri kümesi varsa **doğru** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış tüm türlerin sınırlı bir gösterilemez tablo değerleri kümesi vardır ve **doğru**döndürür.

#### <a name="example"></a>Örnek

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

### <a name="is_exact"></a>is_exact

Bir tür üzerinde yapılan hesaplamaların yuvarlama hatalarının boş olup olmadığını sınar.

```cpp
static constexpr bool is_exact = false;
```

#### <a name="return-value"></a>Dönüş Değeri

hesaplamalar, yuvarlama hatalarından muaf değilse **doğru** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış tüm tamsayı türlerinin değerleri için tam gösterimleri vardır ve **false**döndürür. Sabit noktalı veya Rational temsili de tam olarak değerlendirilir, ancak kayan nokta temsili değildir.

#### <a name="example"></a>Örnek

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

### <a name="is_iec559"></a>is_iec559

Bir türün ıEC 559 standartlarına uygun olup olmadığını sınar.

```cpp
static constexpr bool is_iec559 = false;
```

#### <a name="return-value"></a>Dönüş Değeri

tür, ıEC 559 standartlarına uyuyorsa **true** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

IEC 559, kayan nokta değerlerini temsil eden uluslararası bir standarttır ve ABD 'de IEEE 754 olarak da bilinir.

#### <a name="example"></a>Örnek

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

### <a name="is_integer"></a>is_integer

Bir türün tamsayı gösterimine sahip olup olmadığını sınar.

```cpp
static constexpr bool is_integer = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün bir tamsayı temsili varsa **doğru** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Önceden tanımlanmış tüm tamsayı türlerinin bir tamsayı temsili vardır.

#### <a name="example"></a>Örnek

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

### <a name="is_modulo"></a>is_modulo

Bir **türün** bir modül gösterimine sahip olup olmadığını sınar.

```cpp
static constexpr bool is_modulo = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün bir mod gösterimi varsa **doğru** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Modül temsili, tüm sonuçların azaldığı bir gösterimdir. Önceden tanımlanmış tüm işaretsiz tamsayı türleri bir mod gösterimine sahiptir.

#### <a name="example"></a>Örnek

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

### <a name="is_signed"></a>is_signed

Bir türün işaretli bir temsili olup olmadığını sınar.

```cpp
static constexpr bool is_signed = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün işaretli bir temsili varsa **doğru** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

Üye, önceden tanımlanmış tüm kayan nokta ve imzalı tamsayı türleri için olan işaretli bir temsili olan bir tür için true değerini depolar.

#### <a name="example"></a>Örnek

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

### <a name="is_specialized"></a>is_specialized

Bir türün, Sınıf şablonunda `numeric_limits`tanımlanmış bir açık özelleşmeye sahip olup olmadığını sınar.

```cpp
static constexpr bool is_specialized = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün, Sınıf şablonunda tanımlanmış bir açık özelleştirmesi varsa **true** ; değilse **yanlış** .

#### <a name="remarks"></a>Açıklamalar

İşaretçilerin dışındaki tüm skaler türler, sınıf şablonu için tanımlanan açık bir özelleştirmeye sahiptir `numeric_limits`.

#### <a name="example"></a>Örnek

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

### <a name="lowest"></a>Minimum

En negatif sonlu değeri döndürür.

```cpp
static constexpr Type lowest() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

En negatif sonlu değeri döndürür.

#### <a name="remarks"></a>Açıklamalar

Tür için en negatif sonlu değeri döndürür (genellikle tamsayı türleri için `min()` ve kayan nokta türleri için `-max()`). `is_bounded` **true**ise, dönüş değeri anlamlı olur.

### <a name="max"></a>Biçimlendir

Bir tür için en fazla sonlu değeri döndürür.

```cpp
static constexpr Type max() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Bir tür için maksimum sonlu değer.

#### <a name="remarks"></a>Açıklamalar

Maksimum sonlu değer, Type türü için INT_MAX **ve** **float**türü için FLT_MAX. [İs_bounded](#is_bounded) **true**ise, dönüş değeri anlamlı olur.

#### <a name="example"></a>Örnek

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

### <a name="max_digits10"></a>max_digits10

Türün iki farklı değerinin farklı ondalık gösterimlerine sahip olduğundan emin olmak için gereken ondalık basamak sayısını döndürür.

```cpp
static constexpr int max_digits10 = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türün iki farklı değerinin farklı ondalık gösterimlerine sahip olduğundan emin olmak için gereken ondalık basamak sayısını döndürür.

#### <a name="remarks"></a>Açıklamalar

Üye, türün iki farklı değerinin farklı ondalık gösterimlerine sahip olduğundan emin olmak için gereken ondalık basamak sayısını depolar.

### <a name="max_exponent"></a>max_exponent

Bu kuvvete bir taban tabanı oluşturulduğunda kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en fazla pozitif integral üstel değeri döndürür.

```cpp
static constexpr int max_exponent = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türe göre en büyük integral Radix tabanlı üs tablosu.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi dönüşü yalnızca kayan nokta türleri için anlamlıdır. `max_exponent` **float**türü için FLT_MAX_EXP değeridir.

#### <a name="example"></a>Örnek

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

### <a name="max_exponent10"></a>max_exponent10

Bir taban on bu kuvvete döndürüldüğünde kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en büyük pozitif integral üstel değeri döndürür.

```cpp
static constexpr int max_exponent10 = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türe göre en büyük integral tabanı 10 üs değeri.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi dönüşü yalnızca kayan nokta türleri için anlamlıdır. `max_exponent` **float**türü için FLT_MAX_10 değeridir.

#### <a name="example"></a>Örnek

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

### <a name="min"></a>Min

Bir tür için en küçük normalleştirilmiş değeri döndürür.

```cpp
static constexpr Type min() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür için en küçük normalleştirilmiş değer.

#### <a name="remarks"></a>Açıklamalar

En küçük normalleştirilmiş değer, Type türü için **INT_MIN ve** **float**türü için FLT_MIN. [İs_bounded](#is_bounded) **true** ise veya [is_signed](#is_signed) **false**ise, dönüş değeri anlamlı olur.

#### <a name="example"></a>Örnek

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

### <a name="min_exponent"></a>min_exponent

Bu kuvvete bir taban tabanı oluşturulduğunda kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en büyük negatif integral üstel değeri döndürür.

```cpp
static constexpr int min_exponent = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türe göre en küçük integral yarıçapx tabanlı üs değer tablosu.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi yalnızca kayan nokta türleri için anlamlıdır. `min_exponent` **float**türü için FLT_MIN_EXP değeridir.

#### <a name="example"></a>Örnek

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

### <a name="min_exponent10"></a>min_exponent10

On 'un bir tabanı bu kuvvete oluşturulduğunda kayan nokta türünün sonlu bir değer olarak temsil edilebilmesi için en büyük negatif integral üssün birini döndürür.

```cpp
static constexpr int min_exponent10 = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türe göre en küçük integral tabanı 10 üs değeri.

#### <a name="remarks"></a>Açıklamalar

Üye işlevi yalnızca kayan nokta türleri için anlamlıdır. `min_exponent10` **float**türü için FLT_MIN_10_EXP değeridir.

#### <a name="example"></a>Örnek

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

### <a name="quiet_nan"></a>quiet_NaN

Tür için sessiz sayı değil (NAN) gösterimini döndürür.

```cpp
static constexpr Type quiet_NaN() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür için sessiz NAN gösterimi.

#### <a name="remarks"></a>Açıklamalar

Dönüş değeri yalnızca [has_quiet_NaN](#has_quiet_nan) **true**olduğunda anlamlı olur.

#### <a name="example"></a>Örnek

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

### <a name="radix"></a>taban

Bir türün temsili için kullanılan, Radix olarak adlandırılan integral tabanını döndürür.

```cpp
static constexpr int radix = 0;
```

#### <a name="return-value"></a>Dönüş Değeri

Türün temsili için integral tabanı.

#### <a name="remarks"></a>Açıklamalar

Temel, önceden tanımlı tamsayı türleri için 2, üs 'un oluşturulduğu taban veya FLT_RADIX, önceden tanımlanmış kayan nokta türleri için ise.

#### <a name="example"></a>Örnek

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

### <a name="round_error"></a>round_error

Tür için en fazla yuvarlama hatası döndürür.

```cpp
static constexpr Type round_error() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür için en fazla yuvarlama hatası.

#### <a name="example"></a>Örnek

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

### <a name="round_style"></a>round_style

Bir uygulamanın kayan nokta değerini bir tamsayı değerine yuvarlamak için seçebileceği çeşitli yöntemleri açıklayan bir değer döndürür.

```cpp
static constexpr float_round_style round_style = round_toward_zero;
```

#### <a name="return-value"></a>Dönüş Değeri

`float_round_style` numaralandırmasından yuvarlama stilini açıklayan bir değer.

#### <a name="remarks"></a>Açıklamalar

Üye, bir uygulamanın kayan nokta değerini bir tamsayı değerine yuvarlamak için seçebileceği çeşitli yöntemleri açıklayan bir değer depolar.

Bu uygulamada yuvarlak stil sabit olarak kodlanmıştır, bu nedenle program farklı bir yuvarlama moduyla başlıyorsa bile bu değer değişmez.

#### <a name="example"></a>Örnek

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

### <a name="signaling_nan"></a>signaling_NaN

Tür için bir sinyal (NAN) olarak bir sinyal gösterimini döndürür.

```cpp
static constexpr Type signaling_NaN() throw();
```

#### <a name="return-value"></a>Dönüş Değeri

Tür için bir sinyal NAN gösterimi.

#### <a name="remarks"></a>Açıklamalar

Dönüş değeri yalnızca [has_signaling_NaN](#has_signaling_nan) **true**olduğunda anlamlı olur.

#### <a name="example"></a>Örnek

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

### <a name="tinyness_before"></a>tinyness_before

Bir türün, yuvarlama yapmadan önce normalleştirilmiş bir değer olarak temsil edilebilmesi için çok küçük olup olmadığını test eder.

```cpp
static constexpr bool tinyness_before = false;
```

#### <a name="return-value"></a>Dönüş Değeri

türün yuvarlamadan önce küçük değerleri algılayabilmesi için **true** ; değilse **false** .

#### <a name="remarks"></a>Açıklamalar

Tinyness tespit edebilir olan türler, ıEC 559 kayan nokta temsillerine sahip bir seçenek olarak eklenmiştir ve bunun uygulanması bazı sonuçları etkileyebilir.

#### <a name="example"></a>Örnek

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

### <a name="traps"></a>tuzak

Aritmetik özel durumlarla rapor veren yakalamaya bir tür için uygulanıp uygulanmadığını sınar.

```cpp
static constexpr bool traps = false;
```

#### <a name="return-value"></a>Dönüş Değeri

tür için yakalama uygulanmışsa **true** ; değilse **yanlış** .

#### <a name="example"></a>Örnek

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
