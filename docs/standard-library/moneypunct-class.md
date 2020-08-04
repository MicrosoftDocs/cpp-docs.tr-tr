---
title: moneypunct Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::moneypunct
- xlocmon/std::moneypunct::char_type
- xlocmon/std::moneypunct::string_type
- xlocmon/std::moneypunct::curr_symbol
- xlocmon/std::moneypunct::decimal_point
- xlocmon/std::moneypunct::do_curr_symbol
- xlocmon/std::moneypunct::do_decimal_point
- xlocmon/std::moneypunct::do_frac_digits
- xlocmon/std::moneypunct::do_grouping
- xlocmon/std::moneypunct::do_neg_format
- xlocmon/std::moneypunct::do_negative_sign
- xlocmon/std::moneypunct::do_pos_format
- xlocmon/std::moneypunct::do_positive_sign
- xlocmon/std::moneypunct::do_thousands_sep
- xlocmon/std::moneypunct::frac_digits
- xlocmon/std::moneypunct::grouping
- xlocmon/std::moneypunct::neg_format
- xlocmon/std::moneypunct::negative_sign
- xlocmon/std::moneypunct::pos_format
- xlocmon/std::moneypunct::positive_sign
- xlocmon/std::moneypunct::thousands_sep
helpviewer_keywords:
- std::moneypunct [C++]
- std::moneypunct [C++], char_type
- std::moneypunct [C++], string_type
- std::moneypunct [C++], curr_symbol
- std::moneypunct [C++], decimal_point
- std::moneypunct [C++], do_curr_symbol
- std::moneypunct [C++], do_decimal_point
- std::moneypunct [C++], do_frac_digits
- std::moneypunct [C++], do_grouping
- std::moneypunct [C++], do_neg_format
- std::moneypunct [C++], do_negative_sign
- std::moneypunct [C++], do_pos_format
- std::moneypunct [C++], do_positive_sign
- std::moneypunct [C++], do_thousands_sep
- std::moneypunct [C++], frac_digits
- std::moneypunct [C++], grouping
- std::moneypunct [C++], neg_format
- std::moneypunct [C++], negative_sign
- std::moneypunct [C++], pos_format
- std::moneypunct [C++], positive_sign
- std::moneypunct [C++], thousands_sep
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
ms.openlocfilehash: 8efed3cea9684c61f3bcac9eadb87b8a2b55ce09
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520946"
---
# <a name="moneypunct-class"></a>moneypunct Sınıfı

Sınıf şablonu, parasal giriş alanını veya parasal çıkış alanını temsil etmek için kullanılan *CharType* türündeki dizileri açıklayan bir yerel ayar modeli olarak işlev görebilecek bir nesne tanımlar. *Intl* şablon parametresi *true*ise uluslararası kurallar izlenir.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class CharType, bool Intl>
class moneypunct;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*Uluslararası*\
Gözlenecek uluslararası kurallara uyulup uyulmayacağını belirten bayrak.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

Sabit statik nesne Intl, *Intl*şablon parametresinin değerini depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[moneypunct](#moneypunct)|Türündeki nesnelerin Oluşturucusu `moneypunct` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[string_type](#string_type)|Türünde karakterler içeren bir dizeyi tanımlayan tür `CharType` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[curr_symbol](#curr_symbol)|Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[decimal_point](#decimal_point)|Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[do_curr_symbol](#do_curr_symbol)|Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı sanal üye işlevi.|
|[do_decimal_point](#do_decimal_point)|Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_frac_digits](#do_frac_digits)|Korumalı sanal üye işlevi herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü bir sayısını döndürür.|
|[do_grouping](#do_grouping)|Korumalı sanal üye işlevi herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[do_neg_format](#do_neg_format)|Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.|
|[do_negative_sign](#do_negative_sign)|Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_pos_format](#do_pos_format)|Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.|
|[do_positive_sign](#do_positive_sign)|Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_thousands_sep](#do_thousands_sep)|Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.|
|[frac_digits](#frac_digits)|Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü bir sayısını döndürür.|
|[gruplama](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[neg_format](#neg_format)|Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.|
|[negative_sign](#negative_sign)|Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[pos_format](#pos_format)|Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.|
|[positive_sign](#positive_sign)|Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[thousands_sep](#thousands_sep)|Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="moneypunctchar_type"></a><a name="char_type"></a>moneypunct:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType**şablon parametresi için bir eş anlamlı.

## <a name="moneypunctcurr_symbol"></a><a name="curr_symbol"></a>moneypunct:: curr_symbol

Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type curr_symbol() const;
```

### <a name="return-value"></a>Dönüş Değeri

Para birimi simgesini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_curr_symbol](#do_curr_symbol)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_curr_symbol.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct < char, true > &mpunct = use_facet < moneypunct < char, true > >(loc);
   cout << loc.name( ) << " international currency symbol "<<  mpunct.curr_symbol( ) << endl;

   const moneypunct < char, false> &mpunct2 = use_facet < moneypunct < char, false> >(loc);
   cout << loc.name( ) << " domestic currency symbol "<<  mpunct2.curr_symbol( ) << endl;
};
```

## <a name="moneypunctdecimal_point"></a><a name="decimal_point"></a>moneypunct::d ecimal_point

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_decimal_point](#do_decimal_point)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_decimal_pt.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc("german_germany");

   const moneypunct < char, true > &mpunct = use_facet
      < moneypunct < char, true > >(loc);
   cout << loc.name( ) << " international decimal point "
        << mpunct.decimal_point( ) << endl;

   const moneypunct < char, false> &mpunct2 = use_facet
      < moneypunct < char, false> >(loc);
   cout << loc.name( ) << " domestic decimal point "
        << mpunct2.decimal_point( ) << endl;
}
```

```Output
German_Germany.1252 international decimal point ,
German_Germany.1252 domestic decimal point ,
```

## <a name="moneypunctdo_curr_symbol"></a><a name="do_curr_symbol"></a>moneypunct::d o_curr_symbol

Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı sanal üye işlevi.

```cpp
virtual string_type do_curr_symbol() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [curr_symbol](#curr_symbol)için örneğe bakın `curr_symbol` .

## <a name="moneypunctdo_decimal_point"></a><a name="do_decimal_point"></a>moneypunct::d o_decimal_point

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı bir sanal üye işlevi.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [decimal_point](#decimal_point)için örneğe bakın `decimal_point` .

## <a name="moneypunctdo_frac_digits"></a><a name="do_frac_digits"></a>moneypunct::d o_frac_digits

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü sayısını döndüren korumalı bir sanal üye işlevi.

```cpp
virtual int do_frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü sayısı.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [frac_digits](#frac_digits)için örneğe bakın `frac_digits` .

## <a name="moneypunctdo_grouping"></a><a name="do_grouping"></a>moneypunct::d o_grouping

Herhangi bir ondalık noktanın solunda nasıl gruplandığını belirlemek için yerel ayara özgü bir kural döndüren korumalı bir sanal üye işlevi.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirlemek için yerel ayara özgü bir kural.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [Gruplandırma](#grouping)örneğine bakın `grouping` .

## <a name="moneypunctdo_neg_format"></a><a name="do_neg_format"></a>moneypunct::d o_neg_format

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi, negatif bir miktar için parasal çıktı alanı oluşturmayı belirlemek için yerel ayara özgü bir kural döndürür. Öğesinin dört öğelerinden her biri şu `pattern::field` değerlere sahip olabilir:

- `none`sıfır veya daha fazla boşluğu eşleştirmek veya hiçbir şey oluşturmak için.

- `sign`pozitif veya negatif bir işareti eşlemek veya oluşturmak için.

- `space`sıfır veya daha fazla boşluğu eşleştirmek veya bir boşluk oluşturmak için.

- `symbol`bir para birimi sembolünü eşleştirmek veya oluşturmak için.

- `value`bir parasal değeri eşleştirmek veya oluşturmak için.

Parasal çıkış alanının bileşenleri oluşturulur ve bir parasal giriş alanının bileşenleri, bu öğelerin içinde göründüğü sırayla eşleştirilir `pattern::field` . ,, Ve değerlerinin her biri `sign` `symbol` `value` `none` `space` tam olarak bir kez görünmelidir. Değer `none` ilk olarak gösterilmemelidir. Değer `space` ilk veya son olarak görünmemelidir. True ise, düzen,,, ve `Intl` olur `symbol` `sign` `none` `value` .

Uygulamasının şablon sürümü, `moneypunct< CharType, Intl >` döndürür `{money_base::symbol, money_base::sign, money_base::value, money_base::none}` .

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [neg_format](#neg_format)için örneğe bakın `neg_format` .

## <a name="moneypunctdo_negative_sign"></a><a name="do_negative_sign"></a>moneypunct::d o_negative_sign

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string_type do_negative_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Negatif bir işaret olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [negative_sign](#negative_sign)için örneğe bakın `negative_sign` .

## <a name="moneypunctdo_pos_format"></a><a name="do_pos_format"></a>moneypunct::d o_pos_format

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_pos_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi, pozitif bir miktar için parasal çıktı alanı oluşturmayı belirlemek için yerel ayara özgü bir kural döndürür. (Parasal giriş alanının bileşenleriyle nasıl eşleşeceğini de belirler.) Kodlama, [do_neg_format](#do_neg_format)ile aynıdır.

Uygulamasının şablon sürümü, `moneypunct< CharType, Inputlterator >` döndürür `{ money_base::symbol, money_base::sign, money_base::value, money_base::none }` .

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [pos_format](#pos_format)için örneğe bakın `pos_format` .

## <a name="moneypunctdo_positive_sign"></a><a name="do_positive_sign"></a>moneypunct::d o_positive_sign

Pozitif bir işaret olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı bir sanal üye işlevi.

```cpp
virtual string_type do_positive_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pozitif bir işaret olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [positive_sign](#positive_sign)için örneğe bakın `positive_sign` .

## <a name="moneypunctdo_thousands_sep"></a><a name="do_thousands_sep"></a>moneypunct::d o_thousands_sep

Herhangi bir ondalık noktanın solunda bir grup ayırıcısı olarak kullanılacak, yerel ayara özgü bir öğe döndüren korumalı bir sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktanın solunda Grup ayırıcı olarak kullanılacak yerel ayara özgü bir öğe.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [thousands_sep](#thousands_sep)için örneğe bakın `thousands_sep` .

## <a name="moneypunctfrac_digits"></a><a name="frac_digits"></a>moneypunct:: frac_digits

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü bir sayısını döndürür.

```cpp
int frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_frac_digits](#do_frac_digits)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_frac_digits.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true> >(loc);
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " international frac_digits\n to the right"
        << " of the radix character: "
        << mpunct.frac_digits ( ) << endl << endl;

   const moneypunct <char, false> &mpunct2 =
       use_facet <moneypunct <char, false> >(loc);
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " domestic grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct2.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " domestic frac_digits\n to the right"
        << " of the radix character: "
        << mpunct2.frac_digits ( ) << endl << endl;
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 international frac_digits
to the right of the radix character: 2

German_Germany.1252 domestic grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 domestic frac_digits
to the right of the radix character: 2
```

## <a name="moneypunctgrouping"></a><a name="grouping"></a>moneypunct:: Grouping

Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.

```cpp
string grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirlemek için yerel ayara özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_grouping](#do_grouping)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_grouping.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true> >( loc );
   for (unsigned int i = 0; i <mpunct.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " international frac_digits\n to the right"
        << " of the radix character: "
        << mpunct.frac_digits ( ) << endl << endl;

   const moneypunct <char, false> &mpunct2 =
       use_facet <moneypunct <char, false> >( loc );
   for (unsigned int i = 0; i <mpunct2.grouping( ).length( ); i++ )
   {
      cout << loc.name( ) << " domestic grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(mpunct2.grouping ( )[i])
           << endl;
   }
   cout << loc.name( ) << " domestic frac_digits\n to the right"
        << " of the radix character: "
        << mpunct2.frac_digits ( ) << endl << endl;
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 international frac_digits
to the right of the radix character: 2

German_Germany.1252 domestic grouping:
the 0th group to the left of the radix character is of size 3
German_Germany.1252 domestic frac_digits
to the right of the radix character: 2
```

## <a name="moneypunctmoneypunct"></a><a name="moneypunct"></a>moneypunct:: moneypunct

Türündeki nesnelerin Oluşturucusu `moneypunct` .

```cpp
explicit moneypunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*\
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini [locale:: model](../standard-library/locale-class.md#facet_class)(_ *refs*) ile başlatır.

## <a name="moneypunctneg_format"></a><a name="neg_format"></a>moneypunct:: neg_format

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.

```cpp
pattern neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkışları negatif tutarlarla biçimlendirmek için yerel ayara özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_neg_format](#do_neg_format)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_neg_format.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( ) {
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international negative number format: "
        << mpunct.neg_format( ).field[0]
        << mpunct.neg_format( ).field[1]
        << mpunct.neg_format( ).field[2]
        << mpunct.neg_format( ).field[3] << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic negative number format: "
        << mpunct2.neg_format( ).field[0]
        << mpunct2.neg_format( ).field[1]
        << mpunct2.neg_format( ).field[2]
        << mpunct2.neg_format( ).field[3] << endl;
}
```

## <a name="moneypunctnegative_sign"></a><a name="negative_sign"></a>moneypunct:: negative_sign

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type negative_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_negative_sign](#do_negative_sign)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_neg_sign.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true> >(loc);
   cout << loc.name( ) << " international negative sign: "
        << mpunct.negative_sign( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic negative sign: "
        << mpunct2.negative_sign( ) << endl;

   locale loc2( "French" );

   const moneypunct <char, true> &mpunct3 =
      use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international negative sign: "
        << mpunct3.negative_sign( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic negative sign: "
        << mpunct4.negative_sign( ) << endl;
};
```

```Output
German_Germany.1252 international negative sign: -
German_Germany.1252 domestic negative sign: -
French_France.1252 international negative sign: -
French_France.1252 domestic negative sign: -
```

## <a name="moneypunctpos_format"></a><a name="pos_format"></a>moneypunct::p os_format

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.

```cpp
pattern pos_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıkışları pozitif tutarlarla biçimlendirmek için yerel ayara özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_pos_format](#do_pos_format)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_pos_format.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main() {
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true> >(loc);
   cout << loc.name( ) << " international positive number format: "
        << mpunct.pos_format( ).field[0]
        << mpunct.pos_format( ).field[1]
        << mpunct.pos_format( ).field[2]
        << mpunct.pos_format( ).field[3] << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic positive number format: "
        << mpunct2.pos_format( ).field[0]
        << mpunct2.pos_format( ).field[1]
        << mpunct2.pos_format( ).field[2]
        << mpunct2.pos_format( ).field[3] << endl;
}
```

## <a name="moneypunctpositive_sign"></a><a name="positive_sign"></a>moneypunct::p ositive_sign

Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type positive_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pozitif bir işaret simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_positive_sign](#do_positive_sign)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_pos_sign.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>

using namespace std;

int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
      use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international positive sign:"
        << mpunct.positive_sign( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic positive sign:"
        << mpunct2.positive_sign( ) << endl;

   locale loc2( "French" );

   const moneypunct <char, true> &mpunct3 =
      use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international positive sign:"
        << mpunct3.positive_sign( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic positive sign:"
        << mpunct4.positive_sign( ) << endl;
};
```

```Output
German_Germany.1252 international positive sign:
German_Germany.1252 domestic positive sign:
French_France.1252 international positive sign:
French_France.1252 domestic positive sign:
```

## <a name="moneypunctstring_type"></a><a name="string_type"></a>moneypunct:: string_type

**CharType**türünde karakterler içeren bir dizeyi tanımlayan tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, nesne noktalama sıralarının kopyalarını depolayabilen [basic_string](../standard-library/basic-string-class.md) sınıf şablonu özelleştirmesi tanımlar.

## <a name="moneypunctthousands_sep"></a><a name="thousands_sep"></a>moneypunct:: thousands_sep

Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik ayırıcı olarak kullanılacak öğelerin yerel ayara özgü dizisi

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_thousands_sep](#do_thousands_sep)döndürür.

### <a name="example"></a>Örnek

```cpp
// moneypunct_thou_sep.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const moneypunct <char, true> &mpunct =
       use_facet <moneypunct <char, true > >(loc);
   cout << loc.name( ) << " international thousands separator: "
        << mpunct.thousands_sep( ) << endl;

   const moneypunct <char, false> &mpunct2 =
      use_facet <moneypunct <char, false> >(loc);
   cout << loc.name( ) << " domestic thousands separator: "
        << mpunct2.thousands_sep( ) << endl << endl;

   locale loc2( "english_canada" );

   const moneypunct <char, true> &mpunct3 =
       use_facet <moneypunct <char, true> >(loc2);
   cout << loc2.name( ) << " international thousands separator: "
        << mpunct3.thousands_sep( ) << endl;

   const moneypunct <char, false> &mpunct4 =
      use_facet <moneypunct <char, false> >(loc2);
   cout << loc2.name( ) << " domestic thousands separator: "
        << mpunct4.thousands_sep( ) << endl;
}
```

```Output
German_Germany.1252 international thousands separator: .
German_Germany.1252 domestic thousands separator: .

English_Canada.1252 international thousands separator: ,
English_Canada.1252 domestic thousands separator: ,
```

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
