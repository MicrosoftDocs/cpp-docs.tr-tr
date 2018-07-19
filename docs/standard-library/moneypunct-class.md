---
title: moneypunct sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ed808d8b28071978e89d873d0af9735167e4dbf
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38957515"
---
# <a name="moneypunct-class"></a>moneypunct Sınıfı

Şablon sınıfı türü dizileri tanımlamak için bir yerel ayar modeli hizmet verebilen bir nesneyi tanımlayan *CharType* bir parasal giriş alanını veya parasal çıkış alanını temsil etmek için kullanılır. Şablon parametresi *INTL* olduğu *true*, uluslararası kurallar gözlenir.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, bool Intl>
class moneypunct;
```

### <a name="parameters"></a>Parametreler

*CharType* bir program içindeki karakterleri kodlamak için kullanılan tür.

*Uluslararası* gözlenecek uluslararası kurallara olup olmadığını belirten bir bayrak.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

Sabit statik nesne intl şablon parametresinin değerini depolar *INTL*.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[moneypunct](#moneypunct)|Türü nesnelerin Oluşturucusu `moneypunct`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[string_type](#string_type)|Türü karakterler içeren dizeyi tanımlayan tür `CharType`.|

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
|[Gruplandırma](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[neg_format](#neg_format)|Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.|
|[negative_sign](#negative_sign)|Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[pos_format](#pos_format)|Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.|
|[positive_sign](#positive_sign)|Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|
|[thousands_sep](#thousands_sep)|Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  moneypunct::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **CharType**.

## <a name="curr_symbol"></a>  moneypunct::curr_symbol

Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type curr_symbol() const;
```

### <a name="return-value"></a>Dönüş Değeri

Para birimi sembolü içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_curr_symbol](#do_curr_symbol).

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

## <a name="decimal_point"></a>  moneypunct::decimal_point

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_decimal_point](#do_decimal_point).

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

## <a name="do_curr_symbol"></a>  moneypunct::do_curr_symbol

Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı sanal üye işlevi.

```cpp
virtual string_type do_curr_symbol() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bakın [curr_symbol](#curr_symbol), sanal üye işlevi çağıran burada `curr_symbol`.

## <a name="do_decimal_point"></a>  moneypunct::do_decimal_point

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı sanal üye işlevi.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bakın [decimal_point](#decimal_point), sanal üye işlevi çağıran burada `decimal_point`.

## <a name="do_frac_digits"></a>  moneypunct::do_frac_digits

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü sayımını döndürür ve korumalı sanal üye işlevi.

```cpp
virtual int do_frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü sayı.

### <a name="example"></a>Örnek

Örneğin bakın [frac_digits](#frac_digits), sanal üye işlevi çağıran burada `frac_digits`.

## <a name="do_grouping"></a>  moneypunct::do_grouping

Basamak herhangi bir ondalık noktasının solunda nasıl belirleneceğine yönelik yerel ayara özgü kural döndürür ve korumalı sanal üye işlevi.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamak herhangi bir ondalık noktasının solunda nasıl belirleneceğine yönelik yerel ayara özgü kural.

### <a name="example"></a>Örnek

Örneğin bakın [gruplandırma](#grouping), sanal üye işlevi çağıran burada `grouping`.

## <a name="do_neg_format"></a>  moneypunct::do_neg_format

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi için negatif bir tutar parasal çıkış alanını oluşturmak nasıl belirlemek için bir yerel ayara özgü kural döndürür. Her dört öğe `pattern::field` değerlere sahip olabilir:

- `none` eşleşen sıfır veya daha fazla boşluk veya hiçbir şey oluşturmak için.

- `sign` eşleşen ya da artı veya eksi işareti oluşturmak için.

- `space` eşleşen sıfır veya daha fazla boşluk veya bir alan oluşturmak için.

- `symbol` eşleşen veya bir para birimi sembolü oluşturmak için.

- `value` eşleşen veya parasal bir değeri oluşturmak için.

Parasal çıkış alanını bileşenlerinin oluşturulur ve bir parasal giriş alanını bileşenlerinin bu öğelerin görüntüleneceği içinde sırayla eşleştirilir `pattern::field`. Değerlerin her birini `sign`, `symbol`, `value`ve her iki `none` veya `space` tam bir kez görünmelidir. Değer `none` ilk görünmemelidir. Değer alanı **gerekir** ilk veya son görünmüyor. Varsa `Intl` sırasıdır true ise `symbol`, `sign`, `none`, ardından `value`.

Şablon sürümünü `moneypunct` \< **CharType**, **INTL**> döndürür `{` **money_base::symbol**, **money_ Base::Sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Örnek

Örneğin bakın [neg_format](#neg_format), sanal üye işlevi çağıran burada `neg_format`.

## <a name="do_negative_sign"></a>  moneypunct::do_negative_sign

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string_type do_negative_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir eksi işareti kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bakın [negative_sign](#negative_sign), sanal üye işlevi çağıran burada `negative_sign`.

## <a name="do_pos_format"></a>  moneypunct::do_pos_format

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_pos_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye işlevi için pozitif bir tutar parasal çıkış alanını oluşturmak nasıl belirlemek için bir yerel ayara özgü kural döndürür. (Ayrıca bir parasal giriş alanını bileşenlerinin eşleşecek şekilde nasıl belirler.) Kodlama aynı olan [do_neg_format](#do_neg_format).

Moneypunct şablon sürümünü\< **CharType**, **Inputlterator**> döndürür `{` **money_base::symbol**, **para _base::Sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Örnek

Örneğin bakın [pos_format](#pos_format), sanal üye işlevi çağıran burada `pos_format`.

## <a name="do_positive_sign"></a>  moneypunct::do_positive_sign

Pozitif işareti kullanılacak öğelerin yerel ayara özgü bir dizisini döndüren korumalı sanal üye işlevi.

```cpp
virtual string_type do_positive_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pozitif işareti kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bakın [positive_sign](#positive_sign), sanal üye işlevi çağıran burada `positive_sign`.

## <a name="do_thousands_sep"></a>  moneypunct::do_thousands_sep

Herhangi bir ondalık noktasının solunda bir Grup ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür ve korumalı sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktasının solunda bir grup ayracı olarak kullanılacak yerel ayara özgü bir öğeyi.

### <a name="example"></a>Örnek

Örneğin bakın [thousands_sep](#thousands_sep), sanal üye işlevi çağıran burada `thousands_sep`.

## <a name="frac_digits"></a>  moneypunct::frac_digits

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü bir sayısını döndürür.

```cpp
int frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü sayı.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_frac_digits](#do_frac_digits).

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

## <a name="grouping"></a>  moneypunct::Grouping

Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.

```cpp
string grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamak herhangi bir ondalık noktasının solunda nasıl belirleneceğine yönelik yerel ayara özgü kural.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_grouping](#do_grouping).

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

## <a name="moneypunct"></a>  moneypunct::moneypunct

Türü nesnelerin Oluşturucusu `moneypunct`.

```cpp
explicit moneypunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs* nesne için bellek yönetimi türünü belirtmek için kullanılan bir tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: nesne ömrü onu içeren yerel ayarlar tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerler tanımlanmadı.

Yok edici korumalı olduğundan doğrudan örnek mümkündür.

Oluşturucu, temel nesnesiyle başlatır [locale::facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="neg_format"></a>  moneypunct::neg_format

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.

```cpp
pattern neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_neg_format](#do_neg_format).

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

## <a name="negative_sign"></a>  moneypunct::negative_sign

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type negative_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_negative_sign](#do_negative_sign).

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

## <a name="pos_format"></a>  moneypunct::pos_format

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.

```cpp
pattern pos_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_pos_format](#do_pos_format).

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

## <a name="positive_sign"></a>  moneypunct::positive_sign

Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type positive_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Pozitif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_positive_sign](#do_positive_sign).

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

## <a name="string_type"></a>  moneypunct::string_type

Türü karakterler içeren dizeyi tanımlayan tür **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_string](../standard-library/basic-string-class.md) noktalama dizileri kopyalarını, nesneleri depolayabilirsiniz.

## <a name="thousands_sep"></a>  moneypunct::thousands_sep

Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik kullanılacak öğelerin yerel ayara özgü bir dizisini ayırıcı

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_thousands_sep](#do_thousands_sep).

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

[\<yerel ayar >](../standard-library/locale.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
