---
title: money_get sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- xlocmon/std::money_get
- xlocmon/std::money_get::char_type
- xlocmon/std::money_get::iter_type
- xlocmon/std::money_get::string_type
- xlocmon/std::money_get::do_get
- xlocmon/std::money_get::get
dev_langs:
- C++
helpviewer_keywords:
- std::money_get [C++]
- std::money_get [C++], char_type
- std::money_get [C++], iter_type
- std::money_get [C++], string_type
- std::money_get [C++], do_get
- std::money_get [C++], get
ms.assetid: 692d3374-3fe7-4b46-8aeb-f8d91ed66b2e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1e3059a4291d21e11304fdf571d2e12828df26fb
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33861707"
---
# <a name="moneyget-class"></a>money_get Sınıfı

Şablon sınıfı türü sıralarının denetim dönüştürmeleri için yerel ayar modeli olarak hizmet verebilir bir nesneyi tanımlayan `CharType` parasal değerleri için.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType, class InputIterator = istreambuf_iterator<CharType>>
class money_get : public locale::facet;
```

### <a name="parameters"></a>Parametreler

`CharType` Yerel karakter kodlamak için bir program içinde kullanılan türü.

`InputIterator` Yineleyici içinden get işlevleri kendi giriş okuma türü.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[money_get](#money_get)|Nesne türü Oluşturucusu `money_get` parasal değerleri temsil eden serilerinden sayısal değerleri ayıklamak için kullanılır.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.|
|[iter_type](#iter_type)|Bir giriş yineleyiciyi açıklayan tür.|
|[STRING_TYPE](#string_type)|Tür karakterleri içeren bir dize açıklayan türü `CharType`.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_get](#do_get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklamak için çağrılan sanal işlev.|
|[get](#get)|Parasal bir değeri temsil eden bir karakter dizisinden sayısal değeri ayıklar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  money_get::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlamak için kullanılan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **CharType**.

## <a name="do_get"></a>  money_get::do_get

Adlı sanal işlev para değerini temsil eden bir karakter dizisi bir sayısal değer ayıklar.

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`Intl` Para birimi simgesini sırayla beklenen türünü gösteren bir Boole değeri: **true** uluslararası, **false** yurtiçi durumunda.

`Iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde, gereklidir.

`State` Olup olmadığını veya işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`val` Dönüştürülen dizisi depolama bir dize.

### <a name="return-value"></a>Dönüş Değeri

İlk öğe para giriş alanını ötesinde adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

İlk sanal korumalı üye fonksiyonu ilk sırada başlayarak sıralı öğeleri eşleştirmeyi dener [ `first`, `last`) bir tam tanıdığını kadar boş olmayan para alan giriş. Başarılı, bu alan isteğe bağlı olarak bir eksi işaretiyle öncesinde bir veya daha fazla ondalık basamak dizisi dönüştürür varsa ( `-`), miktarını temsil etmek için ve sonuçta depolar [STRING_TYPE](#string_type) nesne `val`. Yineleyici para giriş alanını ötesinde ilk öğe belirleme döndürür. Aksi durumda, boş bir dizi işlev depolar `val` ve ayarlar `ios_base::failbit` içinde `State`. Herhangi bir geçerli para giriş alanını öneki ötesinde ilk öğe belirleme yineleyici döndürür. Dönüş değeri eşitse her iki durumda da `last`, işlev kümeleri `ios_base::eofbit` içinde `State`.

Başarılı olursa türünde bir değer için isteğe bağlı olarak imzalanmış bir basamak dizisi dönüştürür dışında ikinci sanal korumalı üye işlevi, birinci ile aynı şekilde davranır `long double` ve bu değeri depolar `val`.

Para giriş alanını biçimi tarafından belirlenen [yerel model](../standard-library/locale-class.md#facet_class)**fac** etkin çağrı tarafından döndürülen [use_facet](../standard-library/locale-functions.md#use_facet)  <  [ moneypunct](../standard-library/moneypunct-class.md) \< **CharType**, **uluslararası**>> ( **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)).

Özellikle:

- **Fac**. [neg_format](../standard-library/moneypunct-class.md#neg_format) bileşenleri alanının içinde sırayla belirler.

- **Fac**. [curr_symbol](../standard-library/moneypunct-class.md#curr_symbol) para birimi simgesini oluşturduğunu öğelerin sırasını belirler.

- **Fac**. [positive_sign](../standard-library/moneypunct-class.md#positive_sign) bir artı işareti oluşturduğunu öğelerin sırasını belirler.

- **Fac**. [negative_sign](../standard-library/moneypunct-class.md#negative_sign) eksi işareti oluşturduğunu öğelerin sırasını belirler.

- **Fac**. [Gruplandırma](../standard-library/moneypunct-class.md#grouping) basamak herhangi Ondalık ayırıcının solundaki nasıl gruplandırılacağını belirler.

- **Fac**. [thousands_sep](../standard-library/moneypunct-class.md#thousands_sep) herhangi Ondalık ayırıcının sol tarafındaki basamak grupları ayıran öğesi belirler.

- **Fac**. [decimal_point](../standard-library/moneypunct-class.md#decimal_point) tamsayı basamak kesir rakamları ayıran öğesi belirler.

- **Fac**. [frac_digits](../standard-library/moneypunct-class.md#frac_digits) herhangi bir ondalık ayırıcısı sağındaki önemli kesir basamak sayısını belirler. İçin denir daha fazla kesir basamak ile para miktarını ayrıştırılırken `frac_digits`, `do_get` en fazla tükettikten sonra ayrıştırma durdurur `frac_digits` karakter.

Varsa oturum dize ( **fac**. `negative_sign` veya **fac**. `positive_sign`) sahip birden fazla öğesi, yalnızca ilk öğesi burada eşleşen eşit öğesi **money_base::sign** biçimi desende görüntülenir ( **fac**. `neg_format`). Kalan öğeler para giriş alanını sonunda eşleştirilir. Hiçbiri dize para giriş alanını sonraki öğe eşleşen ilk bir öğe varsa, oturum dize boş olarak alınır ve pozitif bir işaretidir.

Varsa **iosbase**. [bayrakları](../standard-library/ios-base-class.md#flags) & [showbase](../standard-library/ios-functions.md#showbase) sıfır olmayan, olan dize **fac**. `curr_symbol` WHERE eşleşmelidir eşit öğesi **money_base::symbol** biçimi desende görüntülenir. Aksi halde, eğer **money_base::symbol** biçimi düzeni sonunda gerçekleşir ve oturum dizesinin öğe eşleştirilmesini kalırsa, para birimi simgesini eşlenemiyor. Aksi takdirde, para birimi simgesini isteğe bağlı olarak eşleştirilir.

Hiçbir örneği varsa **fac**. `thousands_sep` para giriş alanı değeri kısmı ortaya (burada eşit öğesi **money_base::value** biçimi desende görünür), hiçbir gruplandırma kısıtlaması uygulanmaz. Aksi takdirde, gruplandırma kısıtlamalar uygulanan tarafından **fac**. **Gruplandırma** zorlanır. Oluşturulan basamak dizisi düşük düzey tamsayı temsil Not **fac**. `frac_digits` ondalık basamak ondalık konumun sağında olarak kabul edilir.

Rastgele boşluk eşleşir burada eşit öğesi **money_base::space** biçimi düzeni sonunda göründüğü dışında biçimi desende görüntülenir. Aksi takdirde hiçbir iç boşluk eşleştirilir. Bir öğenin *ch* boşluk varsa kabul [use_facet](../standard-library/locale-functions.md#use_facet) < [ctype](../standard-library/ctype-class.md) \< **CharType**>> () **iosbase**. [getloc](../standard-library/ios-base-class.md#getloc)). [olan](../standard-library/ctype-class.md#is)( **ctype_base::space**, *ch*) olan **doğru**.

### <a name="example"></a>Örnek

Örneğin bkz [almak](#get), çağıran `do_get`.

## <a name="get"></a>  money_get::get

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

`first` Dönüştürülecek dizisi başına adresleme yineleyici girin.

`last` Dönüştürülecek bitişinde adresleme yineleyici girin.

`Intl` Para birimi simgesini sırayla beklenen türünü gösteren bir Boole değeri: **true** uluslararası, **false** yurtiçi durumunda.

`Iosbase` Bir biçim hangi bayrak kümesi para birimi simgesini isteğe bağlıdır; olduğunu gösterdiğinde Aksi takdirde gereklidir

`State` Olup işlemleri başarılı göre akış durumu için uygun bir bit maskesi öğelerini ayarlar.

`val` Dönüştürülen dizisi depolama bir dize.

### <a name="return-value"></a>Dönüş Değeri

İlk öğe para giriş alanını ötesinde adresleme giriş yineleyici.

### <a name="remarks"></a>Açıklamalar

Her iki üye işlevleri dönmek [do_get](#do_get)`(first, last, Intl, Iosbase, State, val)`.

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

## <a name="iter_type"></a>  money_get::iter_type

Bir giriş yineleyiciyi açıklayan tür.

```cpp
typedef InputIterator iter_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eş anlamlı türüdür **InputIterator**.

## <a name="money_get"></a>  money_get::money_get

Nesne türü Oluşturucusu `money_get` parasal değerleri temsil eden serilerinden sayısal değerleri ayıklamak için kullanılır.

```cpp
explicit money_get(size_t _Refs = 0);
```

### <a name="parameters"></a>Parametreler

`_Refs` Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.

### <a name="remarks"></a>Açıklamalar

Olası değerler için `_Refs` parametre ve bunların anlamlı:

- 0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.

- 1: nesne ömrü el ile yönetilmesi gerekir.

- \> 1: Bu değerleri tanımlanmamış.

Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.

Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)(**_ *** Refs*).

## <a name="string_type"></a>  money_get::string_type

Tür karakterleri içeren bir dize açıklayan türü **CharType**.

```cpp
typedef basic_string<CharType, Traits, Allocator> string_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon sınıfı uzmanlaşması türünü açıklayan [basic_string](../standard-library/basic-string-class.md).

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)<br/>
[facet sınıfı](../standard-library/locale-class.md#facet_class)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
