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
ms.openlocfilehash: 0bdd6556df892e5e231919dbc4ae95d14a6f95fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373623"
---
# <a name="numpunct-class"></a>numpunct Sınıfı

Sayısal ve Boolean ifadelerinbiçimlendirme ve noktalama işaretleri hakkındaki bilgileri `CharType` temsil etmek için kullanılan tür dizilerini açıklamak için yerel bir fakal olarak hizmet verebilen bir nesneyi açıklayan bir sınıf şablonu.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class numpunct : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk **girişim, kimlikte** benzersiz bir pozitif değer depolar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[nükpunct](#numpunct)|Tür `numpunct`nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[string_type](#string_type)|Tür `CharType`karakterleri içeren bir dize açıklayan bir tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[decimal_point](#decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[do_decimal_point](#do_decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_falsename](#do_falsename)|Bir dize yi **false**değerinin metin gösterimi olarak kullanmak üzere döndürmek için çağrılan korumalı sanal üye işlev.|
|[do_grouping](#do_grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_thousands_sep](#do_thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_truename](#do_truename)|**Doğru**değerin metin gösterimi olarak kullanmak için bir dize döndürmek için çağrılan korumalı sanal üye işlevi.|
|[falsename](#falsename)|**Yanlış**değerin metin gösterimi olarak kullanılacak bir dize döndürür.|
|[gruplandırma](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[thousands_sep](#thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[truename](#truename)|**Doğru**değerin metin gösterimi olarak kullanılacak bir dize döndürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="numpunctchar_type"></a><a name="char_type"></a>sayısal::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi **CharType** ile eş anlamlıdır.

## <a name="numpunctdecimal_point"></a><a name="decimal_point"></a>numpunct::decimal_point

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık nokta olarak kullanılacak yerelöğe özgü bir öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_decimal_point](#do_decimal_point)döndürür.

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

## <a name="numpunctdo_decimal_point"></a><a name="do_decimal_point"></a>numpunct::do_ondalık_nokta

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık nokta olarak kullanılacak yerelöğe özgü bir öğe.

### <a name="example"></a>Örnek

Sanal üye işlevinin çağrıldığı [decimal_point](#decimal_point)örneğine `decimal_point`bakın.

## <a name="numpunctdo_falsename"></a><a name="do_falsename"></a>numpunct::do_falsename

Korumalı sanal üye **işlevi, yanlış**değerin metin gösterimi olarak kullanılacak bir sıra döndürür.

```cpp
virtual string_type do_falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

**Yanlış**değerin metin gösterimi olarak kullanılacak bir dizi içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlev, tüm yerel bölgelerde **yanlış** değeri temsil etmek için "false" dizesini döndürür.

### <a name="example"></a>Örnek

Sanal üye [falsename](#falsename)işlevinin `falsename`.

## <a name="numpunctdo_grouping"></a><a name="do_grouping"></a>numpunct::do_grouping

Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamakların herhangi bir ondalık noktanın solunda nasıl gruplandırılmayı belirlemek için yerele özgü bir kural.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür. Kodlama lconv için **aynıdır::gruplandırma**.

### <a name="example"></a>Örnek

Sanal üye işlevin çağrıldığı [gruplandırma](#grouping)örneğine `grouping`bakın.

## <a name="numpunctdo_thousands_sep"></a><a name="do_thousands_sep"></a>numpunct::do_bins_sep

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi, herhangi bir `CharType` ondalık noktanın solunda grup ayırıcısı olarak kullanılacak yerele özgü bir tür öğesi döndürür.

### <a name="example"></a>Örnek

Sanal üye [thousands_sep](#thousands_sep)işlevinin `thousands_sep`çağrıldığı thousands_sep örneğine bakın.

## <a name="numpunctdo_truename"></a><a name="do_truename"></a>numpunct::do_truename

**Doğru**değerin metin gösterimi olarak kullanmak için bir dize döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string_type do_truename() const;
```

### <a name="remarks"></a>Açıklamalar

**Doğru**değerin metin gösterimi olarak kullanılacak bir dize.

Tüm yerel **değerler, değeri doğru**temsil etmek için "true" dizesini döndürer.

### <a name="example"></a>Örnek

[Truename](#truename)için örneğe bakın , sanal üye `truename`işlevi tarafından çağrılır.

## <a name="numpunctfalsename"></a><a name="falsename"></a>numpunct::falsename

**Yanlış**değerin metin gösterimi olarak kullanılacak bir dize döndürür.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

`CharType` **Yanlış**değerin metin gösterimi olarak kullanılacak bir s dizisi içeren bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlev, tüm yerel bölgelerde **yanlış** değeri temsil etmek için "false" dizesini döndürür.

Üye işlev [do_falsename](#do_falsename)döndürür.

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

## <a name="numpunctgrouping"></a><a name="grouping"></a>numpunct::gruplandırma

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

## <a name="numpunctnumpunct"></a><a name="numpunct"></a>sayısal::numpunct

Tür `numpunct`nesneleri için oluşturucu.

```cpp
explicit numpunct(size_t _Refs = 0);
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

Kurucu, temel nesnesini yerel olarak başlaşır:: **locale::**[fason](../standard-library/locale-class.md#facet_class)( ).`_Refs`

## <a name="numpunctstring_type"></a><a name="string_type"></a>sayısal::string_type

**CharType**türünde karakterler içeren bir dize açıklayan bir tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, nesneleri noktalama işaretlerinin kopyalarını depolayabilen sınıf şablonu [basic_string](../standard-library/basic-string-class.md) bir uzmanlık açıklar.

## <a name="numpunctthousands_sep"></a><a name="thousands_sep"></a>sayısal::thousands_sep

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlerce ayırıcı olarak kullanılacak yerele özgü bir öğe.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_thousands_sep](#do_thousands_sep)döndürür.

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

## <a name="numpuncttruename"></a><a name="truename"></a>numpunct::truename

**Doğru**değerin metin gösterimi olarak kullanılacak bir dize döndürür.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

**Doğru**değerin metin gösterimi olarak kullanılacak bir dize.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_truename](#do_truename)döndürür.

Tüm yerel **değerler, değeri doğru**temsil etmek için "true" dizesini döndürer.

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

[\<yerel>](../standard-library/locale.md)\
[fateks Sınıf](../standard-library/locale-class.md#facet_class)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
