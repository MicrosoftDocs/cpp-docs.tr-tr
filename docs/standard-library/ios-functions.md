---
description: 'Daha fazla bilgi edinin: &lt; iOS &gt; işlevleri'
title: '&lt;iOS &gt; işlevleri'
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
ms.openlocfilehash: 82353509be371f9292c05947dbc4221bb0e74b05
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231439"
---
# <a name="ltiosgt-functions"></a>&lt;iOS &gt; işlevleri

## <a name="boolalpha"></a><a name="boolalpha"></a> boolalpha

[Bool](../cpp/bool-cpp.md) türündeki değişkenlerin **`true`** akışta veya akışta göründüğünü belirtir **`false`** .

```cpp
ios_base& boolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, türündeki değişkenler **`bool`** 1 veya 0 olarak görüntülenir.

`boolalpha``str.` [setf](../standard-library/ios-base-class.md#setf)() etkin bir şekilde çağırır `ios_base::boolalpha` ve *Str* döndürür.

[noboolalpha](../standard-library/ios-functions.md#noboolalpha) , öğesinin etkisini tersine çevirir `boolalpha` .

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

## <a name="dec"></a><a name="dec"></a> Dec

Tamsayı değişkenlerinin taban 10 gösteriminde göründüğünü belirtir.

```cpp
ios_base& dec(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri temel 10 ' da görüntülenir.

`dec``str.` [setf](../standard-library/ios-base-class.md#setf)'yi (,) etkin bir şekilde çağırır `ios_base::dec` `ios_base::basefield` ve *Str* döndürür.

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

## <a name="ltiosgt-defaultfloat"></a><a name="ios_defaultfloat"></a>&lt;iOS &gt; defaultfloat

`ios_base`Kayan değerler için varsayılan görüntü biçimini kullanmak üzere bir nesnenin bayraklarını yapılandırır.

```cpp
ios_base& defaultfloat(ios_base& iosbase);
```

### <a name="parameters"></a>Parametreler

*_Iosbase*\
Bir `ios_base` nesnesi.

### <a name="remarks"></a>Açıklamalar

İşleici etkin bir şekilde `iosbase.` [ios_base:: unsetf](../standard-library/ios-base-class.md#unsetf)çağırır `(ios_base::floatfield)` ve sonra *ıosbase* döndürür.

## <a name="fixed"></a><a name="fixed"></a> Düzenle

Sabit ondalık gösterimde bir kayan noktalı sayının görüntülendiğini belirtir.

```cpp
ios_base& fixed(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`fixed` , kayan nokta numaraları için varsayılan görüntüleme gösterimidir. [bilimsel](../standard-library/ios-functions.md#scientific) , kayan nokta numaralarının bilimsel gösterim kullanılarak görüntülenmesine neden olur.

İşleici, *Str*'yi etkin bir şekilde çağırır. [setf](../standard-library/ios-base-class.md#setf)( `ios_base::fixed` , `ios_base::floatfield` ) ve ardından *Str* döndürür.

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

## <a name="hex"></a><a name="hex"></a> eşlenecek

Tamsayı değişkenlerinin temel 16 gösterimde görüneceğini belirtir.

```cpp
ios_base& hex(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri taban 10 gösteriminde görüntülenir. [Dec](../standard-library/ios-functions.md#dec) ve [Oct](../standard-library/ios-functions.md#oct) de tamsayı değişkenlerinin görünme şeklini değiştirir.

İşleici etkin bir şekilde çağırır `str` **.** [setf](../standard-library/ios-base-class.md#setf)( `ios_base::hex` , `ios_base::basefield` ) ve ardından *Str* döndürür.

### <a name="example"></a>Örnek

Öğesinin nasıl [kullanılacağına ilişkin bir örnek için bkz](../standard-library/ios-functions.md#dec) `hex` ..

## <a name="hexfloat"></a><a name="hexfloat"></a> onaltıdan kayan

```cpp
ios_base& hexfloat (ios_base& str);
```

## <a name="io_errc"></a><a name="io_errc"></a> io_errc

```cpp
enum class io_errc {
    stream = 1
};
```

## <a name="internal"></a><a name="internal"></a> iç

Bir sayının işaretinin hizalı olarak sola ve sağa yaslanmasına neden olur.

```cpp
ios_base& internal(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[showpos](../standard-library/ios-functions.md#showpos) , işaretin pozitif sayılar için görüntülenmesine neden olur.

İşleici, `str.` [setf](../standard-library/ios-base-class.md#setf) `(` [ios_base:: Internal](../standard-library/ios-base-class.md#fmtflags) `,` [ios_base:: adjustfield](../standard-library/ios-base-class.md#fmtflags)öğesini etkin bir şekilde çağırır `)` ve *Str* döndürür.

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

## <a name="is_error_code_enum"></a><a name="is_error_code_enum"></a> is_error_code_enum

```cpp
template <> struct is_error_code_enum<io_errc> : public true_type { };
```

## <a name="iostream_category"></a><a name="iostream_category"></a> iostream_category

```cpp
const error_category& iostream_category() noexcept;
```

## <a name="left"></a><a name="left"></a> tarafta

Çıktı genişliği, sol kenar boşluğu ile boşaltımın üzerinde görünmesini sağlayan metnin geniş olmasına neden olur.

```cpp
ios_base& left(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::left, ios_base::adjustfield)` ve *Str* döndürür.

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

## <a name="make_error_code"></a><a name="make_error_code"></a> make_error_code

```cpp
error_code make_error_code(io_errc e) noexcept;
```

## <a name="make_error_condition"></a><a name="make_error_condition"></a> make_error_condition

```cpp
error_condition make_error_condition(io_errc e) noexcept;
```

## <a name="noboolalpha"></a><a name="noboolalpha"></a> noboolalpha

[Bool](../cpp/bool-cpp.md) türündeki değişkenlerin akışta 1 veya 0 olarak göründüğünü belirtir.

```cpp
ios_base& noboolalpha(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak etkindir `noboolalpha` .

`noboolalpha``str.`, [unsetf](../standard-library/ios-base-class.md#unsetf)'yi etkin bir şekilde çağırır `(ios_base::boolalpha)` ve *Str* döndürür.

[boolalpha](../standard-library/ios-functions.md#boolalpha) , öğesinin etkisini tersine çevirir `noboolalpha` .

### <a name="example"></a>Örnek

Kullanım örneği için bkz. [boolalpha](../standard-library/ios-functions.md#boolalpha) `noboolalpha` .

## <a name="noshowbase"></a><a name="noshowbase"></a> noshowbase

Bir sayının gösterildiği notational temelini belirtir.

```cpp
ios_base& noshowbase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`noshowbase` Varsayılan olarak açık olur. Sayıların notational temelini göstermek için [showbase](../standard-library/ios-functions.md#showbase) kullanın.

İşleici etkin bir şekilde `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)çağırır `(ios_base::showbase)` ve *Str* döndürür.

### <a name="example"></a>Örnek

Öğesinin nasıl kullanılacağına ilişkin bir örnek için bkz. [showbase](../standard-library/ios-functions.md#showbase) `noshowbase` .

## <a name="noshowpoint"></a><a name="noshowpoint"></a> noshowpoint

Kısmi bölümü sıfır olan kayan noktalı sayıların yalnızca tam sayı kısmını görüntüler.

```cpp
ios_base& noshowpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`noshowpoint` Varsayılan olarak açık; ondalık ayırıcıdan sonra sıfırları göstermek için [showpoint](../standard-library/ios-functions.md#showpoint) ve [Precision](../standard-library/ios-base-class.md#precision) kullanın.

İşleici etkin bir şekilde `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)çağırır `(ios_base::showpoint)` ve *Str* döndürür.

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

## <a name="noshowpos"></a><a name="noshowpos"></a> noshowpos

Pozitif sayıların açıkça imzalanmamasını sağlar.

```cpp
ios_base& noshowpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`noshowpos` Varsayılan olarak açık olur.

İşleici, `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)'yi etkin bir şekilde çağırır `(ios_base::showps)` , ardından *Str* döndürür.

### <a name="example"></a>Örnek

Bir örneği için bkz. [showpos](../standard-library/ios-functions.md#showpos) `noshowpos` .

## <a name="noskipws"></a><a name="noskipws"></a> noskipws

Giriş akışı tarafından boşlukların okunmasına neden olur.

```cpp
ios_base& noskipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [skipw](../standard-library/ios-functions.md#skipws) etkin olur. Giriş akışında bir boşluk okunıyorsa, arabelleğin sonuna işaret eder.

İşleici etkin bir şekilde `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)çağırır `(ios_base::skipws)` ve *Str* döndürür.

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

## <a name="nounitbuf"></a><a name="nounitbuf"></a> nounitbuf

Arabellek dolduğunda çıktının arabelleğe alınıp işlenmesine neden olur.

```cpp
ios_base& nounitbuf(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[unitarabelleğe](../standard-library/ios-functions.md#unitbuf) , boş olmadığında arabelleğin işlenmesine neden olur.

İşleici etkin bir şekilde `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)çağırır `(ios_base::unitbuf)` ve *Str* döndürür.

## <a name="nouppercase"></a><a name="nouppercase"></a> nouppercase

Bilimsel gösterimdeki onaltılık basamakların ve üs harflerin küçük harf olarak göründüğünü belirtir.

```cpp
ios_base& nouppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

İşleici etkin bir şekilde `str.` [unsetf](../standard-library/ios-base-class.md#unsetf)çağırır `(ios_base::uppercase)` ve *Str* döndürür.

### <a name="example"></a>Örnek

Kullanım örneği için [büyük harfe](../standard-library/ios-functions.md#uppercase) bakın `nouppercase` .

## <a name="oct"></a><a name="oct"></a> Oct

Tamsayı değişkenlerinin taban 8 gösteriminde göründüğünü belirtir.

```cpp
ios_base& oct(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, tamsayı değişkenleri taban 10 gösteriminde görüntülenir. [Dec](../standard-library/ios-functions.md#dec) ve [HEX](../standard-library/ios-functions.md#hex) de tamsayı değişkenlerinin görünme şeklini değiştirir.

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::oct, ios_base::basefield)` ve *Str* döndürür.

### <a name="example"></a>Örnek

Öğesinin nasıl [kullanılacağına ilişkin bir örnek için bkz](../standard-library/ios-functions.md#dec) `oct` ..

## <a name="right"></a><a name="right"></a> Right

Çıktı genişliği doğru olmayan metnin akış temizlemesi durumunda sağ kenar boşluğu ile görünmesini sağlar.

```cpp
ios_base& right(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[sol](../standard-library/ios-functions.md#left) Ayrıca metnin gerekçe üzerinde değişiklik yapar.

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::right, ios_base::adjustfield)` ve *Str* döndürür.

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

## <a name="scientific"></a><a name="scientific"></a> bilimsel

, Kayan nokta numaralarının bilimsel gösterim kullanılarak görüntülenmesine neden olur.

```cpp
ios_base& scientific(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [sabit](../standard-library/ios-functions.md#fixed) Gösterim kayan noktalı sayılar için etkindir.

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::scientific, ios_base::floatfield)` ve *Str* döndürür.

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

## <a name="showbase"></a><a name="showbase"></a> showbase

Bir sayının gösterileceği notational tabanını gösterir.

```cpp
ios_base& showbase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Bir sayının notational temeli [Ara](../standard-library/ios-functions.md#dec), [Oct](../standard-library/ios-functions.md#oct)veya [onaltılık](../standard-library/ios-functions.md#hex)ile değiştirilebilir.

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::showbase)` ve *Str* döndürür.

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

## <a name="showpoint"></a><a name="showpoint"></a> showpoint

Kesirli bölüm sıfır olduğunda bile ondalık noktanın sağ tarafındaki bir kayan nokta sayısı ve rakamların tam sayı kısmını görüntüler.

```cpp
ios_base& showpoint(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [noshowpoint](../standard-library/ios-functions.md#noshowpoint) etkin olur.

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::showpoint)` ve *Str* döndürür.

### <a name="example"></a>Örnek

Kullanım örneği için bkz. [noshowpoint](../standard-library/ios-functions.md#noshowpoint) `showpoint` .

## <a name="showpos"></a><a name="showpos"></a> showpos

Pozitif sayıların açıkça imzalanmasına neden olur.

```cpp
ios_base& showpos(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

[noshowpos](../standard-library/ios-functions.md#noshowpos) varsayılandır.

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::showpos)` ve *Str* döndürür.

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

## <a name="skipws"></a><a name="skipws"></a> skipws

Giriş akışı tarafından okunmamasına neden olan boşluk.

```cpp
ios_base& skipws(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak etkindir `skipws` . [noskipws](../standard-library/ios-functions.md#noskipws) , giriş akışından boşlukların okunmasına neden olur.

İşleici `str.` [setf](../standard-library/ios-base-class.md#setf)'yi etkin bir şekilde çağırır `(ios_base::skipws)` ve *Str* döndürür.

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

## <a name="unitbuf"></a><a name="unitbuf"></a> unitbuf

Arabellek boş olmadığında çıktının işlenmesine neden olur.

```cpp
ios_base& unitbuf(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

`endl`Ayrıca arabelleği de temizler.

[nounitarabelleğe](../standard-library/ios-functions.md#nounitbuf) varsayılan olarak etkindir.

İşleici, `str.` [setf](../standard-library/ios-base-class.md#setf) `(` [ios_base:: unitarabelleğe](../standard-library/ios-base-class.md#fmtflags)etkin bir şekilde çağırır `)` ve *Str* döndürür.

## <a name="uppercase"></a><a name="uppercase"></a> İngiliz

Bilimsel gösterimdeki onaltılık basamakların ve üs 'ın büyük harfle göründüğünü belirtir.

```cpp
ios_base& uppercase(ios_base& str);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*\
[İos_base](../standard-library/ios-base-class.md)türünde bir nesneye veya öğesinden devralan bir türe başvuru `ios_base` .

### <a name="return-value"></a>Dönüş Değeri

*Str* 'nin türetildiği nesneye bir başvuru.

### <a name="remarks"></a>Açıklamalar

Varsayılan olarak, [nobüyük](../standard-library/ios-functions.md#nouppercase) değer etkindir.

İşleici, `str.` [setf](../standard-library/ios-base-class.md#setf) `(` [ios_base:: büyük harfe](../standard-library/ios-base-class.md#fmtflags)etkin bir şekilde çağrı yapar `)` ve ardından *Str* döndürür.

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
