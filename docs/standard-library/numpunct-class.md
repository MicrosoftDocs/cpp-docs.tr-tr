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
ms.openlocfilehash: 07285f5c014db1ddf419c372913cac0364538a55
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/16/2020
ms.locfileid: "79419723"
---
# <a name="numpunct-class"></a>numpunct Sınıfı

Sayısal ve Boolean ifadelerin biçimlendirme ve noktalama bilgileri hakkında bilgi temsil etmek için kullanılan `CharType` türlerini açıklayan bir nesneyi tanımlayan bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

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
|[numpunct](#numpunct)|`numpunct`türündeki nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[string_type](#string_type)|`CharType`türünde karakterler içeren bir dizeyi tanımlayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[decimal_point](#decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[do_decimal_point](#do_decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_falsename](#do_falsename)|**False**değerinin metin temsili olarak kullanılacak bir dize döndürmek için çağrılan korumalı bir sanal üye işlevi.|
|[do_grouping](#do_grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_thousands_sep](#do_thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_truename](#do_truename)|**True**değerinin metin temsili olarak kullanılacak bir dize döndürmek için çağrılan korumalı bir sanal üye işlevi.|
|[falsename](#falsename)|**False**değerinin metin temsili olarak kullanılacak bir dize döndürür.|
|[gruplama](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[thousands_sep](#thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[truename](#truename)|**True**değerinin metin temsili olarak kullanılacak bir dize döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="char_type"></a>sayısal tuş takımı:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **CharType** şablon parametresi için bir eş anlamlı.

## <a name="decimal_point"></a>tuş takımı unct::d ecimal_point

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

## <a name="do_decimal_point"></a>tuş takımı unct::d o_decimal_point

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğe.

### <a name="example"></a>Örnek

Sanal üye işlevinin `decimal_point`tarafından çağrıldığı [decimal_point](#decimal_point)için örneğe bakın.

## <a name="do_falsename"></a>tuş takımı unct::d o_falsename

Korumalı sanal üye işlevi, **false**değerinin metin temsili olarak kullanılacak bir dizi döndürür.

```cpp
virtual string_type do_falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

**False**değerinin metin temsili olarak kullanılacak bir dizi içeren dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, tüm yerel ayarlarda **false** değerini göstermek için "false" dizesini döndürür.

### <a name="example"></a>Örnek

Sanal üye işlevinin `falsename`tarafından çağrıldığı [falsename](#falsename)için örneğe bakın.

## <a name="do_grouping"></a>tuş takımı unct::d o_grouping

Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirlemek için yerel ayara özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür. Kodlama, **lconv:: Grouping**ile aynıdır.

### <a name="example"></a>Örnek

Sanal üye işlevinin `grouping`tarafından çağrıldığı [Gruplandırma](#grouping)için örneğe bakın.

## <a name="do_thousands_sep"></a>tuş takımı unct::d o_thousands_sep

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi herhangi bir ondalık noktanın solunda bir grup ayırıcısı olarak kullanılmak üzere `CharType` türünde bir yerel ayara özgü öğe döndürür.

### <a name="example"></a>Örnek

Sanal üye işlevinin `thousands_sep`tarafından çağrıldığı [thousands_sep](#thousands_sep)için örneğe bakın.

## <a name="do_truename"></a>tuş takımı unct::d o_truename

**True**değerinin metin temsili olarak kullanılacak bir dize döndürmek için çağrılan korumalı bir sanal üye işlevi.

```cpp
virtual string_type do_truename() const;
```

### <a name="remarks"></a>Açıklamalar

**True**değerinin metin temsili olarak kullanılacak bir dize.

Tüm yerel ayarlar, **doğru**değeri göstermek için "true" dizesini döndürür.

### <a name="example"></a>Örnek

Sanal üye işlevinin `truename`tarafından çağrıldığı [truename](#truename)örneğine bakın.

## <a name="falsename"></a>tuş takımı unct:: falsename

**False**değerinin metin temsili olarak kullanılacak bir dize döndürür.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

**False**değerinin metin temsili olarak kullanılacak `CharType`s dizisini içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevi, tüm yerel ayarlarda **false** değerini göstermek için "false" dizesini döndürür.

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

## <a name="grouping"></a>tuş takımı unct:: Grouping

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

## <a name="numpunct"></a>tuş takımı unct:: tuş takımı unct

`numpunct`türündeki nesneler için Oluşturucu.

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

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)(`_Refs`) ile başlatır.

## <a name="string_type"></a>sayısal tuş takımı:: string_type

**CharType**türünde karakterler içeren bir dizeyi tanımlayan tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü, nesne noktalama sıralarının kopyalarını depolayabilen [basic_string](../standard-library/basic-string-class.md) sınıf şablonu özelleştirmesi tanımlar.

## <a name="thousands_sep"></a>sayısal tuş takımı:: thousands_sep

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

## <a name="truename"></a>tuş takımı unct:: truename

**True**değerinin metin temsili olarak kullanılacak bir dize döndürür.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

**True**değerinin metin temsili olarak kullanılacak bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_truename](#do_truename)döndürür.

Tüm yerel ayarlar, **doğru**değeri göstermek için "true" dizesini döndürür.

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

[\<yerel ayar >](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
