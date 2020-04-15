---
title: '&lt;iomanip&gt; fonksiyonları'
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
ms.openlocfilehash: 0ed59a94c6b1c7d962b566e2a6b186ffb617a26a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81375421"
---
# <a name="ltiomanipgt-functions"></a>&lt;iomanip&gt; fonksiyonları

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[Alıntı](#quoted)|[resetiosflags](#resetiosflags)|
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="get_money"></a><a name="iomanip_get_money"></a>get_money

İstenilen biçimi kullanarak bir akıştan parasal bir değer ayıklar ve bir parametredeki değeri döndürür.

```cpp
template <class Money>
T7 get_money(Money& amount, bool use_intl);
```

### <a name="parameters"></a>Parametreler

*Tutar*\
Çıkarılan parasal değer.

*use_intl*\
**Doğruysa,** uluslararası format kullanın. Varsayılan değer **false** şeklindedir.

### <a name="remarks"></a>Açıklamalar

`str`Manipülatör, akıştan çıkarıldığında, uluslararası biçimi belirtmek için *use_intl* kullanarak `money_get` ilişkili `str` `get` yerel falaiçin üye işlevi çağıran bir `formatted input function` nesne döndürür. Başarılı olursa, çağrı çıkarılan parasal değeri *tutarda* depolar. Manipülatör daha `str`sonra döner.

`Money`türü `long double` nde veya aynı eleman `basic_string` ve özellikleri parametreleri `str`ile bir anlık olmalıdır.

## <a name="get_time"></a><a name="iomanip_get_time"></a>get_time

İstenilen biçimi kullanarak bir akıştan bir zaman değeri ayıklar. Parametredeki değeri zaman yapısı olarak döndürür.

```cpp
template <class Elem>
T10 put_time(struct tm *time_ptr, const Elem *time_format);
```

### <a name="parameters"></a>Parametreler

*time_ptr*\
Zaman yapısı şeklinde ki zaman.

*time_format*\
Zaman değerini elde etmek için kullanılacak istenen biçim.

### <a name="remarks"></a>Açıklamalar

Manipülatör, `str`akıştan çıkarıldığında, zaman yapısını belirtmek ve `formatted input function` `get` `time_get` `str` `tptr` `fmt` null-sonlandırılan biçim dizesinin başlangıcını belirtmek için kullanarak ilişkili yerel fatur için üye işlevi çağıran bir nesne olarak işlev görür. Başarılı olursa, çağrı zaman yapısında çıkarılan zaman alanlarıyla ilişkili değerleri depolar. Manipülatör daha `str`sonra döner.

## <a name="put_money"></a><a name="iomanip_put_money"></a>put_money

İstenilen biçimi kullanarak bir akışa parasal bir tutar ekler.

```cpp
template <class Money>
T8 put_money(const Money& amount, bool use_intl);
```

### <a name="parameters"></a>Parametreler

*Tutar*\
Akışa eklenecek parasal tutar.

*use_intl*\
Manipülatör uluslararası formatı kullanmalıdır **eğer** **doğru** ayarlayın, yanlış eğer olmamalıdır.

### <a name="return-value"></a>Dönüş Değeri

`str` döndürür.

### <a name="remarks"></a>Açıklamalar

Manipülatör, `str`akışa eklendiğinde, ilişkili yerel fala `put` `money_put` için üye işlevi çağıran biçimlendirilmiş bir çıkış işlevi gibi görünen `str`bir nesne döndürür. Başarılı olursa, `amount` arama, uluslararası biçimi belirtmek için *use_intl* kullanarak `str.fill()`uygun biçimlendirilmiş ve dolgu öğesi olarak ekler. Manipülatör daha `str`sonra döner.

`Money`türü `long double` nde veya aynı eleman `basic_string` ve özellikleri parametreleri `str`ile bir anlık olmalıdır.

## <a name="put_time"></a><a name="iomanip_put_time"></a>put_time

Belirli bir biçimi kullanarak bir zaman yapısından bir akışa bir zaman değeri yazar.

```cpp
template <class Elem>
T10 put_time(struct tm* time_ptr, const Elem* time_format);
```

### <a name="parameters"></a>Parametreler

*time_ptr*\
Akışa yazılması gereken zaman değeri, bir zaman yapısında sağlanır.

*time_format*\
Zaman değerini yazmak için istenen biçim.

### <a name="remarks"></a>Açıklamalar

Manipülatör, akışa `str`eklendiğinde `formatted output function`bir . Çıktı işlevi, '' `put` ile `str`ilişkili yerel `time_put` fason için üye işlevi çağırır. Çıktı işlevi, zaman yapısını belirtmek için *time_ptr* kullanır ve null-sonlandırılan biçim dizesinin başlangıcını belirtmek için *time_format.* Başarılı olursa, çağrı biçim dizesinden gerçek metin ekler ve zaman yapısından dönüştürülmüş değerler. Manipülatör daha `str`sonra döner.

## <a name="quoted"></a><a name="quoted"></a>Alıntı

**(C++14'te yeni)** >> ve << işleçlerini kullanarak dizelerin akışlara uygun bir şekilde yuvarlanmasını ve dışarısını sağlayan bir iostream manipülatörü.

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>Parametreler

*Str*\
Bir std::string,\*char, dize literal veya ham dize literal, ya da bunlardan herhangi biri\*geniş bir sürümü (örneğin std::wstring, wchar_t).

*Sınırlayıcı*\
Kullanıcı tarafından belirtilen karakter veya geniş karakter, dize başlangıcı ve sonu için sınırlayıcı olarak kullanmak.

*Kaçış*\
Kullanıcı tarafından belirtilen karakter veya geniş karakter, dize içinde kaçış dizileri için kaçış karakteri olarak kullanmak.

### <a name="remarks"></a>Açıklamalar

Bkz. [Ekleme Operatörlerini Kullanma ve Biçimi Denetleme](../standard-library/using-insertion-operators-and-controlling-format.md).

### <a name="example"></a>Örnek

Bu örnek, dar `quoted` dizeleri kullanarak varsayılan sınırlayıcı ve kaçış karakteri ile nasıl kullanılacağını gösterir. Geniş dizeleri eşit olarak desteklenir.

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

Aşağıdaki örnek, özel bir sınırlayıcı ve/veya kaçış karakterinin nasıl sağlayabileceğini gösterir:

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

*Maske*\
Bayraklar temize çıktı.

### <a name="return-value"></a>Dönüş Değeri

`str`Manipülatör, akıştan çıkarıldığında veya akışa eklendiğinde `str.` [setf](../standard-library/ios-base-class.md#setf)`(ios_base::`[fmtflags'i](../standard-library/ios-base-class.md#fmtflags)`, mask)`çağıran ve `str`sonra döndüren bir nesneyi döndürür.

### <a name="example"></a>Örnek

Kullanma `resetiosflags`örneği için [setw'ye](../standard-library/iomanip-functions.md#setw) bakın.

## <a name="setbase"></a><a name="setbase"></a>setbase

Sayışörler için taban ayarlayın.

```cpp
T3 setbase(int base);
```

### <a name="parameters"></a>Parametreler

*Temel*\
Sayı tabanı.

### <a name="return-value"></a>Dönüş Değeri

Manipülatör, akıştan `str`çıkarıldığında veya akışa eklendiğinde ios_base `str.setf(mask,` [çağıran](../standard-library/ios-base-class.md#fmtflags)`)`bir nesneyi döndürür `str`ve sonra döndürür. Burada, `mask` aşağıdaki gibi belirlenir:

- *Taban* 8 ise, `mask` `ios_base::`o zaman [ekim](../standard-library/ios-functions.md#oct)olduğunu.

- *Taban* 10 ise, o `ios_base::`zaman maske [aralık.](../standard-library/ios-functions.md#dec)

- *Taban* 16 ise, `mask` `ios_base::`o zaman [hex](../standard-library/ios-functions.md#hex)olduğunu.

- *Taban* başka bir değer ise, `ios_base::`o zaman maske [fmtflags](../standard-library/ios-base-class.md#fmtflags)`(0)`olduğunu.

### <a name="example"></a>Örnek

Kullanma `setbase`örneği için [setw'ye](../standard-library/iomanip-functions.md#setw) bakın.

## <a name="setfill"></a><a name="setfill"></a>setfill

Boşlukları doğru bir ekranda doldurmak için kullanılacak karakteri ayarlar.

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>Parametreler

*Caner*\
Boşlukları sağ gerekçeli bir ekranda doldurmak için kullanılacak karakter.

### <a name="return-value"></a>Dönüş Değeri

`str`Şablon manipülatörü, akıştan çıkarıldığında veya akışa eklendiğinde, `str.` [çağrıların doldurup](../standard-library/basic-ios-class.md#fill)`(Ch)`sonra döndürdeğini sağlayan bir nesne döndürür. `str` Tür, `Elem` akış `str`için öğe türüyle aynı olmalıdır.

### <a name="example"></a>Örnek

Kullanma `setfill`örneği için [setw'ye](../standard-library/iomanip-functions.md#setw) bakın.

## <a name="setiosflags"></a><a name="setiosflags"></a>setiosflags

Belirtilen bayrakları ayarlar.

```cpp
T2 setiosflags(ios_base::fmtflags mask);
```

### <a name="parameters"></a>Parametreler

*Maske*\
Ayarlanan bayraklar.

### <a name="return-value"></a>Dönüş Değeri

Manipülatör, akıştan `str`çıkarıldığında veya akışa eklendiğinde `str.` [setf](../standard-library/ios-base-class.md#setf)`(mask)`çağıran ve sonra `str`döndüren bir nesne döndürür.

### <a name="example"></a>Örnek

Kullanma `setiosflags`örneği için [setw'ye](../standard-library/iomanip-functions.md#setw) bakın.

## <a name="setprecision"></a><a name="setprecision"></a>setprecision

Kayan nokta değerleri için hassasiyeti ayarlar.

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>Parametreler

*Prec*\
Kayan nokta değerleri için kesinlik.

### <a name="return-value"></a>Dönüş Değeri

Manipülatör, akıştan `str`çıkarıldığında veya akışa eklendiğinde, `str.` [hassas](../standard-library/ios-base-class.md#precision)`(Prec)`çağrıları çağıran ve `str`sonra döndüren bir nesne döndürür.

### <a name="example"></a>Örnek

Kullanma `setprecision`örneği için [setw'ye](../standard-library/iomanip-functions.md#setw) bakın.

## <a name="setw"></a><a name="setw"></a>setw

Akıştaki bir sonraki öğe için görüntü alanının genişliğini belirtir.

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>Parametreler

*Geniş*\
Görüntü alanının genişliği.

### <a name="return-value"></a>Dönüş Değeri

Manipülatör, akıştan `str`çıkarıldığında veya akışa eklendiğinde `str.` [genişliği](../standard-library/ios-base-class.md#width)`(Wide)`çağıran bir nesneyi döndürür, sonra döner. `str`

### <a name="remarks"></a>Açıklamalar

setw genişliği yalnızca akıştaki bir sonraki öğe için ayarlar ve genişliğini belirtmek istediğiniz her öğeden önce eklenmelidir.

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

[\<iomanip>](../standard-library/iomanip.md)
