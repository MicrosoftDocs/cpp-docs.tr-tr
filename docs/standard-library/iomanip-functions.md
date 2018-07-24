---
title: '&lt;iomanip&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- iomanip/std::get_money
- iomanip/std::get_time
- iomanip/std::put_money
- iomanip/std::put_time
- iomanip/std::quoted
- iomanip/std::resetiosflags
- iomanip/std::setbase
- iomanip/std::setfill
- iomanip/std::setiosflags
- iomanip/std::setprecision
- iomanip/std::setw
ms.assetid: 3ddde610-70cc-4cfa-8a89-3e83d1d356a8
helpviewer_keywords:
- std::get_money [C++]
- std::get_time [C++]
- std::put_money [C++]
- std::put_time [C++]
- std::quoted [C++]
- std::resetiosflags [C++]
- std::setbase [C++]
- std::setfill [C++]
- std::setiosflags [C++]
- std::setprecision [C++]
- std::setw [C++]
ms.openlocfilehash: 5882a2fc31d5c9369429cdc39fb86a1c08e0c828
ms.sourcegitcommit: 7eadb968405bcb92ffa505e3ad8ac73483e59685
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/23/2018
ms.locfileid: "39208838"
---
# <a name="ltiomanipgt-functions"></a>&lt;iomanip&gt; işlevleri

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[Teklif](#quoted)|[resetiosflags](#resetiosflags)|
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="iomanip_get_money"></a>  get_money

Parasal bir değeri istediğiniz biçimi kullanarak bir akıştan ayıklar ve parametre değeri döndürür.

```cpp
template <class Money>
T7 get_money(Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>Parametreler

*_Amount* ayıklanan parasal değer.

*_Intl* varsa **true**, uluslararası biçimini kullanın. Varsayılan değer **false**.

### <a name="remarks"></a>Açıklamalar

İşleyici bir nesne, akıştan ayıklanan döndürür `str`, olarak davranan bir `formatted input function` üye işlevini çağırır `get` için yerel ayar modeli `money_get` ilişkili `str`kullanarak *_ Uluslararası* uluslararası biçimi belirtmek için. Başarılı çağrı depolar, *_Amount* ayıklanan parasal değer. Ardından işleyici döndürür `str`.

`Money` türünde olmalıdır `long double` veya örneklemesi `basic_string` aynı öğe ve nitelikler parametreleri ile `str`.

## <a name="iomanip_get_time"></a>  get_time

Bir zaman değeri istediğiniz biçimi kullanarak bir akıştan ayıklar. Değer bir parametre bir zaman yapısı döndürür.

```cpp
template <class Elem>
T10 put_time(struct tm *_Tptr, const Elem *_Fmt);
```

### <a name="parameters"></a>Parametreler

*_Tptr* zaman yapısı biçiminde saat.

*_Fmt* saat değeri elde etmek için kullanmak istediğiniz biçimi.

### <a name="remarks"></a>Açıklamalar

İşleyici bir nesne, akıştan ayıklanan döndürür `str`, olarak davranan bir `formatted input function` üye işlevini çağırır `get` için yerel ayar modeli `time_get` ilişkili `str`kullanarak `tptr` için zaman yapısı belirtmek ve `fmt` null ile sonlandırılmış bir biçim dizesi belirtmek için. Başarılı olursa çağrı herhangi ayıklanan saat alanları ile ilişkili değerler zaman yapıda depolar. Ardından işleyici döndürür `str`.

## <a name="iomanip_put_money"></a>  put_money

Bir akışa istediğiniz biçimi kullanarak bir para miktarına ekler.

```cpp
template <class Money>
T8 put_money(const Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>Parametreler

*_Amount* akımına eklenecek parasal tutar.

*_Intl* kümesine **true** işleyici Uluslararası biçim kullanması gerekiyorsa **false** gerektiğini değil ise.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `str`.

### <a name="remarks"></a>Açıklamalar

İşleyici nesneyi akışa eklendiğinde döner `str`, üye işlevi çağıran bir biçimlendirilmiş çıktı işlevi davranır `put` için yerel ayar modeli `money_put` ilişkili `str`. Başarılı çağrı ekler, `amount` uygun şekilde biçimlendirilmiş, kullanarak * _Intl` to indicate international format and `str.fill()`, as the fill element. The manipulator then returns `str'.

`Money` türünde olmalıdır `long double` veya örneklemesi `basic_string` aynı öğe ve nitelikler parametreleri ile `str`.

## <a name="iomanip_put_time"></a>  put_time

Bir zaman değeri zaman yapısından, belirtilen biçimi kullanarak bir akışa yazar.

```cpp
template <class Elem>
T10 put_time(struct tm* _Tptr, const Elem* _Fmt);
```

### <a name="parameters"></a>Parametreler

*_Tptr* zaman yapısı içinde sağlanan akış yazmak için zaman değeri.

*_Fmt* zaman değeri yazmak için istediğiniz biçimi.

### <a name="remarks"></a>Açıklamalar

İşleyici nesneyi akışa eklendiğinde döner `str`, olarak davranan bir `formatted output function`. Çıkış işlevi üye işlevini çağırır `put` için yerel ayar modeli `time_put` ilişkili `str`. Çıkış işlevi kullanır *_Tptr* zaman yapısını belirtmek için ve *_Fmt* null ile sonlandırılmış bir biçim dizesi belirtmek için. Başarılı olursa, arama metin zaman yapısından dönüştürülen değerler ve biçim dizesi ekler. Ardından işleyici döndürür `str`.

## <a name="quoted"></a>  Teklif

**(Yeni C ++ 14)**  Kullanışlı gidiş dönüşü engelleyebilecek dizeleri küme içi ve dışı sağlayan bir iostream işleyici akışları kullanarak >> ve << işleçleri.

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>Parametreler

*str* std::string, char\*, dize sabit değeri veya ham dize sabit değeri veya bunlardan birine geniş bir sürümünü (örneğin, std::wstring, wchar_t\*).

*sınırlayıcı* bir kullanıcı tarafından belirtilen karakter veya geniş karakter başlangıç ve bitiş dizesi için ayırıcı olarak kullanılacak.

*kaçış* bir kullanıcı tarafından belirtilen karakter veya kaçış dizileri dizenin içinde kaçış karakteri olarak kullanılmak üzere, geniş karakter.

### <a name="remarks"></a>Açıklamalar

Bkz: [ekleme işleçlerini kullanma ve biçimi denetleme](../standard-library/using-insertion-operators-and-controlling-format.md).

### <a name="example"></a>Örnek

Bu örnek nasıl kullanılacağını gösterir `quoted` varsayılan ayırıcı ve çıkış karakterini kullanma dizeleri daraltın. Çok geniş dizelerdir eşit olarak desteklenir.

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_quoted_v_nonquoted()
{
    // Results are identical regardless of input string type:
    // string inserted { R"(This is a "sentence".)" }; // raw string literal
    // string inserted { "This is a \"sentence\"." };  // regular string literal
    const char* inserted = "This is a \"sentence\".";  // const char*
    stringstream ss, ss_quoted;
    string extracted, extracted_quoted;

    ss << inserted;
    ss_quoted << quoted(inserted);

    cout << "ss.str() is storing       : " << ss.str() << endl;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl << endl;

    // Round-trip the strings
    ss >> extracted;
    ss_quoted >> quoted(extracted_quoted);

    cout << "After round trip: " << endl;
    cout << "Non-quoted      : " << extracted << endl;
    cout << "Quoted          : " << extracted_quoted << endl;
}

void main(int argc, char* argv[])
{
    show_quoted_v_nonquoted();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}

/* Output:
ss.str() is storing       : This is a "sentence".
ss_quoted.str() is storing: "This is a \"sentence\"."

After round trip:
Non-quoted      : This
Quoted          : This is a "sentence".

Press Enter to exit
*/
```

### <a name="example"></a>Örnek

Aşağıdaki örnek, özel bir sınırlayıcı ve/veya kaçış karakteri sağlamak gösterilmektedir:

```cpp
#include <iostream>
#include <iomanip>
#include <sstream>

using namespace std;

void show_custom_delimiter()
{
    string inserted{ R"("This" "is" "a" "heavily-quoted" "sentence".)" };
    // string inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    // const char* inserted{ "\"This\" \"is\" \"a\" \"heavily-quoted\" \"sentence\"" };
    stringstream ss, ss_quoted;
    string extracted;

    ss_quoted << quoted(inserted, '*');
    ss << inserted;
    cout << "ss_quoted.str() is storing: " << ss_quoted.str() << endl;
    cout << "ss.str() is storing       : " << ss.str() << endl << endl;

    // Use the same quoted arguments as on insertion.
    ss_quoted >> quoted(extracted, '*');

    cout << "After round trip: " << endl;
    cout << "Quoted          : " << extracted << endl;

    extracted = {};
    ss >> extracted;
    cout << "Non-quoted      : " << extracted << endl << endl;
}

void show_custom_escape()
{
    string inserted{ R"(\\root\trunk\branch\nest\egg\yolk)" };
    // string inserted{ "\\\\root\\trunk\\branch\\nest\\egg\\yolk" };
    stringstream ss, ss_quoted, ss_quoted_custom;
    string extracted;

    // Use '"' as delimiter and '~' as escape character.
    ss_quoted_custom << quoted(inserted, '"', '~');
    ss_quoted << quoted(inserted);
    ss << inserted;
    cout << "ss_quoted_custom.str(): " << ss_quoted_custom.str() << endl;
    cout << "ss_quoted.str()       : " << ss_quoted.str() << endl;
    cout << "ss.str()              : " << ss.str() << endl << endl;

    // No spaces in this string, so non-quoted behaves same as quoted
    // after round-tripping.
}

void main(int argc, char* argv[])
{
    cout << "Custom delimiter:" << endl;
    show_custom_delimiter();
    cout << "Custom escape character:" << endl;
    show_custom_escape();

    // Keep console window open in debug mode.
    cout << endl << "Press Enter to exit" << endl;
    string input{};
    getline(cin, input);
}
/* Output:
Custom delimiter:
ss_quoted.str() is storing: *"This" "is" "a" "heavily-quoted" "sentence".*
ss.str() is storing       : "This" "is" "a" "heavily-quoted" "sentence".

After round trip:
Quoted          : "This" "is" "a" "heavily-quoted" "sentence".
Non-quoted      : "This"

Custom escape character:
ss_quoted_custom.str(): "\\root\trunk\branch\nest\egg\yolk"
ss_quoted.str()       : "\\\\root\\trunk\\branch\\nest\\egg\\yolk"
ss.str()              : \\root\trunk\branch\nest\egg\yolk

Press Enter to exit
*/

```

## <a name="resetiosflags"></a>  resetiosflags

Belirtilen bayraklar temizler.

```cpp
T1 resetiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>Parametreler

*Maske* temizlemek için bayrakları.

### <a name="return-value"></a>Dönüş Değeri

İşleyici bir nesne, ayıklanan veya akışa eklenen döner `str`, çağrıları **str**. [setf](../standard-library/ios-base-class.md#setf)( `ios_base::` [fmtflags](../standard-library/ios-base-class.md#fmtflags), _ *maskesi*) ve sonra `str`.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `resetiosflags`.

## <a name="setbase"></a>  setbase

Tamsayılar için temel olarak ayarlayın.

```cpp
T3 setbase(int _Base);
```

### <a name="parameters"></a>Parametreler

*_Temel* sayı tabanı.

### <a name="return-value"></a>Dönüş Değeri

İşleyici bir nesne, ayıklanan veya akışa eklenen döner `str`, çağrıları **str**. `setf`( **maskesi**, [ios_base::basefield](../standard-library/ios-base-class.md#fmtflags)) ve sonra `str`. Burada, `mask` şu şekilde belirlenir:

- _ *Temel* 8 ise `mask` olduğu `ios_base::` [Eki](../standard-library/ios-functions.md#oct).

- _ *Temel* 10'dur ve maskesi `ios_base::` [Ara](../standard-library/ios-functions.md#dec).

- _ *Temel* 16 ise `mask` olduğu `ios_base::` [onaltılık](../standard-library/ios-functions.md#hex).

- _ *Temel* maskesi sonra başka bir değer olan `ios_base::` [fmtflags](../standard-library/ios-base-class.md#fmtflags)(0).

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setbase`.

## <a name="setfill"></a>  setfill

Sağa yaslanmış görüntüsündeki alanları doldurmak için kullanılan karakter ayarlar.

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>Parametreler

*CH* sağa yaslanmış görüntüsündeki alanları doldurmak için kullanılan karakter.

### <a name="return-value"></a>Dönüş Değeri

Şablonu işleyici bir nesne, ayıklanan veya akışa eklenen döner `str`, çağrıları **str**. [Dolgu](../standard-library/basic-ios-class.md#fill)(`Ch`) ve sonra `str`. Türü `Elem` akış için öğe türü ile aynı olmalıdır `str`.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setfill`.

## <a name="setiosflags"></a>  setiosflags

Belirtilen bayraklar ayarlar.

```cpp
T2 setiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>Parametreler

*Maske* ayarlamak için bayrakları.

### <a name="return-value"></a>Dönüş Değeri

İşleyici bir nesne, ayıklanan veya akışa eklenen döner `str`, çağrıları **str**. [setf](../standard-library/ios-base-class.md#setf)(_ *maskesi*) ve sonra `str`.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setiosflags`.

## <a name="setprecision"></a>  setprecision

Duyarlık kayan nokta değerleri için ayarlar.

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>Parametreler

*Prec* duyarlık kayan nokta değerleri.

### <a name="return-value"></a>Dönüş Değeri

İşleyici bir nesne, ayıklanan veya akışa eklenen döner `str`, çağrıları **str**. [Duyarlık](../standard-library/ios-base-class.md#precision)(`Prec`) ve sonra `str`.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setprecision`.

## <a name="setw"></a>  setw

Akıştaki sonraki öğe için görüntüleme alanının genişliğini belirtir.

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>Parametreler

*Geniş* görüntü alanının genişliği.

### <a name="return-value"></a>Dönüş Değeri

İşleyici bir nesne, ayıklanan veya akışa eklenen döner `str`, çağrıları **str**. [Genişlik](../standard-library/ios-base-class.md#width)(_ *geniş*), ardından döndürür `str`.

### <a name="remarks"></a>Açıklamalar

setw, genişliği yalnızca sonraki öğe için stream'de ayarlar ve genişliğini belirtmek istediğiniz her öğeden önce eklenmesi gerekir.

### <a name="example"></a>Örnek

```cpp
// iomanip_setw.cpp
// compile with: /EHsc
// Defines the entry point for the console application.
//
// Sample use of the following manipulators:
//   resetiosflags
//   setiosflags
//   setbase
//   setfill
//   setprecision
//   setw

#include <iostream>
#include <iomanip>

using namespace std;

const double   d1 = 1.23456789;
const double   d2 = 12.3456789;
const double   d3 = 123.456789;
const double   d4 = 1234.56789;
const double   d5 = 12345.6789;
const long      l1 = 16;
const long      l2 = 256;
const long      l3 = 1024;
const long      l4 = 4096;
const long      l5 = 65536;
int         base = 10;

void DisplayDefault( )
{
   cout << endl << "default display" << endl;
   cout << "d1 = " << d1 << endl;
   cout << "d2 = " << d2 << endl;
   cout << "d3 = " << d3 << endl;
   cout << "d4 = " << d4 << endl;
   cout << "d5 = " << d5 << endl;
}

void DisplayWidth( int n )
{
   cout << endl << "fixed width display set to " << n << ".\n";
   cout << "d1 = " << setw(n) << d1 << endl;
   cout << "d2 = " << setw(n) << d2 << endl;
   cout << "d3 = " << setw(n) << d3 << endl;
   cout << "d4 = " << setw(n) << d4 << endl;
   cout << "d5 = " << setw(n) << d5 << endl;
}

void DisplayLongs( )
{
   cout << setbase(10);
   cout << endl << "setbase(" << base << ")" << endl;
   cout << setbase(base);
   cout << "l1 = " << l1 << endl;
   cout << "l2 = " << l2 << endl;
   cout << "l3 = " << l3 << endl;
   cout << "l4 = " << l4 << endl;
   cout << "l5 = " << l5 << endl;
}

int main( int argc, char* argv[] )
{
   DisplayDefault( );

   cout << endl << "setprecision(" << 3 << ")" << setprecision(3);
   DisplayDefault( );

   cout << endl << "setprecision(" << 12 << ")" << setprecision(12);
   DisplayDefault( );

   cout << setiosflags(ios_base::scientific);
   cout << endl << "setiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << resetiosflags(ios_base::scientific);
   cout << endl << "resetiosflags(" << ios_base::scientific << ")";
   DisplayDefault( );

   cout << endl << "setfill('" << 'S' << "')" << setfill('S');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setfill('" << ' ' << "')" << setfill(' ');
   DisplayWidth(15);
   DisplayDefault( );

   cout << endl << "setprecision(" << 8 << ")" << setprecision(8);
   DisplayWidth(10);
   DisplayDefault( );

   base = 16;
   DisplayLongs( );

   base = 8;
   DisplayLongs( );

   base = 10;
   DisplayLongs( );

   return   0;
}
```

```Output

default display
d1 = 1.23457
d2 = 12.3457
d3 = 123.457
d4 = 1234.57
d5 = 12345.7

setprecision(3)
default display
d1 = 1.23
d2 = 12.3
d3 = 123
d4 = 1.23e+003
d5 = 1.23e+004

setprecision(12)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setiosflags(4096)
default display
d1 = 1.234567890000e+000
d2 = 1.234567890000e+001
d3 = 1.234567890000e+002
d4 = 1.234567890000e+003
d5 = 1.234567890000e+004

resetiosflags(4096)
default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill('S')
fixed width display set to 15.
d1 = SSSSS1.23456789
d2 = SSSSS12.3456789
d3 = SSSSS123.456789
d4 = SSSSS1234.56789
d5 = SSSSS12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setfill(' ')
fixed width display set to 15.
d1 =      1.23456789
d2 =      12.3456789
d3 =      123.456789
d4 =      1234.56789
d5 =      12345.6789

default display
d1 = 1.23456789
d2 = 12.3456789
d3 = 123.456789
d4 = 1234.56789
d5 = 12345.6789

setprecision(8)
fixed width display set to 10.
d1 =  1.2345679
d2 =  12.345679
d3 =  123.45679
d4 =  1234.5679
d5 =  12345.679

default display
d1 = 1.2345679
d2 = 12.345679
d3 = 123.45679
d4 = 1234.5679
d5 = 12345.679

setbase(16)
l1 = 10
l2 = 100
l3 = 400
l4 = 1000
l5 = 10000

setbase(8)
l1 = 20
l2 = 400
l3 = 2000
l4 = 10000
l5 = 200000

setbase(10)
l1 = 16
l2 = 256
l3 = 1024
l4 = 4096
l5 = 65536
```

## <a name="see-also"></a>Ayrıca bkz.

[\<iomanip >](../standard-library/iomanip.md)<br/>
