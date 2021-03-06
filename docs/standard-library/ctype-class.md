---
description: 'Daha fazla bilgi edinin: CType sınıfı'
title: ctype Sınıfı
ms.date: 11/04/2016
f1_keywords:
- xlocale/std::ctype
- xlocale/std::ctype::char_type
- xlocale/std::ctype::do_is
- xlocale/std::ctype::do_narrow
- xlocale/std::ctype::do_scan_is
- xlocale/std::ctype::do_scan_not
- xlocale/std::ctype::do_tolower
- xlocale/std::ctype::do_toupper
- xlocale/std::ctype::do_widen
- xlocale/std::ctype::is
- xlocale/std::ctype::narrow
- xlocale/std::ctype::scan_is
- xlocale/std::ctype::scan_not
- xlocale/std::ctype::tolower
- xlocale/std::ctype::toupper
- xlocale/std::ctype::widen
helpviewer_keywords:
- std::ctype [C++]
- std::ctype [C++], char_type
- std::ctype [C++], do_is
- std::ctype [C++], do_narrow
- std::ctype [C++], do_scan_is
- std::ctype [C++], do_scan_not
- std::ctype [C++], do_tolower
- std::ctype [C++], do_toupper
- std::ctype [C++], do_widen
- std::ctype [C++], is
- std::ctype [C++], narrow
- std::ctype [C++], scan_is
- std::ctype [C++], scan_not
- std::ctype [C++], tolower
- std::ctype [C++], toupper
- std::ctype [C++], widen
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
ms.openlocfilehash: 9ef23707aa08e0fb3ad7edcff07bd2c6a4ae3814
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233090"
---
# <a name="ctype-class"></a>ctype Sınıfı

Büyük küçük harflerden ve yerel karakter kümesiyle yerel ayar tarafından kullanılan küme arasında dönüştürme yapan, karakterleri sınıflandırmak için kullanılan model sağlayan bir sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>Parametreler

*CharType*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim, içinde benzersiz bir pozitif değer depolar `id` . Sınıflandırma ölçütü temel sınıf ctype_base içindeki bir iç içe bit maskesi türünde sağlanır.

C++ standart kitaplığı, bu sınıf şablonunun iki açık uzmanlığını tanımlar:

- `ctype<char>`, farkları ayrı olarak açıklanan açık bir özelleşme. Daha fazla bilgi için bkz. [CType &lt; char &gt; sınıfı](../standard-library/ctype-char-class.md).

- `ctype<wchar_t>`öğeleri geniş karakter olarak ele alır.

Sınıf şablonunun diğer özelleştirilmiş oluşturmaları `ctype<CharType>` :

- *CharType* türündeki *bir değeri* , ifadesi ile türünde bir değere dönüştürür **`char`** `(char)ch` .

- Türü bir değer *baytı* **`char`** , ifadesiyle *CharType* türünde bir değere dönüştürür `CharType(byte)` .

Diğer tüm işlemler, **`char`** Açık özelleştirme için aynı şekilde değerler üzerinde gerçekleştirilir `ctype<char>` .

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[CType](#ctype)|`ctype`Karakterlerin yerel ayar modelleri olarak sunan sınıfının nesneleri için Oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_is](#do_is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınamak veya bir aralıktaki her bir karakter özniteliğini sınıflandırmak ve bunları bir dizide saklamak için çağrılan bir sanal işlev.|
|[do_narrow](#do_narrow)|Yerel `CharType` karakter kümesindeki türü karşılık gelen bir yerel ayar tarafından kullanılan türdeki bir karakteri dönüştürmek için çağrılan bir sanal işlev **`char`** .|
|[do_scan_is](#do_scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|
|[do_scan_not](#do_scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|
|[do_tolower](#do_tolower)|Bir karakteri ya da karakter aralığını kendi küçük harflerine dönüştürmek için çağrılan bir sanal işlev.|
|[do_toupper](#do_toupper)|Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.|
|[do_widen](#do_widen)|Yerel karakter kümesindeki türü bir karakteri yerel **`char`** ayar tarafından kullanılan türden karşılık gelen karaktere dönüştüren bir sanal işlev `CharType` .|
|[is](#is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınar veya bir aralıktaki her bir karakter özniteliğini sınıflandırır ve bunları bir dizide saklar.|
|[narrow](#narrow)|`CharType`Bir yerel ayar tarafından kullanılan bir karakteri yerel karakter kümesindeki char türünde karşılık gelen karaktere dönüştürür.|
|[scan_is](#scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.|
|[scan_not](#scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.|
|[ToLower](#tolower)|Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.|
|[ToUpper](#toupper)|Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.|
|[Genişlet](#widen)|**`char`** Yerel karakter kümesindeki türü bir karakteri `CharType` yerel ayar tarafından kullanılan türdeki karşılık gelen karaktere dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="ctypechar_type"></a><a name="char_type"></a> CType:: char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, *CharType* şablon parametresi için bir eş anlamlı.

### <a name="example"></a>Örnek

Dönüş değeri olarak kullanılan bir [örnek için bkz](#widen) . üye işlevi `char_type` .

## <a name="ctypectype"></a><a name="ctype"></a> CType:: CType

Karakterlerin yerel ayar modelleri olarak sunan CType sınıfının nesneleri için Oluşturucu.

```cpp
explicit ctype(size_t _Refs = 0);
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

Oluşturucu kendi `locale::facet` temel nesnesini **locale::**[model](../standard-library/locale-class.md#facet_class)() ile başlatır `_Refs` .

## <a name="ctypedo_is"></a><a name="do_is"></a> CType::d o_is

Tek bir karakterin belirli bir özniteliği olup olmadığını sınamak veya bir aralıktaki her bir karakter özniteliğini sınıflandırmak ve bunları bir dizide saklamak için çağrılan bir sanal işlev.

```cpp
virtual bool do_is(
    mask maskVal,
    CharType ch) const;

virtual const CharType *do_is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Karakterin test edileceği maske değeri.

*denetleyebilirsiniz*\
Öznitelikleri sınanacak olan karakter.

*adı*\
İçindeki öznitelikleri sınıflandırılacak olan aralıktaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Öznitelikleri sınıflandırılacak aralıktaki son karakteri izleyen karaktere yönelik bir işaretçi.

*HD*\
Maske değerlerinin her bir karakterin özniteliklerini karakterize olarak niteleyen dizinin başlangıcına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, **`true`** test edilen karakterin maske değeri tarafından tanımlanan özniteliği varsa, özniteliğe sahip olup olmadığını belirten bir Boole değeri döndürür **`false`** .

İkinci üye işlevi, aralıktaki her bir karakterin özniteliklerini karakterize eden maske değerlerini içeren bir dizi döndürür.

### <a name="remarks"></a>Açıklamalar

Karakterlerin özniteliklerini sınıflandırın maske değerleri, CType 'ın türettiği [ctype_base](../standard-library/ctype-base-class.md)sınıf tarafından sağlanır. İlk üye işlevi, bit maskeleri olarak adlandırılan ilk parametresi için ifadeleri kabul edebilir ve mantıksal bit düzeyinde işleçlere (&#124;, &, ^, ~) göre maske değerlerinin birleşiminden oluşturulur.

### <a name="example"></a>Örnek

Çağrısı [için bkz](#is) `do_is` ..

## <a name="ctypedo_narrow"></a><a name="do_narrow"></a> CType::d o_narrow

Yerel `CharType` karakter kümesindeki türü karşılık gelen bir yerel ayar tarafından kullanılan türdeki bir karakteri dönüştürmek için çağrılan bir sanal işlev **`char`** .

```cpp
virtual char do_narrow(
    CharType ch,
    char default = '\0') const;

virtual const CharType* do_narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
`Chartype`Dönüştürülecek yerel ayar tarafından kullanılan türün karakteri.

*varsayılanını*\
Üye işlevi tarafından, türünde `CharType` karşılık gelen karakterlere sahip olmayan karakterlerin karakterlerine atanacak varsayılan değer **`char`** .

*adı*\
Dönüştürülecek karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dönüştürülecek karakter aralığındaki son karakterin hemen ardından gelen karaktere yönelik bir işaretçi.

*HD*\
**`char`** Hedef aralıktaki, dönüştürülmüş karakter aralığını depolayan ilk karaktere yönelik const işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi char türünde parametre karakterine karşılık gelen yerel karakteri `CharType` veya hiçbir karşılık tanımlanmamışsa, *varsayılan* değerini döndürür.

İkinci korumalı üye işlevi, türündeki karakterlerden dönüştürülen yerel karakterlerin hedef aralığına bir işaretçi döndürür `CharType` .

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablonu işlevi [] içinde `dest` [ `I` ] `do_narrow` ( `first` [ `I` ],) değerini `default` `I` [0,) aralığında depolar `last`  -  `first` .

### <a name="example"></a>Örnek

' İ çağıran [daraltma](#narrow)örneğine bakın `do_narrow` .

## <a name="ctypedo_scan_is"></a><a name="do_scan_is"></a> CType::d o_scan_is

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.

```cpp
virtual const CharType *do_scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Bir karakterle eşleştirilecek maske değeri.

*adı*\
Taranacak aralıktaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Taranacak aralıktaki son karakteri izleyen karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşen bir aralıktaki ilk karaktere yönelik bir işaretçi. Böyle bir değer yoksa, işlev *son* döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, `ptr` `first` `last` [do_is](#do_is)( `maskVal` , \* `ptr` ) değeri için [,) aralığında en küçük işaretçiyi döndürür.

### <a name="example"></a>Örnek

Çağıran [scan_is](#scan_is)için örneğe bakın `do_scan_is` .

## <a name="ctypedo_scan_not"></a><a name="do_scan_not"></a> CType::d o_scan_not

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.

```cpp
virtual const CharType *do_scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Maske değeri bir karakterle eşleştirilemez.

*adı*\
Taranacak aralıktaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Taranacak aralıktaki son karakteri izleyen karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşmeyen bir aralıktaki ilk karaktere yönelik bir işaretçi. Böyle bir değer yoksa, işlev *son* döndürür.

### <a name="remarks"></a>Açıklamalar

Protected member işlevi, `ptr` `first` `last` [do_is](#do_is)( `maskVal` , \* `ptr` ) false olan [,) aralığında en küçük işaretçiyi döndürür.

### <a name="example"></a>Örnek

Çağıran [scan_not](#scan_not)için örneğe bakın `do_scan_not` .

## <a name="ctypedo_tolower"></a><a name="do_tolower"></a> CType::d o_tolower

Bir karakteri ya da karakter aralığını küçük harfe dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual CharType do_tolower(CharType ch) const;

virtual const CharType *do_tolower(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Küçük harfe Dönüştürülecek karakter.

*adı*\
Örnekleri dönüştürülecek olan karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Örnekleri dönüştürülecek olan karakter aralığındaki son karakteri izleyen karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi, *ch* parametresinin küçük harfli biçimini döndürür. Küçük harfli bir form yoksa *ch* döndürür. İkinci korumalı üye işlevi *son* döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablonu işlevi, `first` `I` [0,) aralığındaki [] öğelerinin her bir [] öğesini `I` `last`  -  `first` `do_tolower` ( `first` [ `I` ]) ile değiştirir.

### <a name="example"></a>Örnek

Öğesini çağıran, [ToLower](#tolower)örneğine bakın `do_tolower` .

## <a name="ctypedo_toupper"></a><a name="do_toupper"></a> CType::d o_toupper

Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual CharType do_toupper(CharType ch) const;

virtual const CharType *do_toupper(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Büyük harfe Dönüştürülecek karakter.

*adı*\
Örnekleri dönüştürülecek olan karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Örnekleri dönüştürülecek olan karakter aralığındaki son karakteri izleyen karakter işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi, *ch* parametresinin büyük harfli biçimini döndürür. Büyük harfli form yoksa *ch* döndürür. İkinci korumalı üye işlevi *son* döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablonu işlevi, `first` `I` [0,) aralığındaki [] öğelerinin her bir [] öğesini `I` `last`  -  `first` `do_toupper` ( `first` [ `I` ]) ile değiştirir.

### <a name="example"></a>Örnek

' İ çağıran [ToUpper](#toupper)örneğine bakın `do_toupper` .

## <a name="ctypedo_widen"></a><a name="do_widen"></a> CType::d o_widen

Yerel karakter kümesindeki türü bir karakteri yerel **`char`** ayar tarafından kullanılan türden karşılık gelen karaktere dönüştüren bir sanal işlev `CharType` .

```cpp
virtual CharType do_widen(char byte) const;

virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>Parametreler

*bayt*\
**`char`** Dönüştürülecek yerel karakter kümesindeki tür karakteri.

*adı*\
Dönüştürülecek karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dönüştürülecek karakter aralığındaki son karakterin hemen ardından gelen karaktere yönelik bir işaretçi.

*HD*\
`CharType`Hedef aralıktaki, dönüştürülmüş karakter aralığını depolayan ilk karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi, `CharType` yerel türdeki parametre karakterine karşılık gelen türün karakterini döndürür **`char`** .

İkinci korumalı üye işlevi, `CharType` türünün yerel karakterlerinden dönüştürülmüş bir yerel ayar tarafından kullanılan türdeki karakterlerin hedef aralığına bir işaretçi döndürür **`char`** .

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablonu işlevi [] içinde `dest` [ `I` ] `do_widen` ( `first` [ `I` ]) değerini `I` [0,) aralığında depolar `last`  -  `first` .

### <a name="example"></a>Örnek

Öğesini çağıran, [Genişlet](#widen)için örneğe bakın `do_widen` .

## <a name="ctypeis"></a><a name="is"></a> CType::

Tek bir karakterin belirli bir özniteliğe sahip olup olmadığını veya aralıktaki her karakterin özniteliklerini sınıflandırıp sınıflandırmadığını sınar ve bunları bir dizi içinde depolar.

```cpp
bool is(mask maskVal, CharType ch) const;

const CharType *is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Karakterin test edileceği maske değeri.

*denetleyebilirsiniz*\
Öznitelikleri sınanacak olan karakter.

*adı*\
İçindeki öznitelikleri sınıflandırılacak olan aralıktaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Öznitelikleri sınıflandırılacak aralıktaki son karakteri izleyen karaktere yönelik bir işaretçi.

*HD*\
Maske değerlerinin her bir karakterin özniteliklerini karakterize olarak niteleyen dizinin başlangıcına yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, **`true`** test edilen karakter maske değeri tarafından tanımlanan özniteliğe sahipse döndürür; **`false`** özniteliği yoksa.

İkinci üye işlevi, öznitelikleri sınıflandırılacak olan aralıktaki son karaktere bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Karakterlerin özniteliklerini sınıflandırın maske değerleri, CType 'ın türetildiği sınıf [Ctype_base sınıfı](../standard-library/ctype-base-class.md)tarafından sağlanır. İlk üye işlevi, bit maskeleri olarak adlandırılan ilk parametresi için ifadeleri kabul edebilir ve mantıksal bit düzeyinde işleçlere (&#124;, &, ^, ~) göre maske değerlerinin birleşiminden oluşturulur.

### <a name="example"></a>Örnek

```cpp
// ctype_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main() {
   locale loc1 ( "German_Germany" ), loc2 ( "English_Australia" );

   if (use_facet<ctype<char> > ( loc1 ).is( ctype_base::alpha, 'a' ))
      cout << "The character 'a' in locale loc1 is alphabetic."
           << endl;
   else
      cout << "The character 'a' in locale loc1 is not alphabetic."
           << endl;

   if (use_facet<ctype<char> > ( loc2 ).is( ctype_base::alpha, '!' ))
      cout << "The character '!' in locale loc2 is alphabetic."
           << endl;
   else
      cout << "The character '!' in locale loc2 is not alphabetic."
           << endl;

   char *string = "Hello, my name is John!";
   ctype<char>::mask maskarray[30];
   use_facet<ctype<char> > ( loc2 ).is(
      string, string + strlen(string), maskarray );
   for (unsigned int i = 0; i < strlen(string); i++) {
      cout << string[i] << ": "
           << (maskarray[i] & ctype_base::alpha  "alpha"
                                                : "not alpha")
           << endl;;
   };
}
```

## <a name="ctypenarrow"></a><a name="narrow"></a> CType:: dar

`CharType`Bir yerel ayar tarafından kullanılan türdeki karakterleri yerel karakter kümesindeki türü karşılık gelen karakterlere dönüştürür **`char`** .

```cpp
char narrow(CharType ch, char default = '\0') const;

const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
`Chartype`Dönüştürülecek yerel ayar tarafından kullanılan türün karakteri.

*varsayılanını*\
Üye işlevi tarafından, türünde `CharType` karşılık gelen karakterlere sahip olmayan karakterlerin karakterlerine atanacak varsayılan değer **`char`** .

*adı*\
Dönüştürülecek karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dönüştürülecek karakter aralığındaki son karakterin hemen ardından gelen karaktere yönelik bir işaretçi.

*HD*\
**`char`** Hedef aralıktaki, dönüştürülmüş karakter aralığını depolayan ilk karaktere yönelik const işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, karşılık **`char`** geldiği tanımlı değilse, türünün parametre karakterine karşılık gelen yerel karakterini döndürür `CharType default` .

İkinci üye işlevi, türündeki karakterlerden dönüştürülen yerel karakterlerin hedef aralığına bir işaretçi döndürür `CharType` .

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [do_narrow](#do_narrow)döndürür ( `ch` , `default` ). İkinci üye işlevi [do_narrow](#do_narrow) döndürür (,,, `first` `last` `default` `dest` ). Yalnızca temel kaynak karakterlerin altında benzersiz bir ters görüntü olması garanti edilir `CharType` `narrow` . Bu temel kaynak karakterler için şu sabit tutar: `narrow` ( [Genişlet](#widen) ( **c** ), 0) = = **c**.

### <a name="example"></a>Örnek

```cpp
// ctype_narrow.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "english" );
   wchar_t *str1 = L"\x0392fhello everyone";
   char str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).narrow
      ( str1, str1 + wcslen(str1), 'X', &str2[0] ) != 0);  // C4996
   str2[wcslen(str1)] = '\0';
   wcout << str1 << endl;
   cout << &str2[0] << endl;
}
```

```Output
Xhello everyone
```

## <a name="ctypescan_is"></a><a name="scan_is"></a> CType:: scan_is

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.

```cpp
const CharType *scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Bir karakterle eşleştirilecek maske değeri.

*adı*\
Taranacak aralıktaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Taranacak aralıktaki son karakteri izleyen karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşen bir aralıktaki ilk karaktere yönelik bir işaretçi. Böyle bir değer yoksa, işlev *son* döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_scan_is](#do_scan_is)döndürür ( `maskVal` , `first` , `last` ).

### <a name="example"></a>Örnek

```cpp
// ctype_scan_is.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_is
      ( ctype_base::punct, string, string + strlen(string) );
   cout << "The first punctuation is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
The first punctuation is "," at position: 5
```

## <a name="ctypescan_not"></a><a name="scan_not"></a> CType:: scan_not

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.

```cpp
const CharType *scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Maske değeri bir karakterle eşleştirilemez.

*adı*\
Taranacak aralıktaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Taranacak aralıktaki son karakteri izleyen karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşmeyen bir aralıktaki ilk karaktere yönelik bir işaretçi. Böyle bir değer yoksa, işlev *son* döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlevi [do_scan_not](#do_scan_not)döndürür ( `maskVal` , `first` , `last` ).

### <a name="example"></a>Örnek

```cpp
// ctype_scan_not.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char *string = "Hello, my name is John!";

   const char* i = use_facet<ctype<char> > ( loc1 ).scan_not
      ( ctype_base::alpha, string, string + strlen(string) );
   cout << "First nonalpha character is \"" << *i << "\" at position: "
      << i - string << endl;
}
```

```Output
First nonalpha character is "," at position: 5
```

## <a name="ctypetolower"></a><a name="tolower"></a> CType:: ToLower

Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.

```cpp
CharType tolower(CharType ch) const;

const CharType *tolower(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Küçük harfe Dönüştürülecek karakter.

*adı*\
Örnekleri dönüştürülecek olan karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Örnekleri dönüştürülecek olan karakter aralığındaki son karakteri izleyen karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, *ch* parametresinin küçük harfli biçimini döndürür. Küçük harfli bir form yoksa *ch* döndürür.

İkinci üye işlevi *son* döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [do_tolower](#do_tolower)() döndürür `ch` . İkinci üye işlevi [do_tolower](#do_tolower)( `first` ,) döndürür `last` .

### <a name="example"></a>Örnek

```cpp
// ctype_tolower.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "HELLO, MY NAME IS JOHN";

   use_facet<ctype<char> > ( loc1 ).tolower
      ( string, string + strlen(string) );
   cout << "The lowercase string is: " << string << endl;
}
```

```Output
The lowercase string is: hello, my name is john
```

## <a name="ctypetoupper"></a><a name="toupper"></a> CType:: ToUpper

Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.

```cpp
CharType toupper(CharType ch) const;
const CharType *toupper(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*denetleyebilirsiniz*\
Büyük harfe Dönüştürülecek karakter.

*adı*\
Örnekleri dönüştürülecek olan karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Örnekleri dönüştürülecek olan karakter aralığındaki son karakteri izleyen karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, *ch* parametresinin büyük harfli biçimini döndürür. Büyük harfli form yoksa *ch* döndürür.

İkinci üye işlevi *son* döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [do_toupper](#do_toupper)() döndürür `ch` . İkinci üye işlevi [do_toupper](#do_toupper)( `first` ,) döndürür `last` .

### <a name="example"></a>Örnek

```cpp
// ctype_toupper.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "German_Germany" );

   char string[] = "Hello, my name is John";

   use_facet<ctype<char> > ( loc1 ).toupper
      ( string, string + strlen(string) );
   cout << "The uppercase string is: " << string << endl;
}
```

```Output
The uppercase string is: HELLO, MY NAME IS JOHN
```

## <a name="ctypewiden"></a><a name="widen"></a> CType:: Genişlet

**`char`** Yerel karakter kümesindeki türü bir karakteri `CharType` yerel ayar tarafından kullanılan türdeki karşılık gelen karaktere dönüştürür.

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>Parametreler

*bayt*\
Dönüştürülecek yerel karakter kümesindeki char türü karakteri.

*adı*\
Dönüştürülecek karakter aralığındaki ilk karaktere yönelik bir işaretçi.

*soyadına*\
Dönüştürülecek karakter aralığındaki son karakterin hemen ardından gelen karaktere yönelik bir işaretçi.

*HD*\
`CharType`Hedef aralıktaki, dönüştürülmüş karakter aralığını depolayan ilk karaktere yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi, `CharType` yerel türdeki parametre karakterine karşılık gelen türün karakterini döndürür **`char`** .

İkinci üye işlevi, `CharType` türünün yerel karakterlerinden dönüştürülmüş bir yerel ayar tarafından kullanılan türdeki karakterlerin hedef aralığına bir işaretçi döndürür **`char`** .

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi [do_widen](#do_widen)() döndürür `byte` . İkinci üye işlevi [do_widen](#do_widen)döndürür ( `first` , `last` , `dest` ).

### <a name="example"></a>Örnek

```cpp
// ctype_widen.cpp
// compile with: /EHsc /W3
#include <locale>
#include <iostream>
using namespace std;

int main( )
{
   locale loc1 ( "English" );
   char *str1 = "Hello everyone!";
   wchar_t str2 [16];
   bool result1 = (use_facet<ctype<wchar_t> > ( loc1 ).widen
      ( str1, str1 + strlen(str1), &str2[0] ) != 0);  // C4996
   str2[strlen(str1)] = '\0';
   cout << str1 << endl;
   wcout << &str2[0] << endl;

   ctype<wchar_t>::char_type charT;
   charT = use_facet<ctype<char> > ( loc1 ).widen( 'a' );
}
```

```Output
Hello everyone!
Hello everyone!
```

## <a name="see-also"></a>Ayrıca bkz.

[\<locale>](../standard-library/locale.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
