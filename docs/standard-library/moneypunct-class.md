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
ms.openlocfilehash: 3a277b2f97fd53c52b705051c30eb18faf6364d0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366245"
---
# <a name="moneypunct-class"></a>moneypunct Sınıfı

Sınıf şablonu, parasal bir giriş alanını veya parasal çıktı alanını temsil etmek için kullanılan *CharType* türü dizilerini açıklamak için yerel bir yönü olarak hizmet verebilen bir nesneyi açıklar. Şablon parametresi *Intl* *doğruysa,* uluslararası sözleşmeler gözlenir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, bool Intl>
class moneypunct;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

*ıntl*\
Gözlenecek uluslararası kurallara uyulup uyulmayacağını belirten bayrak.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

Const statik nesne intl şablon parametresi *Intl*değerini depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[moneypunct](#moneypunct)|Tür `moneypunct`nesnelerin oluşturucusu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[string_type](#string_type)|Tür `CharType`karakterleri içeren bir dize açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
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
|[gruplandırma](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[neg_format](#neg_format)|Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.|
|[negative_sign](#negative_sign)|Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[pos_format](#pos_format)|Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.|
|[positive_sign](#positive_sign)|Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[thousands_sep](#thousands_sep)|Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="moneypunctchar_type"></a><a name="char_type"></a>moneypunct::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **CharType**ile eş anlamlıdır.

## <a name="moneypunctcurr_symbol"></a><a name="curr_symbol"></a>moneypunct::curr_symbol

Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type curr_symbol() const;
```

### <a name="return-value"></a>Dönüş Değeri

Para birimi simgesini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_curr_symbol](#do_curr_symbol)döndürür.

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

## <a name="moneypunctdecimal_point"></a><a name="decimal_point"></a>moneypunct::decimal_point

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık nokta sembolü olarak kullanılacak yerel öğelerdizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_decimal_point](#do_decimal_point)döndürür.

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

## <a name="moneypunctdo_curr_symbol"></a><a name="do_curr_symbol"></a>moneypunct::do_curr_symbol

Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı sanal üye işlevi.

```cpp
virtual string_type do_curr_symbol() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık nokta sembolü olarak kullanılacak yerel öğelerdizisi.

### <a name="example"></a>Örnek

Sanal üye işlevinin çağrıldığı [curr_symbol](#curr_symbol)örneğine `curr_symbol`bakın.

## <a name="moneypunctdo_decimal_point"></a><a name="do_decimal_point"></a>moneypunct::do_decimal_point

Ondalık nokta sembolü olarak kullanılmak üzere yerele özgü bir öğe dizisi döndüren korumalı sanal üye işlevi.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık nokta sembolü olarak kullanılacak yerel öğelerdizisi.

### <a name="example"></a>Örnek

Sanal üye işlevinin çağrıldığı [decimal_point](#decimal_point)örneğine `decimal_point`bakın.

## <a name="moneypunctdo_frac_digits"></a><a name="do_frac_digits"></a>moneypunct::do_frac_digits

Herhangi bir ondalık noktanın sağına görüntülenecek basamak sayısının yerele özgü sayısını döndüren korumalı sanal üye işlevi.

```cpp
virtual int do_frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktanın sağında görüntülenecek basamak sayısının yerele özgü sayısı.

### <a name="example"></a>Örnek

Sanal üye [frac_digits](#frac_digits)işlevin `frac_digits`çağrıldığı frac_digits örneğine bakın.

## <a name="moneypunctdo_grouping"></a><a name="do_grouping"></a>moneypunct::do_grouping

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirlemek için yerelkurala özgü bir kuralı döndüren korumalı sanal üye işlevi.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırılmayı belirlemek için yerele özgü bir kural.

### <a name="example"></a>Örnek

Sanal üye işlevin çağrıldığı [gruplandırma](#grouping)örneğine `grouping`bakın.

## <a name="moneypunctdo_neg_format"></a><a name="do_neg_format"></a>moneypunct::do_neg_formatı

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi, negatif bir tutar için parasal çıktı alanının nasıl oluşturunu belirlemek için yerele özgü bir kural döndürür. Dört öğenin `pattern::field` her biri değerlere sahip olabilir:

- `none`sıfır veya daha fazla boşluk eşleştirmek veya hiçbir şey oluşturmak için.

- `sign`eşleştirmek veya pozitif veya olumsuz bir işaret oluşturmak için.

- `space`sıfır veya daha fazla boşluk eşleştirmek veya bir boşluk oluşturmak için.

- `symbol`eşleştirmek veya bir para birimi simgesi oluşturmak için.

- `value`eşleştirmek veya parasal bir değer oluşturmak için.

Parasal çıktı alanının bileşenleri oluşturulur ve parasal giriş alanının bileşenleri bu öğelerin görünür `pattern::field`sırasına göre eşleşir. Değerlerin `sign`her biri `symbol` `value`, , `none` `space` , , veya tam olarak bir kez görünmesi gerekir. Değer `none` önce görünmemelidir. Değer alanı ilk veya son **görünmemelidir.** Eğer `Intl` doğruysa, sıra `symbol`, `sign` `none`, `value`, o zaman .

`moneypunct` \< **CharType**şablon sürümü , **Intl**> money_base döndürür::sembol `{` **money_base::symbol**, **money_base:: işaret**, **money_base::değer**, **money_base::yok**`}`.

### <a name="example"></a>Örnek

Sanal üye işlevinin çağrıldığı [neg_format](#neg_format)örneğine `neg_format`bakın.

## <a name="moneypunctdo_negative_sign"></a><a name="do_negative_sign"></a>moneypunct::do_negative_sign

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string_type do_negative_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Negatif işaret olarak kullanılacak yerel öğeler dizisi.

### <a name="example"></a>Örnek

Sanal üye [negative_sign](#negative_sign)işlevinin negative_sign tarafından `negative_sign`çağrıldığı negative_sign örneğine bakın.

## <a name="moneypunctdo_pos_format"></a><a name="do_pos_format"></a>moneypunct::do_pos_formatı

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_pos_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi, pozitif bir miktar için parasal çıktı alanının nasıl oluşturunu belirlemek için yerele özgü bir kural döndürür. (Ayrıca, parasal giriş alanının bileşenlerinin nasıl eşleşecek lerini de belirler.) Kodlama [do_neg_format](#do_neg_format)için aynıdır.

Moneypunct\< **CharType**şablon sürümü , **Inputlterator**> money_base döndürür::sembol `{` **money_base::symbol**, **money_base::sign**, **money_base::değer**, **money_base::yok**`}`.

### <a name="example"></a>Örnek

Sanal üye işlevinin çağrıldığı [pos_format](#pos_format)örneğine `pos_format`bakın.

## <a name="moneypunctdo_positive_sign"></a><a name="do_positive_sign"></a>moneypunct::do_positive_sign

Olumlu bir işaret olarak kullanmak üzere yerele özgü bir öğe dizisini döndüren korumalı sanal üye işlevi.

```cpp
virtual string_type do_positive_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Olumlu bir işaret olarak kullanılacak yerel öğelerdizisi.

### <a name="example"></a>Örnek

Sanal üye işlevinin çağrıldığı [positive_sign](#positive_sign)örneğine `positive_sign`bakın.

## <a name="moneypunctdo_thousands_sep"></a><a name="do_thousands_sep"></a>moneypunct::do_bins_sep

Herhangi bir ondalık noktanın solunda grup ayırıcısı olarak kullanmak üzere yerel öğeye özgü bir öğeyi döndüren korumalı sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktanın solunda grup ayırıcıolarak kullanılacak yerelöğeözgü bir öğe.

### <a name="example"></a>Örnek

Sanal üye [thousands_sep](#thousands_sep)işlevinin `thousands_sep`çağrıldığı thousands_sep örneğine bakın.

## <a name="moneypunctfrac_digits"></a><a name="frac_digits"></a>moneypunct::frac_digits

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü bir sayısını döndürür.

```cpp
int frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktanın sağında görüntülenecek basamak sayısının yerele özgü sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_frac_digits](#do_frac_digits)döndürür.

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

## <a name="moneypunctgrouping"></a><a name="grouping"></a>moneypunct::gruplandırma

Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.

```cpp
string grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırılmayı belirlemek için yerele özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_grouping](#do_grouping)döndürür.

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

## <a name="moneypunctmoneypunct"></a><a name="moneypunct"></a>moneypunct::moneypunct

Tür `moneypunct`nesnelerin oluşturucusu.

```cpp
explicit moneypunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_refs*\
Nesneiçin bellek yönetimi türünü belirtmek için kullanılan eden arameger değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve önemi şunlardır:

- 0: Nesnenin ömrü, onu içeren yerel nesneler tarafından yönetilir.

- 1: Nesnenin ömrü el ile yönetilmelidir.

- \>1: Bu değerler tanımlı değildir.

Yıkıcı korunduğundan, doğrudan örnek yoktur.

Oluşturucu, temel nesnesini yerel olarak [başlatleştirir::fakal](../standard-library/locale-class.md#facet_class)(_ *Refs).*

## <a name="moneypunctneg_format"></a><a name="neg_format"></a>moneypunct::neg_format

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.

```cpp
pattern neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıktıları negatif tutarlarla biçimlendirmek için yerele özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_neg_format](#do_neg_format)döndürür.

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

## <a name="moneypunctnegative_sign"></a><a name="negative_sign"></a>moneypunct::negative_sign

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type negative_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_negative_sign](#do_negative_sign)döndürür.

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

## <a name="moneypunctpos_format"></a><a name="pos_format"></a>moneypunct::pos_formatı

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.

```cpp
pattern pos_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çıktıları pozitif tutarlarla biçimlendirmek için yerele özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_pos_format](#do_pos_format)döndürür.

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

## <a name="moneypunctpositive_sign"></a><a name="positive_sign"></a>moneypunct::positive_sign

Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type positive_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pozitif işaret sembolü olarak kullanılacak yerel öğeler dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_positive_sign](#do_positive_sign)döndürür.

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

## <a name="moneypunctstring_type"></a><a name="string_type"></a>moneypunct::string_type

**CharType**türünde karakterler içeren bir dize açıklayan bir tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, nesneleri noktalama işaretlerinin kopyalarını depolayabilen sınıf şablonu [basic_string](../standard-library/basic-string-class.md) bir uzmanlık açıklar.

## <a name="moneypunctthousands_sep"></a><a name="thousands_sep"></a>moneypunct::thousands_sep

Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlerce ayırıcı olarak kullanılacak yerel öğelerdizisi

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_thousands_sep](#do_thousands_sep)döndürür.

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

[\<yerel>](../standard-library/locale.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
