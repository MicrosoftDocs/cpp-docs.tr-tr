---
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
ms.openlocfilehash: d882edd5ce55b15d03512ca9a55a49bc3424ee7a
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/21/2019
ms.locfileid: "72687675"
---
# <a name="money_get-class"></a>money_get Sınıfı

Sınıf şablonu, parasal değerlere `CharType` türündeki dizilerin dönüştürmelerini denetlemek için bir yerel ayar modeli olarak işlev görebilecek bir nesne tanımlar.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

*CharType* \
Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.

*InputIterator* \
Alma işlevlerinin kendi girişlerini okuyacağı yineleyicinin türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, kimlik içinde benzersiz bir pozitif değer depolar **.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_get](#money_get)|Parasal değerleri temsil eden dizilerden sayısal değerler ayıklamak için kullanılan `money_get` türündeki nesneler için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|
|[string_type](#string_type)|@No__t_0 türünde karakterler içeren bir dizeyi tanımlayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_get](#do_get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklamak için çağrılan sanal işlev.|
|[get](#get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<locale >

**Ad alanı:** std

## <a name="char_type"></a>money_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, *CharType*şablon parametresi için bir eş anlamlı.

## <a name="do_get"></a>money_get::d o_get

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

*ilk* \
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*son* \
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*Intl* \
Dizide beklenen para birimi sembolünün türünü belirten bir Boole **değeri: Uluslararası, yurtiçi ise** **false** .

*Iosbase* \
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir.

*Durum* \
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*val* \
Dönüştürülmüş sırayı depolayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye işlevi, bir tamamen, boş olmayan parasal giriş alanı tanınana kadar [`first`, `last`) dizisindeki ilk başlayarak sıralı öğeleri eşleştirmeyi dener. Başarılı olursa, bu alanı bir veya daha fazla ondalık basamak dizisine, isteğe bağlı olarak bir eksi işareti (`-`), miktarı göstermek ve sonucu [string_type](#string_type) nesne *Val*içinde depolar. Birinci öğeyi parasal giriş alanının ötesine atayarak bir yineleyici döndürür. Aksi takdirde, işlev *değer* 'de boş bir sıra depolar ve `ios_base::failbit` *durumu*olarak ayarlar. Geçerli bir parasal giriş alanının herhangi bir ön ekinin ötesinde ilk öğeyi tanımlayarak bir yineleyici döndürür. Her iki durumda da, dönüş değeri `last` eşitse, işlev `State` `ios_base::eofbit` belirler.

İkinci sanal korumalı üye işlevi ilki ile aynı şekilde davranır, ancak başarılı olursa, isteğe bağlı olarak imzalanan basamak sırasını **Long Double** türünde bir değere dönüştürdüğünde ve bu değeri *Val*içinde depolar.

Parasal giriş alanının biçimi, geçerli çağrı [use_facet](../standard-library/locale-functions.md#use_facet)  < [moneypunct](../standard-library/moneypunct-class.md) \< **chartype**, **Intl**> > ( **iosbase**)**tarafından döndürülen** [yerel ayar modeli](../standard-library/locale-class.md#facet_class)tarafından belirlenir. [getloc](../standard-library/ios-base-class.md#getloc)).

Engelle

- **fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) , alanın bileşenlerinin ne sırada olacağını belirler.

- **fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) bir para birimi sembolünü oluşturan öğelerin sırasını belirler.

- **fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) pozitif bir işaret oluşturan öğelerin sırasını belirler.

- **fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) eksi işareti oluşturan öğelerin sırasını belirler.

- **fac**. [Gruplandırma](../standard-library/moneypunct-class.md#grouping) , basamakların herhangi bir ondalık noktanın solunda nasıl gruplandığını belirler.

- **fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) herhangi bir ondalık noktanın solundaki basamak gruplarını ayıran öğeyi belirler.

- **fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) kesir basamaklarından tamsayı basamaklarını ayıran öğeyi belirler.

- **fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) , herhangi bir ondalık noktanın sağında bulunan önemli kesir basamak sayısını belirler. @No__t_0 tarafından çağrılmasından daha fazla kesir basamağıyla bir parasal miktarı ayrıştırırken, `do_get` en fazla `frac_digits` karakter kullandıktan sonra ayrıştırmayı durduruyor.

İmza dizesi varsa ( **fac**. `negative_sign` veya **fac**. `positive_sign`) birden fazla öğe içeriyor, yalnızca ilk öğe eşleştirildiği için **money_base:: Sign** öğesine eşit olan öğe biçim düzeninde görünür ( **fac**. `neg_format`). Kalan öğeler, parasal giriş alanının sonunda eşleştirilir. Hiçbir dize parasal giriş alanındaki Next öğesiyle eşleşen bir ilk öğesi yoksa, imza dizesi boş olarak alınır ve işaret pozitif olur.

Eğer **iosbase**ise. [showbase](../standard-library/ios-functions.md#showbase)  &  [bayrakları](../standard-library/ios-base-class.md#flags) sıfır değil, dize **fac**. `curr_symbol` eşleşmesi gerekir, çünkü biçim düzeninde **money_base:: symbol** öğesine eşittir. Aksi halde, biçim deseninin sonunda **money_base:: symbol** oluşursa ve imza dizesinin hiçbir öğesi eşleştirilmeye devam ediyorsa, para birimi simgesi eşleştirmez. Aksi takdirde, para birimi simgesi isteğe bağlı olarak eşleştirilir.

Eğer **fac**örneği yoksa. `thousands_sep`, parasal giriş alanının değer bölümünde ( **money_base:: value** öğesine eşit olan öğe biçim düzeninde göründüğünde) oluşur, hiçbir gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, **fac**tarafından uygulanan gruplandırma kısıtlamaları. **Gruplandırma** zorlanır. Elde edilen basamak sırasının, düşük sıralı **fac**bir tamsayıyı temsil ettiğini unutmayın. `frac_digits` ondalık basamak, ondalık noktanın sağında değerlendirilir.

Öğe, biçim deseninin sonundaki gibi görünüyorsa, biçim düzeninde **money_base:: Space** 'e eşit olan bir rastgele boşluk eşleşir. Aksi takdirde, dahili bir boşluk eşleştirildiği. [Use_facet](../standard-library/locale-functions.md#use_facet)  < [CType](../standard-library/ctype-class.md) \< **CharType**> > ( **ıosbase**) varsa, bir öğe *ch* boşluk olarak değerlendirilir. [getloc](../standard-library/ios-base-class.md#getloc)). [(](../standard-library/ctype-class.md#is) **ctype_base:: Space**, *ch*) ise **geçerlidir**.

### <a name="example"></a>Örnek

@No__t_1 çağıran [Get](#get)için örneğe bakın.

## <a name="get"></a>money_get:: Get

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

*ilk* \
Dönüştürülecek sıranın başlangıcını ele alarak giriş Yineleyici.

*son* \
Dönüştürülecek dizinin sonunu ele alarak giriş Yineleyici.

*Intl* \
Dizide beklenen para birimi sembolünün türünü belirten bir Boole **değeri: Uluslararası, yurtiçi ise** **false** .

*Iosbase* \
Ayarlanan para birimi sembolünün isteğe bağlı olduğunu gösterdiği zaman bir biçim bayrağı. Aksi takdirde, gereklidir

*Durum* \
İşlem başarılı olup olmadığına göre akış durumu için uygun bit maskesi öğelerini ayarlar.

*val* \
Dönüştürülmüş sırayı depolayan bir dize.

### <a name="return-value"></a>Dönüş Değeri

Parasal giriş alanının ötesinde ilk öğeyi ele alan bir giriş Yineleyici.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlevi de [do_get](#do_get) `(first, last, Intl, Iosbase, State, val)` döndürür.

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

## <a name="iter_type"></a>money_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, **InputIterator**şablon parametresi için bir eş anlamlı.

## <a name="money_get"></a>money_get::money_get

Parasal değerleri temsil eden dizilerden sayısal değerler ayıklamak için kullanılan `money_get` türündeki nesneler için Oluşturucu.

```cpp
explicit money_get(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

*_Refs* \
Nesnenin bellek yönetimi türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

*_Refs* parametresi için olası değerler ve bunların önemi şunlardır:

- 0: nesnenin ömrü, kendisini içeren yerel ayarlara göre yönetilir.

- 1: nesnenin ömrü el ile yönetilmelidir.

- \> 1: Bu değerler tanımlı değil.

Yok edicisi korunduğu için doğrudan örnek mümkün değildir.

Oluşturucu kendi temel nesnesini **locale::** [model](../standard-library/locale-class.md#facet_class)( *_Refs*) ile başlatır.

## <a name="string_type"></a>money_get::string_type

**CharType**türünde karakterler içeren bir dizeyi tanımlayan tür.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, [basic_string](../standard-library/basic-string-class.md)sınıf şablonunun bir özelleştirmesi tanımlar.

## <a name="see-also"></a>Ayrıca bkz.

[\<locale >](../standard-library/locale.md) \
[model sınıfı](../standard-library/locale-class.md#facet_class) \
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
