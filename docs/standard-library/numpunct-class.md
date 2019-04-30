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
ms.openlocfilehash: 6084392c5cae151f6c7111fbe9fe7a45e103b74d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371483"
---
# <a name="numpunct-class"></a>numpunct Sınıfı

Türü dizileri tanımlamak için bir yerel ayar hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı `CharType` biçimlendirmesi ve noktalama işaretleri sayısal ve Boolean ifadelerin hakkında bilgi göstermek için kullanılır.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class numpunct : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[numpunct](#numpunct)|Türündeki nesneler için oluşturucu `numpunct`.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[string_type](#string_type)|Türü karakterler içeren dizeyi tanımlayan tür `CharType`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[decimal_point](#decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[do_decimal_point](#do_decimal_point)|Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_falsename](#do_falsename)|Korumalı değeri metin temsili olarak kullanılacak bir dizeyi döndürmek için çağrılan bir sanal üye işlevi **false**.|
|[do_grouping](#do_grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_thousands_sep](#do_thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.|
|[do_truename](#do_truename)|Korumalı değeri metin temsili olarak kullanılacak bir dizeyi döndürmek için çağrılan bir sanal üye işlevi **true**.|
|[falsename](#falsename)|Değerin metin temsili olarak kullanılacak bir dize döndürür **false**.|
|[Gruplandırma](#grouping)|Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür.|
|[thousands_sep](#thousands_sep)|Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.|
|[truename](#truename)|Değerin metin temsili olarak kullanılacak bir dize döndürür **true**.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  numpunct::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür **CharType.**

## <a name="decimal_point"></a>  numpunct::decimal_point

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

```cpp
CharType decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası olarak kullanılacak yerel ayara özgü öğesi.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_decimal_point](#do_decimal_point).

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

## <a name="do_decimal_point"></a>  numpunct::do_decimal_point

Ondalık noktası olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_decimal_point() const;
```

### <a name="return-value"></a>Dönüş Değeri

Ondalık noktası olarak kullanılacak yerel ayara özgü öğesi.

### <a name="example"></a>Örnek

Örneğin bakın [decimal_point](#decimal_point), sanal üye işlevi çağıran burada `decimal_point`.

## <a name="do_falsename"></a>  numpunct::do_falsename

Korumalı sanal üye işlevi değeri metin temsili olarak kullanılacak bir dizisini döndürür **false**.

```cpp
virtual string_type do_falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

Değerin metin temsili olarak kullanılacak bir dizisini içeren bir dize **false**.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ' % s'dize değeri temsil etmek için "false" döndürür **false** tüm bölgelerde.

### <a name="example"></a>Örnek

Örneğin bakın [falsename](#falsename), sanal üye işlevi çağıran burada `falsename`.

## <a name="do_grouping"></a>  numpunct::do_grouping

Herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual string do_grouping() const;
```

### <a name="return-value"></a>Dönüş Değeri

Basamak herhangi bir ondalık noktasının solunda nasıl belirleneceğine yönelik yerel ayara özgü kural.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi herhangi bir ondalık noktasının solunda gruplanacak basamakların nasıl belirleneceğine yönelik yerel ayara özgü bir kural döndürür. Kodlama aynı olan **lconv::grouping**.

### <a name="example"></a>Örnek

Örneğin bakın [gruplandırma](#grouping), sanal üye işlevi çağıran burada `grouping`.

## <a name="do_thousands_sep"></a>  numpunct::do_thousands_sep

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürmek için çağrılan korumalı sanal üye işlevi.

```cpp
virtual CharType do_thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı sanal üye işlevi türü yerel ayara özgü bir öğeyi döndürür `CharType` herhangi bir ondalık noktasının solunda bir Grup ayırıcı olarak kullanılacak.

### <a name="example"></a>Örnek

Örneğin bakın [thousands_sep](#thousands_sep), sanal üye işlevi çağıran burada `thousands_sep`.

## <a name="do_truename"></a>  numpunct::do_truename

Korumalı değeri metin temsili olarak kullanılacak bir dizeyi döndürmek için çağrılan bir sanal üye işlevi **true**.

```cpp
virtual string_type do_truename() const;
```

### <a name="remarks"></a>Açıklamalar

Değerin metin temsili olarak kullanılacak bir dize **true**.

Tüm yerel bir dize değeri temsil etmek için "true" dönüş **true**.

### <a name="example"></a>Örnek

Örneğin bakın [truename](#truename), sanal üye işlevi çağıran burada `truename`.

## <a name="falsename"></a>  numpunct::falsename

Değerin metin temsili olarak kullanılacak bir dize döndürür **false**.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

Bir dizi içeren bir dize `CharType`değeri metin temsili olarak kullanılacak s **false**.

### <a name="remarks"></a>Açıklamalar

Üye işlevi ' % s'dize değeri temsil etmek için "false" döndürür **false** tüm bölgelerde.

Üye işlevinin döndürdüğü [do_falsename](#do_falsename).

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

## <a name="grouping"></a>  numpunct::Grouping

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

## <a name="numpunct"></a>  numpunct::numpunct

Türündeki nesneler için oluşturucu `numpunct`.

```cpp
explicit numpunct(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs*<br/>
Bellek yönetimi için nesne türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için *_Refs* parametresi ve bunların önemi:

- 0: Nesnenin ömrünü, onu içeren yerel ayarlar tarafından yönetilir.

- 1: Nesnenin ömrünü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlı değil.

Yok edici korumalı olduğundan doğrudan örnek mümkündür.

Oluşturucu, temel nesnesiyle başlatır **yerel::**[modeli](../standard-library/locale-class.md#facet_class)(`_Refs`).

## <a name="string_type"></a>  numpunct::string_type

Türü karakterler içeren dizeyi tanımlayan tür **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Türü tanımlayan Şablon sınıfı bir alt uzmanlaşması [basic_string](../standard-library/basic-string-class.md) noktalama dizileri kopyalarını, nesneleri depolayabilirsiniz.

## <a name="thousands_sep"></a>  numpunct::thousands_sep

Binlik ayırıcı olarak kullanılacak yerel ayara özgü bir öğeyi döndürür.

```cpp
CharType thousands_sep() const;
```

### <a name="return-value"></a>Dönüş Değeri

Binlik kullanılacak yerel ayara özgü bir öğeyi ayırıcı.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_thousands_sep](#do_thousands_sep).

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

## <a name="truename"></a>  numpunct::truename

Değerin metin temsili olarak kullanılacak bir dize döndürür **true**.

```cpp
string_type falsename() const;
```

### <a name="return-value"></a>Dönüş Değeri

Değerin metin temsili olarak kullanılacak bir dize **true**.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_truename](#do_truename).

Tüm yerel bir dize değeri temsil etmek için "true" dönüş **true**.

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

[\<yerel ayar >](../standard-library/locale.md)<br/>
[facet sınıfı](../standard-library/locale-class.md#facet_class)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
