---
title: numpunct Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocnum/std::numpunct
- xlocnum/std::numpunct::char_type
- xlocnum/std::numpunct::string_type
- xlocnum/std::numpunct::decimal_point
- xlocnum/std::numpunct::do_decimal_point
- xlocnum/std::numpunct::do_falsename
- xlocnum/std::numpunct::do_grouping
- xlocnum/std::numpunct::do_thousands_sep
- xlocnum/std::numpunct::do_truename
- xlocnum/std::numpunct::falsename
- xlocnum/std::numpunct::grouping
- xlocnum/std::numpunct::thousands_sep
- xlocnum/std::numpunct::truename
helpviewer_keywords:
- std::numpunct [C++]
- std::numpunct [C++], char_type
- std::numpunct [C++], string_type
- std::numpunct [C++], decimal_point
- std::numpunct [C++], do_decimal_point
- std::numpunct [C++], do_falsename
- std::numpunct [C++], do_grouping
- std::numpunct [C++], do_thousands_sep
- std::numpunct [C++], do_truename
- std::numpunct [C++], falsename
- std::numpunct [C++], grouping
- std::numpunct [C++], thousands_sep
- std::numpunct [C++], truename
ms.assetid: 73fb93cc-ac11-4c98-987c-bfa6267df596
ms.openlocfilehash: 602d8edef80f0e4d4abe4cb6773b774d174e1cbe
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87202824"
---
# <a name="numpunct-class"></a>numpunct Sınıfı

`CharType`Sayısal ve Boolean ifadelerin biçimlendirme ve noktalama bilgileri hakkında bilgi temsil etmek için kullanılan türdeki dizileri açıklayan bir nesneyi tanımlayan bir sınıf şablonu.

## <a name="syntax"></a>Söz dizimi

```cpp
template <class CharType>
class numpunct : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[numpunct](#numpunct)|Türündeki nesneler için Oluşturucu `numpunct` .|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[string_type](#string_type)|Türünde karakterler içeren bir dizeyi tanımlayan tür `CharType` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[decimal_point](#decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[do_decimal_point](#do_decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_falsename](#do_falsename)|Değerin metin temsili olarak kullanılacak bir dize döndürmek için çağrılan korumalı bir sanal üye işlevi **`false`** .|
|[do_grouping](#do_grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_thousands_sep](#do_thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_truename](#do_truename)|Değerin metin temsili olarak kullanılacak bir dize döndürmek için çağrılan korumalı bir sanal üye işlevi **`true`** .|
|[falsename](#falsename)|Değerin metin temsili olarak kullanılacak bir dize döndürür **`false`** .|
|[gruplama](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[thousands_sep](#thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[truename](#truename)|Değerin metin temsili olarak kullanılacak bir dize döndürür **`true`** .|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="numpunctchar_type"></a><a name="char_type"></a>sayısal tuş takımı:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType** şablon parametresi için bir eş anlamlı.

## <a name="numpunctdecimal_point"></a><a name="decimal_point"></a>tuş takımı unct::d ecimal_point

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_decimal_point](#do_decimal_point)döndürür.

### <a name="example"></a>Örnek

```cpp
// numpunct_decimal_point.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const numpunct <char> &npunct =
   use_facet <numpunct <char> >( loc);
   cout << loc.name( ) << " decimal point "<<
   npunct.decimal_point( ) << endl;
   cout << loc.name( ) << " thousands separator "
   << npunct.thousands_sep( ) << endl;
};
```

```Output
German_Germany.1252 decimal point ,
German_Germany.1252 thousands separator .
```

## <a name="numpunctdo_decimal_point"></a><a name="do_decimal_point"></a>tuş takımı unct::d o_decimal_point

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğe.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [decimal_point](#decimal_point)için örneğe bakın `decimal_point` .

## <a name="numpunctdo_falsename"></a><a name="do_falsename"></a>tuş takımı unct::d o_falsename

Korumalı sanal üye işlevi, değerin metin temsili olarak kullanılacak bir dizi döndürür **`false`** .

```cpp
virtual string_type do_falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

Değerin metin temsili olarak kullanılacak bir dizi içeren dize **`false`** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, tüm yerel ayarlarda değeri temsil etmek için "false" dizesini döndürür **`false`** .

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [falsename](#falsename)için örneğe bakın `falsename` .

## <a name="numpunctdo_grouping"></a><a name="do_grouping"></a>tuş takımı unct::d o_grouping

Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirlemek için yerel ayara özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür. Kodlama, **lconv:: Grouping**ile aynıdır.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [Gruplandırma](#grouping)örneğine bakın `grouping` .

## <a name="numpunctdo_thousands_sep"></a><a name="do_thousands_sep"></a>tuş takımı unct::d o_thousands_sep

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, `CharType` herhangi bir ondalık noktanın solunda bir grup ayırıcısı olarak kullanılacak türde yerel ayara özgü bir öğe döndürür.

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [thousands_sep](#thousands_sep)için örneğe bakın `thousands_sep` .

## <a name="numpunctdo_truename"></a><a name="do_truename"></a>tuş takımı unct::d o_truename

Değerin metin temsili olarak kullanılacak bir dize döndürmek için çağrılan korumalı bir sanal üye işlevi **`true`** .

```cpp
virtual string_type do_truename() const;
```

### <a name="remarks"></a>Açıklamalar

Değerin metin temsili olarak kullanılacak bir dize **`true`** .

Tüm yerel ayarlar, değeri temsil etmek için "true" dizesini döndürür **`true`** .

### <a name="example"></a>Örnek

Sanal üye işlevinin tarafından çağrıldığı [truename](#truename)örneğine bakın `truename` .

## <a name="numpunctfalsename"></a><a name="falsename"></a>tuş takımı unct:: falsename

Değerin metin temsili olarak kullanılacak bir dize döndürür **`false`** .

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CharType`Değerin metin temsili olarak kullanılacak bir dizisini içeren bir dize **`false`** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi, tüm yerel ayarlarda değeri temsil etmek için "false" dizesini döndürür **`false`** .

Üye işlevi [do_falsename](#do_falsename)döndürür.

### <a name="example"></a>Örnek

```cpp
// numpunct_falsename.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "English" );

   const numpunct <char> &npunct = use_facet <numpunct <char> >( loc );
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;

   locale loc2( "French" );
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >(loc2);
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;
}
```

```Output
English_United States.1252 truename true
English_United States.1252 falsename false
French_France.1252 truename true
French_France.1252 falsename false
```

## <a name="numpunctgrouping"></a><a name="grouping"></a>tuş takımı unct:: Grouping

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
// numpunct_grouping.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany");

   const numpunct <char> &npunct =
       use_facet < numpunct <char> >( loc );
   for (unsigned int i = 0; i < npunct.grouping( ).length( ); i++)
   {
      cout << loc.name( ) << " international grouping:\n the "
           << i <<"th group to the left of the radix character "
           << "is of size " << (int)(npunct.grouping ( )[i])
           << endl;
   }
}
```

```Output
German_Germany.1252 international grouping:
the 0th group to the left of the radix character is of size 3
```

## <a name="numpunctnumpunct"></a><a name="numpunct"></a>tuş takımı unct:: tuş takımı unct

Türündeki nesneler için Oluşturucu `numpunct` .

```cpp
explicit numpunct(size_t _Refs = 0);
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

Oluşturucu kendi temel nesnesini **locale::**[model](../standard-library/locale-class.md#facet_class)() ile başlatır `_Refs` .

## <a name="numpunctstring_type"></a><a name="string_type"></a>sayısal tuş takımı:: string_type

**CharType**türünde karakterler içeren bir dizeyi tanımlayan tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, nesne noktalama sıralarının kopyalarını depolayabilen [basic_string](../standard-library/basic-string-class.md) sınıf şablonu özelleştirmesi tanımlar.

## <a name="numpunctthousands_sep"></a><a name="thousands_sep"></a>sayısal tuş takımı:: thousands_sep

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_thousands_sep](#do_thousands_sep)döndürür.

### <a name="example"></a>Örnek

```cpp
// numpunct_thou_sep.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "german_germany" );

   const numpunct <char> &npunct =
   use_facet < numpunct < char > >( loc );
   cout << loc.name( ) << " decimal point "<<
   npunct.decimal_point( ) << endl;
   cout << loc.name( ) << " thousands separator "
   << npunct.thousands_sep( ) << endl;
};
```

```Output
German_Germany.1252 decimal point ,
German_Germany.1252 thousands separator .
```

## <a name="numpuncttruename"></a><a name="truename"></a>tuş takımı unct:: truename

Değerin metin temsili olarak kullanılacak bir dize döndürür **`true`** .

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

Değerin metin temsili olarak kullanılacak bir dize **`true`** .

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_truename](#do_truename)döndürür.

Tüm yerel ayarlar, değeri temsil etmek için "true" dizesini döndürür **`true`** .

### <a name="example"></a>Örnek

```cpp
// numpunct_truename.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;
int main( )
{
   locale loc( "English" );

   const numpunct < char> &npunct = use_facet <numpunct <char> >( loc );
   cout << loc.name( ) << " truename "<< npunct.truename( ) << endl;
   cout << loc.name( ) << " falsename "<< npunct.falsename( ) << endl;

   locale loc2("French");
   const numpunct <char> &npunct2 = use_facet <numpunct <char> >( loc2 );
   cout << loc2.name( ) << " truename "<< npunct2.truename( ) << endl;
   cout << loc2.name( ) << " falsename "<< npunct2.falsename( ) << endl;
}
```

```Output
English_United States.1252 truename true
English_United States.1252 falsename false
French_France.1252 truename true
French_France.1252 falsename false
```

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
