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
ms.openlocfilehash: 28acc1eb2f2ed265d20507d2b47efa657c2d1bb9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
---
# <a name="moneypunct-class"></a>moneypunct Sınıfı

Şablon sınıfı türü dizilerini açıklamak için yerel ayar model hizmet verebilir bir nesneyi tanımlayan `CharType` para giriş alanı veya parasal çıkış alanı göstermek için kullanılır. Varsa şablon parametresi `Intl` olan `true`, uluslararası kuralları gözlenen.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, bool Intl>
class moneypunct;
```

### <a name="parameters"></a>Parametreler

`CharType` Bir program içinden karakterlerin kodlanması için kullanılan türü.

`Intl` Uluslararası kuralları gözlenecek olup olmadığını belirten bir bayrak.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**

Const statik nesne uluslararası şablon parametresi değerini depolar **uluslararası**.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[moneypunct](#moneypunct)|Nesne türü Oluşturucusu `moneypunct`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[STRING_TYPE](#string_type)|Tür karakterleri içeren bir dize açıklayan türü `CharType`.|

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

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

## <a name="curr_symbol"></a>  moneypunct::curr_symbol

Para birimi simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
string_type curr_symbol() const;
```

### <a name="return-value"></a>Dönüş Değeri

Para birimi simgesini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_curr_symbol](#do_curr_symbol).

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

Öğe bir ondalık ayırıcısı simgesi olarak kullanılacak yerel ayarlara özgü dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_decimal_point](#do_decimal_point).

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

Öğe bir ondalık ayırıcısı simgesi olarak kullanılacak yerel ayarlara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bkz [curr_symbol](#curr_symbol), sanal üye fonksiyonu tarafından çağrılır burada `curr_symbol`.

## <a name="do_decimal_point"></a>  moneypunct::do_decimal_point

Ondalık simgesi olarak kullanılacak öğeleri yerel ayarlara özgü bir dizi döndüren bir korumalı sanal üye işlev.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bir ondalık ayırıcısı simgesi olarak kullanılacak yerel ayarlara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bkz [decimal_point](#decimal_point), sanal üye fonksiyonu tarafından çağrılır burada `decimal_point`.

## <a name="do_frac_digits"></a>  moneypunct::do_frac_digits

Herhangi bir ondalık ayırıcısı sağındaki görüntülenecek basamak sayısı yerel ayarlara özgü sayımını döndürür korumalı sanal üye işlevi.

```cpp
virtual int do_frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık ayırıcısı sağındaki görüntülenecek basamak sayısı yerel ayarlara özgü sayısı.

### <a name="example"></a>Örnek

Örneğin bkz [frac_digits](#frac_digits), sanal üye fonksiyonu tarafından çağrılır burada `frac_digits`.

## <a name="do_grouping"></a>  moneypunct::do_grouping

Sayı Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirlemek için bir yerel ayarlara özgü kural döndüren bir korumalı sanal üye işlev.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Sayı Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirlemek için bir yerel ayarlara özgü kuralı.

### <a name="example"></a>Örnek

Örneğin bkz [gruplandırma](#grouping), sanal üye fonksiyonu tarafından çağrılır burada **gruplandırma**.

## <a name="do_neg_format"></a>  moneypunct::do_neg_format

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye fonksiyonu için negatif bir tutar parasal çıktı alanı oluşturmak nasıl belirlemek için bir yerel ayarlara özgü kural döndürür. Her dört öğelerinin **pattern::field** değerlere sahip olabilir:

- **Hiçbiri** sıfır veya daha fazla boşluk veya hiçbir şey oluşturmak üzere.

- **oturum** eşleşen veya olumlu veya olumsuz bir oturum oluşturur.

- **alan** sıfır veya daha fazla boşluk veya bir alan oluşturmak üzere.

- **Sembol** veya bir para birimi simgesini oluşturmak üzere.

- **değer** veya parasal bir değer üretmek üzere.

Para çıktı alanı bileşenlerinin oluşturulur ve para giriş alanını bileşenlerinin bu öğelerin görüntüleneceği içinde sırayla eşleştirilir **pattern::field**. Değerlerin her birini **oturum**, **simgesi**, **değeri**ve her iki **hiçbiri** veya **alanı** tam olarak görünmelidir bir kez. Değer **hiçbiri** ilk görünmemesi gerekir. Değer alanı **gerekir** ilk veya son gösterilmiyor. Varsa **uluslararası** sırada doğrudur **simgesi**, **oturum**, **hiçbiri**, ardından **değeri**.

Şablon sürümü `moneypunct` \< **CharType**, **uluslararası**> döndürür `{` **money_base::symbol**, **money_ Base::Sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Örnek

Örneğin bkz [neg_format](#neg_format), sanal üye fonksiyonu tarafından çağrılır burada `neg_format`.

## <a name="do_negative_sign"></a>  moneypunct::do_negative_sign

Negatif işareti simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string_type do_negative_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Eksi işareti kullanılacak öğe yerel ayarlara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bkz [negative_sign](#negative_sign), sanal üye fonksiyonu tarafından çağrılır burada `negative_sign`.

## <a name="do_pos_format"></a>  moneypunct::do_pos_format

Pozitif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual pattern do_pos_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Korumalı sanal üye fonksiyonu için pozitif bir tutar parasal çıktı alanı oluşturmak nasıl belirlemek için bir yerel ayarlara özgü kural döndürür. (Ayrıca para giriş alanını bileşenlerinin eşleşecek şekilde nasıl belirler.) Aynı kodlamadır [do_neg_format](#do_neg_format).

Moneypunct şablon sürümü\< **CharType**, **Inputlterator**> döndürür `{` **money_base::symbol**, **para _base::Sign**, **money_base::value**, **money_base::none**`}`.

### <a name="example"></a>Örnek

Örneğin bkz [pos_format](#pos_format), sanal üye fonksiyonu tarafından çağrılır burada `pos_format`.

## <a name="do_positive_sign"></a>  moneypunct::do_positive_sign

Artı işareti kullanmak için öğeleri yerel ayarlara özgü bir dizi döndüren bir korumalı sanal üye işlev.

```cpp
virtual string_type do_positive_sign() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğe bir artı işareti kullanılacak yerel ayarlara özgü dizisi.

### <a name="example"></a>Örnek

Örneğin bkz [positive_sign](#positive_sign), sanal üye fonksiyonu tarafından çağrılır burada `positive_sign`.

## <a name="do_thousands_sep"></a>  moneypunct::do_thousands_sep

Ondalık ayırıcının solundaki Grup ayırıcı olarak kullanmak için bir yerel ayarlara özgü öğesi döndürür korumalı sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık ayırıcının solundaki Grup ayırıcı olarak kullanmak için bir yerel ayarlara özgü öğesi.

### <a name="example"></a>Örnek

Örneğin bkz [thousands_sep](#thousands_sep), sanal üye fonksiyonu tarafından çağrılır burada `thousands_sep`.

## <a name="frac_digits"></a>  moneypunct::frac_digits

Herhangi bir ondalık noktasının sağında görüntülenecek basamak sayısının yerel ayara özgü bir sayısını döndürür.

```cpp
int frac_digits() const;
```

### <a name="return-value"></a>Dönüş Değeri

Herhangi bir ondalık ayırıcısı sağındaki görüntülenecek basamak sayısı yerel ayarlara özgü sayısı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_frac_digits](#do_frac_digits).

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

Sayı Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirlemek için bir yerel ayarlara özgü kuralı.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_grouping](#do_grouping).

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

Nesne türü Oluşturucusu `moneypunct`.

```cpp
explicit moneypunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

`_Refs` Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için `_Refs` parametre ve bunların anlamlı:

- 0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlanmamış.

Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.

Oluşturucu temel nesnesiyle başlatır [locale::facet](../standard-library/locale-class.md#facet_class)(_ *Refs*).

## <a name="neg_format"></a>  moneypunct::neg_format

Negatif tutarlara sahip çıkışları biçimlendirmek için bir yerel ayara özgü kural döndürür.

```cpp
pattern neg_format() const;
```

### <a name="return-value"></a>Dönüş Değeri

Biçimlendirme için yerel ayar özgü bir kural ile negatif tutarlar çıkarır.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_neg_format](#do_neg_format).

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

Üye işlevi döndürür [do_negative_sign](#do_negative_sign).

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

Biçimlendirme için yerel ayar özgü bir kural ile pozitif tutarlar çıkarır.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_pos_format](#do_pos_format).

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

Öğe bir artı işareti sembolü olarak kullanılacak yerel ayarlara özgü dizisi.

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_positive_sign](#do_positive_sign).

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

Tür karakterleri içeren bir dize açıklayan türü **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı uzmanlaşması türünü açıklayan [basic_string](../standard-library/basic-string-class.md) olan nesneleri noktalama sıraları kopyalarını depolayabilirsiniz.

## <a name="thousands_sep"></a>  moneypunct::thousands_sep

Binlik ayırıcı simgesi olarak kullanılacak öğelerin yerel ayara özgü bir dizisini döndürür.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Öğeleri olarak kullanılacak yerel ayarlara özgü bir dizi ayırıcı

### <a name="remarks"></a>Açıklamalar

Üye işlevi döndürür [do_thousands_sep](#do_thousands_sep).

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
