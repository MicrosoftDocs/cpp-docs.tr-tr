---
title: '&lt;ios&gt; fonksiyonları'
ms.date: 11/04/2016
f1_keywords:
- xiosbase/std::defaultfloat
- xiosbase/std::boolalpha
- xiosbase/std::dec
- ios/std::fixed
- ios/std::hex
- ios/std::internal
- ios/std::left
- ios/std::noboolalpha
- ios/std::noshowbase
- ios/std::noshowpoint
- ios/std::noshowpos
- ios/std::noskipws
- ios/std::nounitbuf
- ios/std::nouppercase
- ios/std::oct
- ios/std::right
- ios/std::scientific
- ios/std::showbase
- ios/std::showpoint
- ios/std::showpos
- ios/std::skipws
- ios/std::unitbuf
- ios/std::uppercase
ms.assetid: 1382d53f-e531-4b41-adf6-6a1543512e51
helpviewer_keywords:
- std::defaultfloat [C++]
- std::boolalpha [C++]
- std::dec [C++]
- std::fixed [C++]
- std::hex [C++]
- std::hexfloat [C++]
- std::io_errc [C++]
- std::internal [C++]
- std::iostream_category [C++]
- std::is_error_code_enum [C++]
- std::left [C++]
- std::make_error_code [C++]
- std::make_error_condition [C++]
- std::noboolalpha [C++]
- std::noshowbase [C++]
- std::noshowpoint [C++]
- std::noshowpos [C++]
- std::noskipws [C++]
- std::nounitbuf [C++]
- std::nouppercase [C++]
- std::oct [C++]
- std::right [C++]
- std::scientific [C++]
- std::showbase [C++]
- std::showpoint [C++]
- std::showpos [C++]
- std::skipws [C++]
- std::unitbuf [C++]
- std::uppercase [C++]
ms.openlocfilehash: 67ac9259110abbd03fc054ea4e60ed1715030dcc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375409"
---
# <a name="ltiosgt-functions"></a>&lt;ios&gt; fonksiyonları

## <a name="boolalpha"></a><a name="boolalpha"></a>boolalpha

Tür [bool](../cpp/bool-cpp.md) değişkenlerinin akışta **doğru** veya **yanlış** olarak göründüğünü belirtir.

```cpp
ios_base& boolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tip **bool** değişkenleri 1 veya 0 olarak görüntülenir.

`boolalpha`etkin bir `str.`şekilde `ios_base::boolalpha` [setf](../standard-library/ios-base-class.md#setf)çağırır ( ), ve sonra str *döndürür*.

[noboolalpha](../standard-library/ios-functions.md#noboolalpha) etkisini tersine `boolalpha`çevirir.

### <a name="example"></a>Örnek

```cpp
// ios_boolalpha.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   bool b = true;
   cout << b << endl;
   boolalpha( cout );
   cout << b << endl;
   noboolalpha( cout );
   cout << b << endl;
   cout << boolalpha << b << endl;
}
```

```Output
1
true
1
true
```

## <a name="dec"></a><a name="dec"></a>Aralık

Temel 10 gösteriminde görünen bir üstsayı değişkeni belirtir.

```cpp
ios_base& dec(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, varsayılan olarak, sayılama değişkenleri temel 10'da görüntülenir.

`dec`etkin bir `str.`şekilde `ios_base::dec` [setf](../standard-library/ios-base-class.md#setf)çağırır ( , `ios_base::basefield`), ve sonra str *döndürür*.

### <a name="example"></a>Örnek

```cpp
// ios_dec.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 100;

   cout << i << endl;   // Default is base 10
   cout << hex << i << endl;
   dec( cout );
   cout << i << endl;
   oct( cout );
   cout << i << endl;
   cout << dec << i << endl;
}
```

```Output
100
64
100
144
100
```

## <a name="ltiosgt-defaultfloat"></a><a name="ios_defaultfloat"></a>&lt;ios&gt; varsayılan float

Float değerleri için `ios_base` varsayılan görüntü biçimini kullanacak bir nesnenin bayraklarını yapılandırır.

```cpp
ios_base& defaultfloat(ios_base& iosbase);
```

### <a name="parameters"></a>Parametreler

*_Iosbase*\
Bir `ios_base` nesnesi.

### <a name="remarks"></a>Açıklamalar

Manipülatör etkili `iosbase.` [ios_base çağırır::unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::floatfield)`, sonra *iosbase*döndürür .

## <a name="fixed"></a><a name="fixed"></a>Sabit

Kayan nokta sayısının sabit ondalık gösterimde görüntüleneceğini belirtir.

```cpp
ios_base& fixed(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`fixed`kayan nokta numaraları için varsayılan ekran gösterimidir. [bilimsel](../standard-library/ios-functions.md#scientific) gösterim kullanılarak görüntülenecek kayan nokta numaralarının bilimsel nedenleri.

Manipülatör etkili *str*çağırır. [setf](../standard-library/ios-base-class.md#setf) `ios_base::fixed`( `ios_base::floatfield` , ), ve sonra *str döndürür*.

### <a name="example"></a>Örnek

```cpp
// ios_fixed.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 1.1F;

   cout << i << endl;   // fixed is the default
   cout << scientific << i << endl;
   cout.precision( 1 );
   cout << fixed << i << endl;
}
```

```Output
1.1
1.100000e+000
1.1
```

## <a name="hex"></a><a name="hex"></a>Hex

İnsteger değişkenlerinin baz 16 gösteriminde görünmeyeceğini belirtir.

```cpp
ios_base& hex(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, varsayılan olarak, sayılama değişkenleri temel 10 gösteriminde görüntülenir. [dec](../standard-library/ios-functions.md#dec) ve [oct](../standard-library/ios-functions.md#oct) da sonlu değişkenlerin görünme şeklini değiştirir.

Manipülatör etkin bir `str`şekilde **çağırır.** [setf](../standard-library/ios-base-class.md#setf) `ios_base::hex`( `ios_base::basefield`, ), ve sonra *str döndürür*.

### <a name="example"></a>Örnek

Nasıl [dec](../standard-library/ios-functions.md#dec) kullanılacağına `hex`bir örnek için dec bakın.

## <a name="hexfloat"></a><a name="hexfloat"></a>hexfloat

```cpp
ios_base& hexfloat (ios_base& str);
```

## <a name="io_errc"></a><a name="io_errc"></a>io_errc

```cpp
enum class io_errc {
    stream = 1
};
```

## <a name="internal"></a><a name="internal"></a>Iç

Bir sayının işaretinin haklı bırakılmasına ve sayının doğru olmasının doğru yasılmasına neden olur.

```cpp
ios_base& internal(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[showpos](../standard-library/ios-functions.md#showpos) pozitif sayılar için göstermek için işareti neden olur.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(`çağırır[ios_base::iç](../standard-library/ios-base-class.md#fmtflags) `,` [ios_base::adjustfield](../standard-library/ios-base-class.md#fmtflags)`)`, ve sonra *str*döndürür .

### <a name="example"></a>Örnek

```cpp
// ios_internal.cpp
// compile with: /EHsc
#include <iostream>
#include <iomanip>

int main( void )
{
   using namespace std;
   float i = -123.456F;
   cout.fill( '.' );
   cout << setw( 10 ) << i << endl;
   cout << setw( 10 ) << internal << i << endl;
}
```

```Output
..-123.456
-..123.456
```

## <a name="is_error_code_enum"></a><a name="is_error_code_enum"></a>is_error_code_enum

```cpp
template <> struct is_error_code_enum<io_errc> : public true_type { };
```

## <a name="iostream_category"></a><a name="iostream_category"></a>iostream_category

```cpp
const error_category& iostream_category() noexcept;
```

## <a name="left"></a><a name="left"></a>Sol

Çıkış genişliği kadar geniş olmayan metnin sol kenar boşluğuyla birlikte akış floşta görünmesine neden olur.

```cpp
ios_base& left(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::left, ios_base::adjustfield)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

```cpp
// ios_left.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout.width( 20 );
   cout << f1 << endl;
   cout << left << f1 << endl;
}
```

```Output
5
        5
```

## <a name="make_error_code"></a><a name="make_error_code"></a>make_error_code

```cpp
error_code make_error_code(io_errc e) noexcept;
```

## <a name="make_error_condition"></a><a name="make_error_condition"></a>make_error_condition

```cpp
error_condition make_error_condition(io_errc e) noexcept;
```

## <a name="noboolalpha"></a><a name="noboolalpha"></a>noboolalpha

Tür [bool](../cpp/bool-cpp.md) değişkenlerinin akışta 1 veya 0 olarak göründüğünü belirtir.

```cpp
ios_base& noboolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `noboolalpha` yürürlüktedir.

`noboolalpha`etkin bir `str.`şekilde [unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::boolalpha)`çağırır ve sonra *str döndürür.*

[boolalpha](../standard-library/ios-functions.md#boolalpha) etkisini tersine `noboolalpha`çevirir.

### <a name="example"></a>Örnek

Kullanma `noboolalpha`örneği için [boolalpha'ya](../standard-library/ios-functions.md#boolalpha) bakın.

## <a name="noshowbase"></a><a name="noshowbase"></a>noshowbase

Bir sayının görüntülendiği notasyon tabanını gösteren kapatır.

```cpp
ios_base& noshowbase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`noshowbase`varsayılan olarak açıktır. Sayıların gösterim altonmasını belirtmek için [showbase'i](../standard-library/ios-functions.md#showbase) kullanın.

Manipülatör etkin `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::showbase)`çağırır , ve sonra *str*döndürür .

### <a name="example"></a>Örnek

Nasıl kullanılacağına `noshowbase`bir örnek için [showbase'e](../standard-library/ios-functions.md#showbase) bakın.

## <a name="noshowpoint"></a><a name="noshowpoint"></a>noshowpoint

Kesirli kısmı sıfır olan kayan nokta numaralarının yalnızca tam sayı kısmını görüntüler.

```cpp
ios_base& noshowpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`noshowpoint`varsayılan olarak açıktır; ondalık noktadan sonra sıfırları görüntülemek için [showpoint](../standard-library/ios-functions.md#showpoint) ve [kesinlik](../standard-library/ios-base-class.md#precision) kullanın.

Manipülatör etkin `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::showpoint)`çağırır , ve sonra *str*döndürür .

### <a name="example"></a>Örnek

```cpp
// ios_noshowpoint.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.000;
   cout << f1 << endl;   // noshowpoint is default
   cout.precision( 4 );
   cout << showpoint << f1 << endl;
   cout << noshowpoint << f1 << endl;
}
```

```Output
5
5.000
5
```

## <a name="noshowpos"></a><a name="noshowpos"></a>noshowpos

Pozitif sayıların açıkça imzalanmamasını neden olur.

```cpp
ios_base& noshowpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`noshowpos`varsayılan olarak açıktır.

Manipülatör etkin `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::showps)`çağırır , sonra *str*döndürür.

### <a name="example"></a>Örnek

Kullanma örneği için [showpos'a](../standard-library/ios-functions.md#showpos) `noshowpos`bakın.

## <a name="noskipws"></a><a name="noskipws"></a>noskipws

Giriş akışı tarafından okunacak boşluklara neden olur.

```cpp
ios_base& noskipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [skipws](../standard-library/ios-functions.md#skipws) etkindir. Giriş akışında bir boşluk okunduğunda, arabelleğe son sinyali verirken.

Manipülatör etkin `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::skipws)`çağırır , ve sonra *str*döndürür .

### <a name="example"></a>Örnek

```cpp
// ios_noskipws.cpp
// compile with: /EHsc
#include <iostream>
#include <string>

int main() {
   using namespace std;
   string s1, s2, s3;
   cout << "Enter three strings: ";
   cin >> noskipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

## <a name="nounitbuf"></a><a name="nounitbuf"></a>nounitbuf

Arabellek dolduğunda çıktının arabelleğe alınmasına ve işlenmesine neden olur.

```cpp
ios_base& nounitbuf(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[unitbuf](../standard-library/ios-functions.md#unitbuf) boş olmadığında arabellek işlenmesine neden olur.

Manipülatör etkin `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::unitbuf)`çağırır , ve sonra *str*döndürür .

## <a name="nouppercase"></a><a name="nouppercase"></a>nouppercase

Hexadecimal basamakların ve bilimsel gösterimdeki üs küçük harfte göründüğünü belirtir.

```cpp
ios_base& nouppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Manipülatör etkin `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)`(ios_base::uppercase)`çağırır , ve sonra *str*döndürür .

### <a name="example"></a>Örnek

Kullanma `nouppercase`örneği için [büyük harfe](../standard-library/ios-functions.md#uppercase) bakın.

## <a name="oct"></a><a name="oct"></a>Ekim

Temel 8 gösteriminde görünen bir sayı yayla değişkeni belirtir.

```cpp
ios_base& oct(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, varsayılan olarak, sayılama değişkenleri temel 10 gösteriminde görüntülenir. [dec](../standard-library/ios-functions.md#dec) ve [hex](../standard-library/ios-functions.md#hex) de tamsayı değişkenlerinin görünme şeklini değiştirir.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::oct, ios_base::basefield)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

Nasıl [dec](../standard-library/ios-functions.md#dec) kullanılacağına `oct`bir örnek için dec bakın.

## <a name="right"></a><a name="right"></a>Doğru

Çıkış genişliği kadar geniş olmayan metnin doğru kenar boşluğuyla akış floşta görünmesine neden olur.

```cpp
ios_base& right(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[sol](../standard-library/ios-functions.md#left) da metnin gerekçesini değiştirir.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::right, ios_base::adjustfield)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

```cpp
// ios_right.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   double f1= 5.00;
   cout << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << left << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
   cout.width( 20 );
   cout << right << f1 << endl;
   cout.width( 20 );
   cout << f1 << endl;
}
```

```Output
5
                   5
5
5
                   5
                   5
```

## <a name="scientific"></a><a name="scientific"></a>Bilimsel

Kayan nokta numaralarının bilimsel gösterim kullanılarak görüntülenmesine neden olur.

```cpp
ios_base& scientific(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, kayan nokta numaraları için [sabit](../standard-library/ios-functions.md#fixed) gösterim etkindir.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::scientific, ios_base::floatfield)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

```cpp
// ios_scientific.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   float i = 100.23F;

   cout << i << endl;
   cout << scientific << i << endl;
}
```

```Output
100.23
1.002300e+002
```

## <a name="showbase"></a><a name="showbase"></a>showbase

Bir sayının görüntülendiği gösterim tabanını gösterir.

```cpp
ios_base& showbase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bir sayının notasyonal tabanı [dec](../standard-library/ios-functions.md#dec), [ekim](../standard-library/ios-functions.md#oct), veya [hex](../standard-library/ios-functions.md#hex)ile değiştirilebilir.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::showbase)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

```cpp
// ios_showbase.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int j = 100;

   cout << showbase << j << endl;   // dec is default
   cout << hex << j << showbase << endl;
   cout << oct << j << showbase << endl;

   cout << dec << j << noshowbase << endl;
   cout << hex << j << noshowbase << endl;
   cout << oct << j << noshowbase << endl;
}
```

```Output
100
0x64
0144
100
64
144
```

## <a name="showpoint"></a><a name="showpoint"></a>showpoint

Kayan nokta sayısının tam sayı kısmını görüntüler ve kesirli parça sıfır olsa bile ondalık noktanın sağındaki basamakları görüntüler.

```cpp
ios_base& showpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [noshowpoint](../standard-library/ios-functions.md#noshowpoint) etkindir.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::showpoint)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

Kullanma `showpoint`örneği için [noshowpoint'e](../standard-library/ios-functions.md#noshowpoint) bakın.

## <a name="showpos"></a><a name="showpos"></a>showpos

Pozitif sayıların açıkça imzalanmasına neden olur.

```cpp
ios_base& showpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[noshowpos](../standard-library/ios-functions.md#noshowpos) varsayılandır.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::showpos)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

```cpp
// ios_showpos.cpp
// compile with: /EHsc
#include <iostream>

int main( )
{
   using namespace std;
   int i = 1;

   cout << noshowpos << i << endl;   // noshowpos is default
   cout << showpos << i << endl;
}
```

```Output
1
+1
```

## <a name="skipws"></a><a name="skipws"></a>skipws

Giriş akışı tarafından okunmaması için boşluklara neden olun.

```cpp
ios_base& skipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, `skipws` yürürlüktedir. [noskipws](../standard-library/ios-functions.md#noskipws) giriş akışından okunacak boşluklara neden olur.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::skipws)`çağırır ve sonra *str döndürür.*

### <a name="example"></a>Örnek

```cpp
#include <iostream>
#include <string>

int main( )
{
   using namespace std;
   char s1, s2, s3;
   cout << "Enter three characters: ";
   cin >> skipws >> s1 >> s2 >> s3;
   cout << "." << s1  << "." << endl;
   cout << "." << s2 << "." << endl;
   cout << "." << s3 << "." << endl;
}
```

```Input
1 2 3
```

```Output
Enter three characters: 1 2 3
.1.
.2.
.3.
```

## <a name="unitbuf"></a><a name="unitbuf"></a>unitbuf

Arabellek boş olmadığında çıktının işlenmesine neden olur.

```cpp
ios_base& unitbuf(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Arabelleği `endl` de temize çıkar.

[nounitbuf](../standard-library/ios-functions.md#nounitbuf) varsayılan olarak yürürlüktedir.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(`[ios_base çağırır::unitbuf](../standard-library/ios-base-class.md#fmtflags)`)`, ve sonra *str*döndürür .

## <a name="uppercase"></a><a name="uppercase"></a>Büyük

Heksadedemimal basamakların ve bilimsel gösterimdeki üs büyük harfle göründüğünü belirtir.

```cpp
ios_base& uppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*Str*\
[ios_base](../standard-library/ios-base-class.md)türünden bir nesneye veya 'den `ios_base`devralan bir türe başvuru

### <a name="return-value"></a>Dönüş Değeri

*Str* türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [nouppercase](../standard-library/ios-functions.md#nouppercase) etkindir.

Manipülatör etkili `str.` [setf](../standard-library/ios-base-class.md#setf)`(`[çağırır ios_base::büyük harf](../standard-library/ios-base-class.md#fmtflags)`)`, ve sonra *str*döndürür .

### <a name="example"></a>Örnek

```cpp
// ios_uppercase.cpp
// compile with: /EHsc
#include <iostream>

int main( void )
{
   using namespace std;

   double i = 1.23e100;
   cout << i << endl;
   cout << uppercase << i << endl;

   int j = 10;
   cout << hex << nouppercase << j << endl;
   cout << hex << uppercase << j << endl;
}
```

```Output
1.23e+100
1.23E+100
a
A
```
