---
title: '&lt;iomanıp&gt; işlevleri'
ms.date: 11/04/2016
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
ms.openlocfilehash: 7fd523dc9184ae613cf8a52969a497b6b4761cf6
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150829"
---
# <a name="ltiomanipgt-functions"></a>&lt;iomanıp&gt; işlevleri

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[tırnak işaretli](#quoted)|[resetiosflags](#resetiosflags)|
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="get_money"></a><a name="iomanip_get_money"></a>get_money

İstenen biçimi kullanarak bir akıştan parasal bir değer ayıklar ve bir parametresindeki değeri döndürür.

```cpp
template <class Money>
T7 get_money(Money& amount, bool use_intl);
```

### <a name="parameters"></a>Parametreler

*tutar*\
Ayıklanan parasal değer.

*use_intl*\
**Değer doğru**ise, uluslararası biçim kullanın. Varsayılan değer **false**'dur.

### <a name="remarks"></a>Açıklamalar

İşleici, Stream `str`ayıklandığında, `str`ile ilişkili yerel ayar modeli `money_get` `get` üye işlevini çağıran bir `formatted input function` olarak davranır ve bu da uluslararası biçimi göstermek için *use_intl* kullanılarak yapılır. Başarılı olursa, çağrı çıkarılan parasal değeri *tutar* olarak depolanır. Ardından, işleleyici `str`döndürür.

`Money`, `str`ile aynı öğe ve nitelikler parametrelerine sahip `basic_string` `long double` türünde veya bir örneklemede olmalıdır.

## <a name="get_time"></a><a name="iomanip_get_time"></a>get_time

İstenen biçimi kullanarak bir akıştan zaman değeri ayıklar. Bir parametre içindeki değeri zaman yapısı olarak döndürür.

```cpp
template <class Elem>
T10 put_time(struct tm *time_ptr, const Elem *time_format);
```

### <a name="parameters"></a>Parametreler

*time_ptr*\
Zaman yapısı biçimindeki zaman.

*time_format*\
Saat değerini elde etmek için kullanılacak biçim.

### <a name="remarks"></a>Açıklamalar

İşleici, Stream `str`ayıklandığında, `str`ile ilişkili yerel ayar `time_get` modeli için `get` üye işlevini çağıran bir `formatted input function` olarak davranır ve null sonlandırılmış bir biçim dizesinin başlangıcını göstermek için `tptr` kullanarak zaman yapısını ve `fmt` gösterir. Başarılı olursa, çağrı, ayıklanan zaman alanları ile ilişkili değerleri zaman yapısında depolar. Ardından, işleleyici `str`döndürür.

## <a name="put_money"></a><a name="iomanip_put_money"></a>put_money

İstenen biçimi bir akışa kullanarak parasal bir miktar ekler.

```cpp
template <class Money>
T8 put_money(const Money& amount, bool use_intl);
```

### <a name="parameters"></a>Parametreler

*tutar*\
Akışa eklenecek parasal miktar.

*use_intl*\
İşleyici Uluslararası biçim kullanıyorsa **true** , değilse **false** olarak ayarlayın.

### <a name="return-value"></a>Dönüş Değeri

`str` döndürür.

### <a name="remarks"></a>Açıklamalar

İşleici, akışa eklenen bir nesne döndürür `str`, `str`ilişkili yerel ayar modeli `money_put` için `put` üye işlevini çağıran bir biçimli çıkış işlevi olarak davranır. Başarılı olursa, arama `amount` uygun şekilde biçimlendirir ve *use_intl* kullanarak, bir uluslararası biçimi ve `str.fill()`, Fill öğesi olarak gösterir. Ardından, işleleyici `str`döndürür.

`Money`, `str`ile aynı öğe ve nitelikler parametrelerine sahip `basic_string` `long double` türünde veya bir örneklemede olmalıdır.

## <a name="put_time"></a><a name="iomanip_put_time"></a>put_time

Belirtilen biçimi kullanarak bir zaman yapısından bir zaman değerini akışa yazar.

```cpp
template <class Elem>
T10 put_time(struct tm* time_ptr, const Elem* time_format);
```

### <a name="parameters"></a>Parametreler

*time_ptr*\
Zaman yapısında belirtilen akışa yazılacak zaman değeri.

*time_format*\
Saat değerini yazmak için istenen biçim.

### <a name="remarks"></a>Açıklamalar

İşleici, akışa eklenen `str``formatted output function`olarak davrandığı bir nesne döndürür. Output işlevi, `str`ilişkili yerel ayar modeli `time_put` için `put` üye işlevini çağırır. Output işlevi, zaman yapısını belirtmek için *time_ptr* kullanır ve null sonlandırılmış bir biçim dizesinin başlangıcını göstermek için *time_format* . Başarılı olursa, çağrı, biçim dizesinden sabit metin ve zaman yapısından dönüştürülen değerleri ekler. Ardından, işleleyici `str`döndürür.

## <a name="quoted"></a><a name="quoted"></a>tırnak işaretli

**(C++ 14 ' te yeni)** > > Ve < < işleçlerini kullanarak, dizelerin kolayca ve dışı olmasına izin veren bir ıostream işleleyicisi.

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>Parametreler

*str*\
Std:: String, Char\*, dize sabiti veya ham dize değişmez değeri ya da bunlardan herhangi birinin geniş bir sürümü (örneğin, std:: wstring, wchar_t\*).

*sınırlayıcı*\
Dizenin başı ve sonu için sınırlayıcı olarak kullanılacak kullanıcı tanımlı bir karakter veya geniş karakter.

*kaçış*\
Dize içinde kaçış dizileri için kaçış karakteri olarak kullanılacak kullanıcı tanımlı bir karakter veya geniş karakter.

### <a name="remarks"></a>Açıklamalar

Bkz. [ekleme Işleçlerini kullanma ve biçimi denetleme](../standard-library/using-insertion-operators-and-controlling-format.md).

### <a name="example"></a>Örnek

Bu örnek, `quoted` dar dizeler kullanılarak varsayılan sınırlayıcı ve kaçış karakteriyle birlikte nasıl kullanılacağını gösterir. Geniş dizeler eşit olarak desteklenir.

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

int main(int argc, char* argv[])
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

Aşağıdaki örnek, özel bir sınırlayıcı ve/veya kaçış karakterinin nasıl alınacağını gösterir:

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

int main(int argc, char* argv[])
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

## <a name="resetiosflags"></a><a name="resetiosflags"></a>resetiosflags

Belirtilen bayrakları temizler.

```cpp
T1 resetiosflags(ios_base::fmtflags mask);
```

### <a name="parameters"></a>Parametreler

*maske*\
Temizlenecek bayraklar.

### <a name="return-value"></a>Dönüş Değeri

İşleici `str`Stream 'den ayıklandığında veya akışa eklenen bir nesne döndürür, `str.`[setf](../standard-library/ios-base-class.md#setf)`(ios_base::`[fmtflags](../standard-library/ios-base-class.md#fmtflags)`, mask)`çağırır ve ardından `str`döndürür.

### <a name="example"></a>Örnek

`resetiosflags`kullanımı örneği için bkz. [setw](../standard-library/iomanip-functions.md#setw) .

## <a name="setbase"></a><a name="setbase"></a>setbase

Tamsayılar için taban ayarla.

```cpp
T3 setbase(int base);
```

### <a name="parameters"></a>Parametreler

*temel*\
Sayı tabanı.

### <a name="return-value"></a>Dönüş Değeri

İşleici `str`Stream 'den ayıklandığında veya akışa eklenen bir nesne döndürür, `str.setf(mask,` [ios_base:: basefield](../standard-library/ios-base-class.md#fmtflags)`)`çağırır ve ardından `str`döndürür. Burada `mask` aşağıdaki şekilde belirlenir:

- *Taban* 8 ise, [`mask` `ios_base::`.](../standard-library/ios-functions.md#oct)

- *Taban* 10 ise, maske `ios_base::`[Dec](../standard-library/ios-functions.md#dec)olur.

- *Taban* 16 ise, `mask` `ios_base::`[onaltılık](../standard-library/ios-functions.md#hex)olur.

- *Taban* başka bir değer ise, maske `ios_base::`[fmtflags](../standard-library/ios-base-class.md#fmtflags)`(0)`olur.

### <a name="example"></a>Örnek

`setbase`kullanımı örneği için bkz. [setw](../standard-library/iomanip-functions.md#setw) .

## <a name="setfill"></a><a name="setfill"></a>setfill

Sağa hizalanmış bir ekranda boşlukları doldur, kullanılacak karakteri ayarlar.

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>Parametreler

*Ch*\
Sağa hizalanmış bir ekranda boşlukları dolduriçin kullanılacak karakter.

### <a name="return-value"></a>Dönüş Değeri

Bu şablon, öğesinden ayıklandığında veya akışa eklenen `str`, `str.`[fill](../standard-library/basic-ios-class.md#fill)`(Ch)`çağırır ve sonra `str`döndüren bir nesne döndürür. `Elem` türü, akış `str`öğe türüyle aynı olmalıdır.

### <a name="example"></a>Örnek

`setfill`kullanımı örneği için bkz. [setw](../standard-library/iomanip-functions.md#setw) .

## <a name="setiosflags"></a><a name="setiosflags"></a>setiosflags

Belirtilen bayrakları ayarlar.

```cpp
T2 setiosflags(ios_base::fmtflags mask);
```

### <a name="parameters"></a>Parametreler

*maske*\
Ayarlanacak bayraklar.

### <a name="return-value"></a>Dönüş Değeri

İşleici `str`, Stream 'den ayıklandığında veya akışa yerleştirildiğinde, `str.`[setf](../standard-library/ios-base-class.md#setf)`(mask)`çağırır ve sonra `str`döndüren bir nesne döndürür.

### <a name="example"></a>Örnek

`setiosflags`kullanımı örneği için bkz. [setw](../standard-library/iomanip-functions.md#setw) .

## <a name="setprecision"></a><a name="setprecision"></a>setprecision

Kayan nokta değerleri için duyarlığı ayarlar.

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>Parametreler

*Prec*\
Kayan nokta değerleri için duyarlık.

### <a name="return-value"></a>Dönüş Değeri

İşleici `str`, Stream 'den ayıklandığında veya akışa yerleştirildiğinde, `str.`[duyarlık](../standard-library/ios-base-class.md#precision)`(Prec)`çağırır ve sonra `str`döndüren bir nesne döndürür.

### <a name="example"></a>Örnek

`setprecision`kullanımı örneği için bkz. [setw](../standard-library/iomanip-functions.md#setw) .

## <a name="setw"></a><a name="setw"></a>setw

Akıştaki sonraki öğe için görüntüleme alanının genişliğini belirtir.

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>Parametreler

*Geniş*\
Görüntüleme alanının genişliği.

### <a name="return-value"></a>Dönüş Değeri

İşleici, `str`kümeden ayıklandığında veya akışa eklenen bir nesne döndürür, `str.`[width](../standard-library/ios-base-class.md#width)`(Wide)`çağırır ve sonra `str`döndürür.

### <a name="remarks"></a>Açıklamalar

setw yalnızca akıştaki bir sonraki öğe için genişliği ayarlar ve genişliğini belirtmek istediğiniz her öğeden önce eklenmelidir.

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

[iomanıp > \<](../standard-library/iomanip.md)
