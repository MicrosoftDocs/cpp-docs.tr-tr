---
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
ms.openlocfilehash: dae6f62a0eda9263986a77b82754596d17be94e5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373161"
---
# <a name="ctype-class"></a>ctype Sınıfı

Büyük küçük harflerden ve yerel karakter kümesiyle yerel ayar tarafından kullanılan küme arasında dönüştürme yapan, karakterleri sınıflandırmak için kullanılan model sağlayan bir sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>Parametreler

*Chartype*\
Bir program içindeki karakterleri kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için ilk girişim benzersiz `id`bir pozitif değer depolar. Sınıflandırma ölçütü temel sınıf ctype_base içindeki bir iç içe bit maskesi türünde sağlanır.

C++ Standart Kitaplığı, bu sınıf şablonunun iki açık uzmanlık özelliğini tanımlar:

- `ctype<char>`, farklılıkları ayrı ayrı açıklanan açık bir uzmanlık. Daha fazla bilgi için [ctype&lt;char&gt; Class'a](../standard-library/ctype-char-class.md)bakın.

- `ctype<wchar_t>`, öğeleri geniş karakterler olarak ele alan.

Sınıf şablonunun `ctype<CharType>`diğer uzmanlıkları:

- *CharType* *türünde* bir ch değerini ifade **char** `(char)ch`yle char türüne dönüştürün.

- Bir değer *bayt* türü **char** ifadesini *chartype* türünde `CharType(byte)`bir değere dönüştürün.

Diğer tüm **işlemler, açık** uzmanlık `ctype<char>`için olduğu gibi char değerleri üzerinde gerçekleştirilir.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Ctype](#ctype)|Karakterler için yerel yisimler olarak hizmet veren sınıf `ctype` nesneleri için oluşturucu.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[do_is](#do_is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınamak veya bir aralıktaki her bir karakter özniteliğini sınıflandırmak ve bunları bir dizide saklamak için çağrılan bir sanal işlev.|
|[do_narrow](#do_narrow)|Bir yerel ayar tarafından kullanılan `CharType` tür karakterini yerel karakter kümesindeki **char** türüne karşılık gelen karaktere dönüştürmek için çağrılan sanal işlev.|
|[do_scan_is](#do_scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|
|[do_scan_not](#do_scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|
|[do_tolower](#do_tolower)|Bir karakteri ya da karakter aralığını kendi küçük harflerine dönüştürmek için çağrılan bir sanal işlev.|
|[do_toupper](#do_toupper)|Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.|
|[do_widen](#do_widen)|Yerel karakter kümesindeki **char** türündeki bir karakteri, yerel bir yerel `CharType` ayar tarafından kullanılan türün ilgili karakterine dönüştürmek için çağrılan sanal bir işlev.|
|[is](#is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınar veya bir aralıktaki her bir karakter özniteliğini sınıflandırır ve bunları bir dizide saklar.|
|[Dar](#narrow)|Bir yerel ayar `CharType` tarafından kullanılan tür karakterini, yerel karakter kümesindeki char türüne karşılık gelen karaktere dönüştürür.|
|[scan_is](#scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.|
|[scan_not](#scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.|
|[Tolower](#tolower)|Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.|
|[Toupper](#toupper)|Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.|
|[Genişlet -mek](#widen)|Yerel karakter kümesindeki **char** türündeki bir karakteri, yerel `CharType` bir yerel ayar tarafından kullanılan türün ilgili karakterine dönüştürür.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="ctypechar_type"></a><a name="char_type"></a>ctype::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Tür, şablon parametresi *CharType*ile eş anlamlıdır.

### <a name="example"></a>Örnek

İade değeri olarak kullanan `char_type` bir örnek için üye [işlevinin genişletilmesine](#widen) bakın.

## <a name="ctypectype"></a><a name="ctype"></a>ctype::ctype

Karakterler için yerel fatlar olarak hizmet veren sınıf ctype nesneleri için oluşturucu.

```cpp
explicit ctype(size_t _Refs = 0);
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

Kurucu, temel nesnesini `locale::facet` yerel olarak başlaşır:: **locale::**[fason](../standard-library/locale-class.md#facet_class)( ). `_Refs`

## <a name="ctypedo_is"></a><a name="do_is"></a>ctype::do_is

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
Karakterin test edilen maske değeri.

*Caner*\
Öznitelikleri test edilecek karakter.

*Ilk*\
Öznitelikleri sınıflandırılacak olan aralıktaki ilk karaktere işaretçi.

*Son*\
Öznitelikleri sınıflandırılacak olan aralıktaki son karakteri hemen izleyen karaktere işaretçi.

*Dest*\
Her karakterin özniteliklerini karakterize eden maske değerlerinin depolandığı dizinin başlangıcına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlev, test edilen karakter maske değeri tarafından açıklanan özniteliğe sahipse **doğru** olan bir Boolean değeri döndürür; özniteliği yoksa **false.**

İkinci üye işlev, aralıktaki her karakterin özniteliklerini karakterize eden maske değerlerini içeren bir dizi döndürür.

### <a name="remarks"></a>Açıklamalar

Karakterlerin özniteliklerini sınıflandıran maske değerleri, ctype'ın türetildiği [sınıf ctype_base](../standard-library/ctype-base-class.md)tarafından sağlanır. İlk üye işlev bitmasks olarak adlandırılan ve mantıksal bitwise işleçleri (&#124; , & , ^ , ~) tarafından maske değerlerinin kombinasyonu oluşan ilk parametresi için ifadeleri kabul edebilir.

### <a name="example"></a>Örnek

[Bkz.](#is)örneğin , hangi `do_is`çağırır .

## <a name="ctypedo_narrow"></a><a name="do_narrow"></a>ctype::do_dar

Bir yerel ayar tarafından kullanılan `CharType` tür karakterini yerel karakter kümesindeki **char** türüne karşılık gelen karaktere dönüştürmek için çağrılan sanal işlev.

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

*Caner*\
Dönüştürülmek üzere `Chartype` yerel olarak kullanılan tür karakteri.

*Varsayılan*\
Üye işlev tarafından, **char**türünde karşıt `CharType` karakterleri olmayan tür deki karakterlere atanacak varsayılan değer.

*Ilk*\
Dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karaktere işaretçi.

*Dest*\
Dönüştürülmüş karakter aralığını depolayan hedef aralığındaki ilk karakter **eki char'a** bir const işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi, karşıt tanımlanmamışsa, tür `CharType` veya *varsayılan* parametre karakterine karşılık gelen tür char'ın yerel karakterini döndürür.

İkinci korumalı üye işlevi, bir işaretçiyi türdeki `CharType`karakterlerden dönüştürülen yerel karakterlerin hedef aralığına döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablon `dest` `I`işlevi [ `do_narrow` `first` ] `I`aralığında `default`[ `I` [ ], `last`  -  `first`) değeri depolar .

### <a name="example"></a>Örnek

Dar [için](#narrow)örneğe bakın `do_narrow`, hangi çağırır .

## <a name="ctypedo_scan_is"></a><a name="do_scan_is"></a>ctype::do_scan_is

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.

```cpp
virtual const CharType *do_scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Bir karakterle eşleşecek maske değeri.

*Ilk*\
Aralıktaki ilk karakterin taranacak bir işaretçisi.

*Son*\
Taranacak aralıktaki son karakteri hemen izleyen karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşen bir aralıktaki ilk karaktere işaretçi. Böyle bir değer yoksa, işlev *son*döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, [do_is](#do_is)( `maskVal` \* `ptr`, `first` `last`) doğru olduğu aralıktaki en küçük işaretçiyi `ptr` [ , ) döndürür.

### <a name="example"></a>Örnek

[scan_is](#scan_is)için örnek bakın `do_scan_is`, hangi çağırır .

## <a name="ctypedo_scan_not"></a><a name="do_scan_not"></a>ctype::do_scan_not

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.

```cpp
virtual const CharType *do_scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Maske değeri bir karakterle eşleşmez.

*Ilk*\
Aralıktaki ilk karakterin taranacak bir işaretçisi.

*Son*\
Taranacak aralıktaki son karakteri hemen izleyen karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşmeyen bir aralıktaki ilk karaktere işaretçi. Böyle bir değer yoksa, işlev *son*döndürür.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, [do_is](#do_is)( `maskVal` \* `ptr`, `first` `last`) yanlış olduğu aralıktaki en küçük işaretçiyi `ptr` [ , ) döndürür.

### <a name="example"></a>Örnek

[scan_not](#scan_not)için örnek bakın `do_scan_not`, hangi çağırır .

## <a name="ctypedo_tolower"></a><a name="do_tolower"></a>ctype::do_tolower

Bir karakteri veya karakter aralığını küçük harfe dönüştürmek için çağrılan sanal bir işlev.

```cpp
virtual CharType do_tolower(CharType ch) const;

virtual const CharType *do_tolower(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Küçük harfe dönüştürülecek karakter.

*Ilk*\
Servis talepleri dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Servis talepleri dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi *parametre ch*küçük formu döndürür. Küçük bir form yoksa, *ch*döndürür. İkinci korumalı üye işlevi *son*döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablon işlevi `first` `I`her öğenin yerine [ `last`  -  `first`], `do_tolower` `I` `first` [0, ) ile ( [ []) `I`aralığında.

### <a name="example"></a>Örnek

Bkz. [tolower](#tolower)için örnek `do_tolower`, hangi çağırır .

## <a name="ctypedo_toupper"></a><a name="do_toupper"></a>ctype::do_toupper

Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual CharType do_toupper(CharType ch) const;

virtual const CharType *do_toupper(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Büyük harfe dönüştürülecek karakter.

*Ilk*\
Servis talepleri dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Servis talepleri dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karakter işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İlk korunan üye işlevi *parametre ch*büyük harf formunu döndürür. Büyük harf formu yoksa, *ch*döndürür. İkinci korumalı üye işlevi *son*döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablon işlevi `first` `I`her öğenin yerine [ `last`  -  `first`], `do_toupper` `I` `first` [0, ) ile ( [ []) `I`aralığında.

### <a name="example"></a>Örnek

[Toupper](#toupper)için örnek bakınız `do_toupper`, hangi çağırır .

## <a name="ctypedo_widen"></a><a name="do_widen"></a>ctype::do_widen

Yerel karakter kümesindeki **char** türündeki bir karakteri, yerel bir yerel `CharType` ayar tarafından kullanılan türün ilgili karakterine dönüştürmek için çağrılan sanal bir işlev.

```cpp
virtual CharType do_widen(char byte) const;

virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>Parametreler

*Bayt*\
Dönüştürülecek şekilde ayarlanacak yerel karakterdeki **tür char** karakteri.

*Ilk*\
Dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karaktere işaretçi.

*Dest*\
Dönüştürülmüş karakter aralığını depolayan hedef aralığındaki ilk tür `CharType` karakterine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi, `CharType` yerel tür **char**parametre karakterine karşılık gelen tür karakterini döndürür.

İkinci korumalı üye işlevi, `CharType` **char**türü yerel karakterlerden dönüştürülen bir yerel bilgisayar tarafından kullanılan tür deki karakterlerin hedef aralığına bir işaretçiyi döndürür.

### <a name="remarks"></a>Açıklamalar

İkinci korumalı üye şablon `dest` `I`işlevi [ `do_widen` `first`] `I`değerini `I` ( [ ], `last`  -  `first`aralıkta [0, ) depolar.

### <a name="example"></a>Örnek

[Genişletme](#widen)için örneğe bakın `do_widen`, hangi çağırır .

## <a name="ctypeis"></a><a name="is"></a>ctype::is

Tek bir karakterin belirli bir özniteliği olup olmadığını sınar veya bir aralıktaki her karakterin özniteliklerini sınıflandırıp bir dizide depolar.

```cpp
bool is(mask maskVal, CharType ch) const;

const CharType *is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Karakterin test edilen maske değeri.

*Caner*\
Öznitelikleri test edilecek karakter.

*Ilk*\
Öznitelikleri sınıflandırılacak olan aralıktaki ilk karaktere işaretçi.

*Son*\
Öznitelikleri sınıflandırılacak olan aralıktaki son karakteri hemen izleyen karaktere işaretçi.

*Dest*\
Her karakterin özniteliklerini karakterize eden maske değerlerinin depolandığı dizinin başlangıcına işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Test edilen karakter maske değeri tarafından açıklanan özniteliğe sahipse ilk üye işlev **doğru** döndürür; özniteliği yoksa **false.**

İkinci üye işlev, öznitelikleri sınıflandırılacak olan aralıktaki son karaktere bir işaretçiyi döndürür.

### <a name="remarks"></a>Açıklamalar

Karakterlerin özniteliklerini sınıflandıran maske değerleri, ctype'ın türetildiği [sınıf ctype_base Sınıfı](../standard-library/ctype-base-class.md)tarafından sağlanır. İlk üye işlev bitmasks olarak adlandırılan ve mantıksal bitwise işleçleri (&#124; , & , ^ , ~) tarafından maske değerlerinin kombinasyonu oluşan ilk parametresi için ifadeleri kabul edebilir.

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

## <a name="ctypenarrow"></a><a name="narrow"></a>ctype::dar

Bir yerel ayar `CharType` tarafından kullanılan tür karakterlerini yerel karakter kümesindeki **char** türündeki ilgili karakterlere dönüştürür.

```cpp
char narrow(CharType ch, char default = '\0') const;

const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Dönüştürülmek üzere `Chartype` yerel olarak kullanılan tür karakteri.

*Varsayılan*\
Üye işlev tarafından, **char**türünde karşıt `CharType` karakterleri olmayan tür deki karakterlere atanacak varsayılan değer.

*Ilk*\
Dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karaktere işaretçi.

*Dest*\
Dönüştürülmüş karakter aralığını depolayan hedef aralığındaki ilk karakter **eki char'a** bir const işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlev, karşıt lık tanımlı değilse, tür `CharType default` parametre karakterine karşılık gelen tür **char'ın** yerel karakterini döndürür.

İkinci üye işlev, tür `CharType`deki karakterlerden dönüştürülen yerel karakterlerin hedef aralığına bir işaretçiyi döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev [do_narrow](#do_narrow)do_narrow`ch`döndürür ( , `default`). İkinci üye işlev [do_narrow](#do_narrow) do_narrow`first` `last`döndürür ( , , `default`, . `dest` Yalnızca temel kaynak karakterlerin altında `CharType` `narrow`benzersiz bir ters görüntü olması garanti edilir. Bu temel kaynak karakterler için aşağıdaki değişmez `narrow` tutar: ( [genişletmek](#widen) ( **c** ), 0 ) == **c**.

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

## <a name="ctypescan_is"></a><a name="scan_is"></a>ctype::scan_is

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.

```cpp
const CharType *scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Bir karakterle eşleşecek maske değeri.

*Ilk*\
Aralıktaki ilk karakterin taranacak bir işaretçisi.

*Son*\
Taranacak aralıktaki son karakteri hemen izleyen karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşen bir aralıktaki ilk karaktere işaretçi. Böyle bir değer yoksa, işlev *son*döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_scan_is](#do_scan_is)`maskVal`döndürür ( , , . `first` `last`

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

## <a name="ctypescan_not"></a><a name="scan_not"></a>ctype::scan_not

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.

```cpp
const CharType *scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*\
Maske değeri bir karakterle eşleşmez.

*Ilk*\
Aralıktaki ilk karakterin taranacak bir işaretçisi.

*Son*\
Taranacak aralıktaki son karakteri hemen izleyen karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirli bir maskeyle eşleşmeyen bir aralıktaki ilk karaktere işaretçi. Böyle bir değer yoksa, işlev *son*döndürür.

### <a name="remarks"></a>Açıklamalar

Üye işlev [do_scan_not](#do_scan_not)`maskVal`döndürür ( , , . `first` `last`

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

## <a name="ctypetolower"></a><a name="tolower"></a>ctype::tolower

Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.

```cpp
CharType tolower(CharType ch) const;

const CharType *tolower(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Küçük harfe dönüştürülecek karakter.

*Ilk*\
Servis talepleri dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Servis talepleri dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye *işlev, ch*parametresinin küçük biçimini döndürür. Küçük bir form yoksa, *ch*döndürür.

İkinci üye işlev *son*döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev [do_tolower](#do_tolower)do_tolower`ch`döndürür ( ). İkinci üye işlev [do_tolower](#do_tolower)do_tolower`first`döndürür ( , `last`).

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

## <a name="ctypetoupper"></a><a name="toupper"></a>ctype::toupper

Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.

```cpp
CharType toupper(CharType ch) const;
const CharType *toupper(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*Caner*\
Büyük harfe dönüştürülecek karakter.

*Ilk*\
Servis talepleri dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Servis talepleri dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karaktere işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye *işlev, ch*parametresinin büyük harf formunu döndürür. Büyük harf formu yoksa, *ch*döndürür.

İkinci üye işlev *son*döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev [do_toupper](#do_toupper)do_toupper`ch`döndürür ( ). İkinci üye işlev [do_toupper](#do_toupper)do_toupper `first`döndürür ( , `last`).

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

## <a name="ctypewiden"></a><a name="widen"></a>ctype::widen

Yerel karakter kümesindeki **char** türündeki bir karakteri, yerel `CharType` bir yerel ayar tarafından kullanılan türün ilgili karakterine dönüştürür.

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>Parametreler

*Bayt*\
Dönüştürülecek şekilde ayarlanacak yerel karakterdeki tür char karakteri.

*Ilk*\
Dönüştürülecek karakter aralığındaki ilk karaktere işaretçi.

*Son*\
Dönüştürülecek karakter aralığındaki son karakteri hemen izleyen karaktere işaretçi.

*Dest*\
Dönüştürülmüş karakter aralığını depolayan hedef aralığındaki ilk tür `CharType` karakterine işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlev, yerel `CharType` tür **char**parametre karakterine karşılık gelen tür karakterini döndürür.

İkinci üye işlev, **char**türü yerel karakterlerden `CharType` dönüştürülen bir yerel bilgisayar tarafından kullanılan tür karakter hedef aralığına bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

İlk üye işlev [do_widen](#do_widen)do_widen`byte`döndürür ( ). İkinci üye işlev [do_widen](#do_widen)do_widen`first`döndürür ( , , . `last` `dest`

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

[\<yerel>](../standard-library/locale.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
