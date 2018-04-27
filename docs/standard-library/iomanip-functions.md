---
title: '&lt;iomanip&gt; işlevleri | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 10
manager: ghogen
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
ms.openlocfilehash: 7926526b803436718eea3f95d3bf74d7f99eca6b
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ltiomanipgt-functions"></a>&lt;iomanip&gt; işlevleri

||||
|-|-|-|
|[get_money](#iomanip_get_money)|[get_time](#iomanip_get_time)|[put_money](#iomanip_put_money)|
|[put_time](#iomanip_put_time)|[tırnak içine alınmış](#quoted)|[resetiosflags](#resetiosflags)|
|[setbase](#setbase)|[setfill](#setfill)|[setiosflags](#setiosflags)|
|[setprecision](#setprecision)|[setw](#setw)|

## <a name="iomanip_get_money"></a>  get_money

Bir para değeri istenen biçimi kullanarak bir akıştan ayıklar ve bir parametre değeri döndürür.

```cpp
template <class Money>
T7 get_money(Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>Parametreler

_Amount ayıklanan para değeri.

_Intl varsa `true`, uluslararası biçimini kullanın. Varsayılan değer `false` şeklindedir.

### <a name="remarks"></a>Açıklamalar

Manipulator bir nesne, akıştan ayıklandığında döndüren `str`, olarak davranan bir `formatted input function` üye işlevi çağırır `get` yerel ayar modelinin `money_get` ile ilişkili `str`kullanarak `_Intl` için Uluslararası biçim belirtin. Başarılı, çağrı depolar, `_Amount` ayıklanan para değeri. Manipulator sonra döndürür `str`.

`Money` türünde olmalıdır `long double` veya bir örnek oluşturma, `basic_string` aynı öğe ve nitelikler parametreleri ile `str`.

## <a name="iomanip_get_time"></a>  get_time

Bir saat değeri istenen biçimi kullanarak bir akıştan ayıklar. Değer bir parametre bir zaman yapısı döndürür.

```cpp
template <class Elem>
T10 put_time(struct tm *_Tptr, const Elem *_Fmt);
```

### <a name="parameters"></a>Parametreler

`_Tptr` Zaman yapısı form süre.

`_Fmt` Saat değeri elde etmek için kullanılacak istenen biçimi.

### <a name="remarks"></a>Açıklamalar

Manipulator bir nesne, akıştan ayıklandığında döndüren `str`, olarak davranan bir `formatted input function` üye işlevi çağırır `get` yerel ayar modelinin `time_get` ile ilişkili `str`kullanarak `tptr` için zaman yapısı belirtmek ve `fmt` null ile sonlandırılmış biçim dizesi başlangıcını belirtmek için. Başarılı olursa, çağrı süresi yapısında herhangi ayıklanan zaman alanlarla ilişkili değerleri depolar. Manipulator sonra döndürür `str`.

## <a name="iomanip_put_money"></a>  put_money

Bir akışa istenen biçimini kullanarak parasal tutar ekler.

```cpp
template <class Money>
T8 put_money(const Money& _Amount, bool _Intl);
```

### <a name="parameters"></a>Parametreler

`_Amount` Akışa eklemek için parasal tutar.

`_Intl` Kümesine `true` manipulator uluslararası biçimini kullanması gerekiyorsa `false` olmaması gerektiği durumunda.

### <a name="return-value"></a>Dönüş Değeri

Döndürür `str`.

### <a name="remarks"></a>Açıklamalar

Manipulator nesneyi akışa eklendiğinde döner `str`, üye işlevi çağıran bir biçimlendirilmiş çıkışı işlev davranır `put` yerel ayar modelinin `money_put` ile ilişkili `str`. Başarılı, çağrı ekler, `amount` düzgün biçimlendirilmiş, kullanarak `_Intl` uluslararası biçimini belirtmek için ve `str.fill()`, dolgu öğesi olarak. Manipulator sonra döndürür `str`.

`Money` türünde olmalıdır `long double` veya bir örnek oluşturma, `basic_string` aynı öğe ve nitelikler parametreleri ile `str`.

## <a name="iomanip_put_time"></a>  put_time

Bir saat değeri belirtilen biçimi kullanarak bir zaman yapısından bir akışa yazar.

```cpp
template <class Elem>
T10 put_time(struct tm* _Tptr, const Elem* _Fmt);
```

### <a name="parameters"></a>Parametreler

`_Tptr` Zaman yapısı içinde sağlanan akış yazmak için zaman değeri.

`_Fmt` Saat değeri yazmak için istenen biçimi.

### <a name="remarks"></a>Açıklamalar

Manipulator nesneyi akışa eklendiğinde döner `str`, olarak davranan bir `formatted output function`. Çıktı işlevi üye işlevini çağırır `put` yerel ayar modelinin `time_put` ile ilişkili `str`. Çıktı işlevini kullanıyor `_Tptr` zaman yapısı göstermek için ve `_Fmt` NUL sonlandırılmış biçim dizesi başlangıcını belirtmek için. Başarılı olursa, arama metin zaman yapısı dönüştürülmüş değerleri ve biçim dizesi ekler. Manipulator sonra döndürür `str`.

## <a name="quoted"></a>  tırnak içine alınmış

**(Yeni C ++ 14 inç)**  Uygun gidiş dizeleri içine ve işyeri dışında sağlayan bir iostream manipulator akışları kullanarak >> ve << işleçler.

```cpp
quoted(std::string str) // or wstring
quoted(const char* str) //or wchar_t*
quoted(std::string str, char delimiter, char escape) // or wide versions
quoted(const char* str, char delimiter, char escape) // or wide versions
```

### <a name="parameters"></a>Parametreler

`str` Bir std::string, char *, dize sabit değeri veya ham dize sabit değeri veya bunları herhangi biri geniş bir sürümünü (ör. std::wstring, wchar_t\*).

`delimiter` Bir kullanıcı tarafından belirtilen karakter veya başlangıç ve bitiş dizesi için ayırıcı olarak kullanmak üzere geniş karakter.

`escape` Bir kullanıcı tarafından belirtilen karakter veya dizedeki kaçış sıraları kaçış karakteri olarak kullanılmak üzere geniş karakter.

### <a name="remarks"></a>Açıklamalar

Bkz: [ekleme işleçlerini kullanma ve biçimi denetleme](../standard-library/using-insertion-operators-and-controlling-format.md).

### <a name="example"></a>Örnek

Bu örnek nasıl kullanılacağını gösterir `quoted` varsayılan sınırlayıcı ve kaçış karakteri kullanarak dizeleri daraltın. Geniş dizeleri eşit olarak desteklenir.

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

Belirtilen bayrakları temizler.

```cpp
T1 resetiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>Parametreler

`Mask` Temizlemek için işaretler.

### <a name="return-value"></a>Dönüş Değeri

Manipulator bir nesne, ayıklanan veya akışa eklenen döndüren **str**, çağrıları **str**. [setf](../standard-library/ios-base-class.md#setf)( `ios_base::` [fmtflags](../standard-library/ios-base-class.md#fmtflags), _ *maskesi*) ve ardından döndürür **str**.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `resetiosflags`.

## <a name="setbase"></a>  setbase

Tamsayıları için temel olarak ayarlayın.

```cpp
T3 setbase(int _Base);
```

### <a name="parameters"></a>Parametreler

`_Base` Temel sayı.

### <a name="return-value"></a>Dönüş Değeri

Manipulator bir nesne, ayıklanan veya akışa eklenen döndüren **str**, çağrıları **str**. `setf`( **maskesi**, [ios_base::basefield](../standard-library/ios-base-class.md#fmtflags)) ve ardından döndürür **str**. Burada, **maskesi** şu şekilde belirlenir:

- Varsa _ *temel* 8 ise **maskesi** olan `ios_base::` [Eki](../standard-library/ios-functions.md#oct).

- Varsa _ *temel* 10'dur ve ardından maskesidir `ios_base::` [Ara](../standard-library/ios-functions.md#dec).

- Varsa _ *temel* 16, ise **maskesi** olan `ios_base::` [onaltılık](../standard-library/ios-functions.md#hex).

- Varsa _ *temel* maskesidir diğer herhangi bir değer olduğundan `ios_base::` [fmtflags](../standard-library/ios-base-class.md#fmtflags)(0).

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setbase`.

## <a name="setfill"></a>  setfill

Sağa hizalı görüntü alanları doldurmak için kullanılan karakter ayarlar.

```cpp
template <class Elem>
T4 setfill(Elem Ch);
```

### <a name="parameters"></a>Parametreler

`Ch` Sağa hizalı görüntü alanları doldurmak için kullanılan karakter.

### <a name="return-value"></a>Dönüş Değeri

Şablon manipulator bir nesne, ayıklanan veya akışa eklenen döndüren **str**, çağrıları **str**. [Dolgu](../standard-library/basic-ios-class.md#fill)( `Ch`) ve ardından döndürür **str**. Türü **Elem** akışın öğe türü ile aynı olmalıdır **str**.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setfill`.

## <a name="setiosflags"></a>  setiosflags

Belirtilen bayrakları ayarlar.

```cpp
T2 setiosflags(ios_base::fmtflags Mask);
```

### <a name="parameters"></a>Parametreler

`Mask` Ayarlamak için işaretler.

### <a name="return-value"></a>Dönüş Değeri

Manipulator bir nesne, ayıklanan veya akışa eklenen döndüren **str**, çağrıları **str**. [setf](../standard-library/ios-base-class.md#setf)(_ *maskesi*) ve ardından döndürür **str**.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setiosflags`.

## <a name="setprecision"></a>  setprecision

Kayan nokta değerlerinin duyarlık ayarlar.

```cpp
T5 setprecision(streamsize Prec);
```

### <a name="parameters"></a>Parametreler

`Prec` Kayan nokta değerlerinin duyarlık.

### <a name="return-value"></a>Dönüş Değeri

Manipulator bir nesne, ayıklanan veya akışa eklenen döndüren **str**, çağrıları **str**. [Duyarlık](../standard-library/ios-base-class.md#precision)( `Prec`) ve ardından döndürür **str**.

### <a name="example"></a>Örnek

Bkz: [setw](../standard-library/iomanip-functions.md#setw) kullanma örneği için `setprecision`.

## <a name="setw"></a>  setw

Akışta sonraki öğeye görüntü alanın genişliğini belirtir.

```cpp
T6 setw(streamsize Wide);
```

### <a name="parameters"></a>Parametreler

`Wide` Görüntü alanı genişliği.

### <a name="return-value"></a>Dönüş Değeri

Manipulator bir nesne, ayıklanan veya akışa eklenen döndüren **str**, çağrıları **str**. [Genişlik](../standard-library/ios-base-class.md#width)(_ *geniş*), ardından döndürür **str**.

### <a name="remarks"></a>Açıklamalar

setw genişliğini yalnızca sonraki öğeye akışta ayarlar ve genişliği belirtmek istediğiniz her öğenin önce eklenmesi gerekir.

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
