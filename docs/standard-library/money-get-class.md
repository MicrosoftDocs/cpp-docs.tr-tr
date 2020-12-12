---
description: 'Hakkında daha fazla bilgi edinin: money_get sınıfı'
title: money_get Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocmon/std::money_get
- xlocmon/std::money_get::char_type
- xlocmon/std::money_get::iter_type
- xlocmon/std::money_get::string_type
- xlocmon/std::money_get::do_get
- xlocmon/std::money_get::get
helpviewer_keywords:
- std::money_get [C++]
- std::money_get [C++], char_type
- std::money_get [C++], iter_type
- std::money_get [C++], string_type
- std::money_get [C++], do_get
- std::money_get [C++], get
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
ms.openlocfilehash: 6dfab2347799c78b89e2da9e00ebdb71af0c22d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277511"
---
# <a name="money_get-class"></a>money_get Sınıfı

Sınıf şablonu, tür dizilerinin parasal değerlere dönüştürmelerini denetlemek için bir yerel ayar modeli olarak işlev görebilecek bir nesne tanımlar `CharType` .

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*InputIterator*\
Alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_get](#money_get)|`money_get`Parasal değerleri temsil eden dizilerden sayısal değerler ayıklamak için kullanılan türündeki nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|
|[string_type](#string_type)|Türünde karakterler içeren bir dizeyi tanımlayan tür `CharType` .|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_get](#do_get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklamak için çağrılan sanal işlev.|
|[get](#get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="money_getchar_type"></a><a name="char_type"></a> money_get:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, *CharType* şablon parametresi için bir eş anlamlı.

## <a name="money_getdo_get"></a><a name="do_get"></a> money_get::d o_get

Bir parasal değeri temsil eden bir karakter dizisinden sayısal bir değeri ayıklamak için çağrılan sanal işlev.

```cpp
virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const virtual iter_type do_get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*Uluslararası*\
Dizide beklenen para birimi sembolünün türünü belirten bir Boole değeri: **`true`** Yurtiçi ise uluslararası **`false`** .

*İosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*Durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*Acil*\
Dönüştürülmüş sırayı depolayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi, `first` `last` bir tamamlanmış ve boş olmayan parasal giriş alanı kabul edene kadar, [,) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı bir veya daha fazla ondalık basamak dizisine, isteğe bağlı olarak bir eksi işaretiyle ( `-` ), miktarı göstermek ve sonucu [string_type](#string_type) nesne *Val*' de depolar. Birinci öğeyi parasal giriş alanının ötesine atayarak bir yineleyici döndürür. Aksi takdirde, işlev *değer* 'de boş bir sıra depolar ve `ios_base::failbit` *durum* olarak ayarlar. Geçerli bir parasal giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri eşitse `last` , işlevi ' de ayarlanır `ios_base::eofbit` `State` .

İkinci sanal korumalı üye işlevi ilki ile aynı şekilde davranır, ancak başarılı olursa, isteğe bağlı olarak işaretli basamak sırasını bir değere dönüştürür **`long double`** ve bu değeri *Val*' de depolar.

Parasal giriş alanının biçimi, [use_facet](../standard-library/locale-functions.md#use_facet) [](../standard-library/locale-class.md#facet_class)  <  [moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **intl**>> ( **iosbase**) etkin çağrı tarafından döndürülen yerel ayar modeli fac tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)).

Özellikle:

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) alanın bileşenlerinin oluşma sırasını belirler.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) , bir para birimi sembolünü oluşturan öğelerin sırasını belirler.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) , pozitif bir işaret oluşturan öğelerin sırasını belirler.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) , eksi işareti oluşturan öğelerin sırasını belirler.

- **fac**. [Gruplandırma](../standard-library/moneypunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) , herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran öğeyi belirler.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) , kesir basamaklarından tamsayı basamaklarını ayıran öğeyi belirler.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) , herhangi bir ondalık noktanın sağında bulunan önemli kesir basamaklarının sayısını belirler. Tarafından için çağrılmasından daha fazla kesir basamağıyla bir parasal miktarı ayrıştırırken `frac_digits` , `do_get` en çok karakter tükettikten sonra ayrıştırma durduruluyor `frac_digits` .

İmza dizesi varsa ( **fac**. `negative_sign` or **fac**. `positive_sign`) birden fazla öğe içeriyor, yalnızca ilk öğe eşleşen öğe **money_base:: işareti** , biçim düzeninde görünür ( **fac**. `neg_format`). Kalan öğeler, parasal giriş alanının sonunda eşleştirilir. Hiçbir dize parasal giriş alanındaki Next öğesiyle eşleşen bir ilk öğesi yoksa, imza dizesi boş olarak alınır ve işaret pozitif olur.

Eğer **iosbase** ise. [bayraklar](../standard-library/ios-base-class.md#flags)  &  [showbase](../standard-library/ios-functions.md#showbase) sıfırdan farklı, **fac** dizesidir. `curr_symbol` biçim düzeninde **money_base:: symbol** öğesine eşit olan öğe ile eşleşmesi gerekir. Aksi halde, biçim deseninin sonunda **money_base:: symbol** oluşursa ve imza dizesinin hiçbir öğesi eşleştirilmeye devam ediyorsa, para birimi simgesi eşleştirmez. Aksi takdirde, para birimi simgesi isteğe bağlı olarak eşleştirilir.

Eğer **fac** örneği yoksa. `thousands_sep` parasal giriş alanının değer bölümünde ( **money_base:: değer** şuna eşit olan öğe biçim düzeninde göründüğünde), gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, **fac** tarafından uygulanan gruplandırma kısıtlamaları. **Gruplandırma** zorlanır. Elde edilen basamak sırasının, düşük sıralı **fac** bir tamsayıyı temsil ettiğini unutmayın. `frac_digits` ondalık basamak sayısı, ondalık noktanın sağında değerlendirilir.

Rastgele boşluk, öğe biçim deseninin sonundaki gibi **money_base:: boşluk** , biçim düzeninde göründüğü zaman eşleştirilir. Aksi takdirde, dahili bir boşluk eşleştirildiği.  [Use_facet](../standard-library/locale-functions.md#use_facet)  <  [CType](../standard-library/ctype-class.md) \< **CharType**> > ( **ıosbase** gibi bir öğe ch boşluk olarak değerlendirilir. [getloc](../standard-library/ios-base-class.md#getloc)). [(](../standard-library/ctype-class.md#is) **ctype_base:: Space**, *ch*) **`true`** .

### <a name="example"></a>Örnek

Çağıran [Get](#get)için örneğe bakın `do_get` .

## <a name="money_getget"></a><a name="get"></a> money_get:: Get

Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.

```cpp
iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    long double& val) const;

iter_type get(iter_type first,
    iter_type last,
    bool Intl,
    ios_base& Iosbase,
    ios_base::iostate& State,
    string_type& val) const;
```

### <a name="parameters"></a>Parametreler

*adı*\
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*soyadına*\
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*Uluslararası*\
Dizide beklenen para birimi sembolünün türünü belirten bir Boole değeri: **`true`** Yurtiçi ise uluslararası **`false`** .

*İosbase*\
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir

*Durumunda*\
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*Acil*\
Dönüştürülmüş sırayı depolayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlevi de [do_get](#do_get)döndürür `(first, last, Intl, Iosbase, State, val)` .

### <a name="example"></a>Örnek

```cpp
// money_get_get.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <sstream>
using namespace std;

int main( )
{
   locale loc( "german_germany" );

   basic_stringstream< char > psz;
   psz << use_facet<moneypunct<char, 1> >(loc).curr_symbol() << "-1.000,56";
   basic_stringstream< char > psz2;
   psz2 << "-100056" << use_facet<moneypunct<char, 1> >(loc).curr_symbol();

   ios_base::iostate st = 0;
   long double fVal;

   psz.flags( psz.flags( )|ios_base::showbase );
   // Which forced the READING the currency symbol
   psz.imbue(loc);
   use_facet < money_get < char > >( loc ).
      get( basic_istream<char>::_Iter( psz.rdbuf( ) ),
           basic_istream<char>::_Iter( 0 ), true, psz, st, fVal );

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz.str( ) << ", intl = 1) FAILED"
           << endl;
   else
      cout << "money_get(" << psz.str( ) << ", intl = 1) = "
           << fVal/100.0 << endl;

   use_facet < money_get < char > >( loc ).
      get(basic_istream<char>::_Iter(psz2.rdbuf( )),
          basic_istream<char>::_Iter(0), false, psz2, st, fVal);

   if ( st & ios_base::failbit )
      cout << "money_get(" << psz2.str( ) << ", intl = 0) FAILED"
           << endl;
   else
      cout << "money_get(" << psz2.str( ) << ", intl = 0) = "
           << fVal/100.0 << endl;
};
```

## <a name="money_getiter_type"></a><a name="iter_type"></a> money_get:: iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **InputIterator** şablon parametresi için bir eş anlamlı.

## <a name="money_getmoney_get"></a><a name="money_get"></a> money_get:: money_get

`money_get`Parasal değerleri temsil eden dizilerden sayısal değerler ayıklamak için kullanılan türündeki nesneler için Oluşturucu.

```cpp
explicit money_get(size_t _Refs = 0);
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

Oluşturucu kendi temel nesnesini **locale::**[model](../standard-library/locale-class.md#facet_class)(*_Refs*) ile başlatır.

## <a name="money_getstring_type"></a><a name="string_type"></a> money_get:: string_type

**CharType** türünde karakterler içeren bir dizeyi tanımlayan tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, [basic_string](../standard-library/basic-string-class.md)sınıf şablonu özelleştirmesi tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[model sınıfı](../standard-library/locale-class.md#facet_class)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
