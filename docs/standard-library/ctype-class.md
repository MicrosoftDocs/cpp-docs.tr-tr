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
ms.openlocfilehash: e7c474e9112acadc11af889471b1e126dfeeb23f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394149"
---
# <a name="ctype-class"></a>ctype Sınıfı

Büyük küçük harflerden ve yerel karakter kümesiyle yerel ayar tarafından kullanılan küme arasında dönüştürme yapan, karakterleri sınıflandırmak için kullanılan model sağlayan bir sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
template <class CharType>
class ctype : public ctype_base;
```

### <a name="parameters"></a>Parametreler

*CharType*<br/>
Bir program içindeki karakterleri kodlamak için kullanılan tür.

## <a name="remarks"></a>Açıklamalar

Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Depolanan değerine erişmek için yapılan ilk girişim içinde benzersiz bir pozitif değer depolar `id`. Sınıflandırma ölçütü temel sınıf ctype_base içindeki bir iç içe bit maskesi türünde sağlanır.

C++ Standart Kitaplığı, bu şablon sınıfının iki açık uzmanlığını tanımlar:

- `ctype<char>`, açık uzmanlığı farklılıkları ayrı olarak açıklanmıştır. Daha fazla bilgi için [ctype&lt;char&gt; sınıfı](../standard-library/ctype-char-class.md).

- `ctype<wchar_t>`, geniş karakterler olarak öğeleri işler.

Şablon sınıfının diğer uzmanlıkları `ctype<CharType>`:

- Bir değere Dönüştür *ch* türü *CharType* türünde bir değer için **char** ifadesiyle `(char)ch`.

- Bir değere Dönüştür *bayt* türü **char** türünde bir değer için *CharType* ifadesiyle `CharType(byte)`.

Tüm diğer işlemler gerçekleştirilir **char** açık uzmanlığında olduğu gibi değerler `ctype<char>`.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[CType](#ctype)|Sınıfındaki nesneler için oluşturucu `ctype` karakterler için yerel ayar olarak hizmet.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[char_type](#char_type)|Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[do_is](#do_is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınamak veya bir aralıktaki her bir karakter özniteliğini sınıflandırmak ve bunları bir dizide saklamak için çağrılan bir sanal işlev.|
|[do_narrow](#do_narrow)|Türü bir karakteri dönüştürmek için çağrılan sanal işlev `CharType` türü karaktere karşılık gelen bir yerel ayar tarafından kullanılan **char** yerel karakter kümesinde.|
|[do_scan_is](#do_scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|
|[do_scan_not](#do_scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.|
|[do_tolower](#do_tolower)|Bir karakteri ya da karakter aralığını kendi küçük harflerine dönüştürmek için çağrılan bir sanal işlev.|
|[do_toupper](#do_toupper)|Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.|
|[do_widen](#do_widen)|İçin çağrılan sanal işlev türü bir karakteri dönüştürür **char** türü karaktere karşılık gelen için ayarlanmış yerel karakter `CharType` bir yerel ayar tarafından kullanılan.|
|[is](#is)|Tek bir karakterin belirli bir özniteliği olup olmadığını sınar veya bir aralıktaki her bir karakter özniteliğini sınıflandırır ve bunları bir dizide saklar.|
|[daraltma](#narrow)|Türü bir karakteri dönüştürür `CharType` karaktere karşılık gelen yerel karakter kümesindeki char türüne bir yerel ayar tarafından kullanılan.|
|[scan_is](#scan_is)|Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.|
|[scan_not](#scan_not)|Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.|
|[tolower](#tolower)|Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.|
|[toupper](#toupper)|Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.|
|[genişletmek](#widen)|Türü bir karakteri dönüştürür **char** türü karaktere karşılık gelen için ayarlanmış yerel karakter `CharType` bir yerel ayar tarafından kullanılan.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="char_type"></a>  CType::char_type

Bir yerel ayar tarafından kullanılan bir karakteri tanımlayan tür.

```cpp
typedef CharType char_type;
```

### <a name="remarks"></a>Açıklamalar

Şablon parametresi için bir eşanlamlı türüdür *CharType*.

### <a name="example"></a>Örnek

Üye işlevi görmek [genişletmek](#widen) kullanan bir örnek için `char_type` dönüş değeri olarak.

## <a name="ctype"></a>  CType::CType

Karakterler için yerel ayar olarak hizmet veren sınıf ctype nesneler için oluşturucu.

```cpp
explicit ctype(size_t _Refs = 0);
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

Oluşturucu başlatır, `locale::facet` temel nesne **yerel::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).

## <a name="do_is"></a>  CType::do_is

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

*maskVal*<br/>
Karakter test edilecek olduğu maske değeri.

*ch*<br/>
Test edilecek niteliklerini olan karakter.

*ilk*<br/>
Sınıflandırılması niteliklerini olan aralıktaki ilk karaktere bir işaretçi.

*Son*<br/>
Sınıflandırılması niteliklerini olan aralıktaki son karakter takip karaktere bir işaretçi.

*Hedef*<br/>
Nerede depolanacak öznitelikleri her karakter characterizing maskesi değerleri olan bir dizi başlangıcı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi olan bir Boolean değer döndürür **true** test karakter maskesi değeri; açıklanan öznitelik varsa **false** özniteliği başarısız olursa.

İkinci üye işlevi, her karakter aralığındaki özniteliklerini characterizing maskesi değerleri içeren bir dizi döndürür.

### <a name="remarks"></a>Açıklamalar

Öznitelikleri karakterleri sınıflandırma maskesi değerleri sınıfı tarafından sağlanan [ctype_base](../standard-library/ctype-base-class.md), hangi ctype türetir. İlk üye işlevi bit maskeleri başvurulan ve maskesi değerleri bileşiminden mantıksal bit düzeyinde işleçler tarafından oluşturulmuş, ilk parametresinin için ifadeleri kabul edebilir (&#124; &, ^, ~).

### <a name="example"></a>Örnek

Örneğin bakın [olduğu](#is), çağıran `do_is`.

## <a name="do_narrow"></a>  CType::do_narrow

Türü bir karakteri dönüştürmek için çağrılan sanal işlev `CharType` türü karaktere karşılık gelen bir yerel ayar tarafından kullanılan **char** yerel karakter kümesinde.

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

*ch*<br/>
Karakter türü `Chartype` dönüştürülecek yerel ayar tarafından kullanılan.

*default*<br/>
Varsayılan değer türü karakterler için üye işlevi tarafından atanacak `CharType` türü karşılık gelen karakterler olmayan **char**.

*ilk*<br/>
Dönüştürülecek karakter aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek karakter aralığındaki son karakter hemen izleyen karaktere bir işaretçi.

*Hedef*<br/>
Türünün ilk karaktere bir const işaretçisi **char** hedef aralıktaki dönüştürülmüş karakterleri depolar.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlevi parametre karaktere karşılık gelen tür char yerel karakter döndürür `CharType` veya *varsayılan* hiçbir karşılık gelen tanımlanmış olması durumunda.

İkinci korumalı üye işlevi, hedef aralığı türü karakterlerinden dönüştürülen yerel karakter için bir işaretçi döndürür. `CharType`.

### <a name="remarks"></a>Açıklamalar

İkinci üye şablon işlevi depolarında korumalı `dest`[ `I`] değeri `do_narrow`( `first` [ `I`], `default`), için `I` de aralık [0, `last`  -  `first`).

### <a name="example"></a>Örnek

Örneğin bakın [daraltmak](#narrow), çağıran `do_narrow`.

## <a name="do_scan_is"></a>  ctype::do_scan_is

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.

```cpp
virtual const CharType *do_scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*<br/>
Bir karakter eşleştirilecek maske değeri.

*ilk*<br/>
Taranacak aralıktaki ilk karaktere bir işaretçi.

*Son*<br/>
Taranacak aralıktaki son karakter takip karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karaktere bir işaretçi. Böyle bir değer var olup olmadığını işlevi döndürür *son*.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, en küçük işaretçi döndürür `ptr` aralıktaki [ `first`, `last`) kendisi için [do_is](#do_is)( `maskVal`, \* `ptr`) geçerlidir.

### <a name="example"></a>Örnek

Örneğin bakın [scan_is](#scan_is), çağıran `do_scan_is`.

## <a name="do_scan_not"></a>  ctype::do_scan_not

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulmak için çağrılan sanal bir işlev.

```cpp
virtual const CharType *do_scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*<br/>
Bir karakter değil eşleştirilecek maske değeri.

*ilk*<br/>
Taranacak aralıktaki ilk karaktere bir işaretçi.

*Son*<br/>
Taranacak aralıktaki son karakter takip karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karaktere bir işaretçi. Böyle bir değer var olup olmadığını işlevi döndürür *son*.

### <a name="remarks"></a>Açıklamalar

Korumalı üye işlevi, en küçük işaretçi döndürür `ptr` aralıktaki [ `first`, `last`) kendisi için [do_is](#do_is)( `maskVal`, \* `ptr`) yanlış.

### <a name="example"></a>Örnek

Örneğin bakın [scan_not](#scan_not), çağıran `do_scan_not`.

## <a name="do_tolower"></a>  CType::do_tolower

Bir karakteri ya da karakter aralığını küçük harflere dönüştürmek için çağrılan sanal işlev.

```cpp
virtual CharType do_tolower(CharType ch) const;

virtual const CharType *do_tolower(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ch*<br/>
Küçük harflere dönüştürülecek karakter.

*ilk*<br/>
Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek olan durumlarda karakterler aralığının son karakter hemen izleyen karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Küçük harf formun parametresinin ilk korumalı üye işlevi döndürür *ch*. Küçük harf form var olup olmadığını döndürür *ch*. İkinci üye işlevi döndürür korumalı *son*.

### <a name="remarks"></a>Açıklamalar

Her öğe ikinci korumalı üye şablon işlevi yerine geçer `first` [ `I`], için `I` de aralık [0, `last`  -  `first`), ile `do_tolower`( `first` [ `I`]).

### <a name="example"></a>Örnek

Örneğin bakın [tolower](#tolower), çağıran `do_tolower`.

## <a name="do_toupper"></a>  CType::do_toupper

Bir karakteri ya da karakter aralığını kendi büyük harflerine dönüştürmek için çağrılan bir sanal işlev.

```cpp
virtual CharType do_toupper(CharType ch) const;

virtual const CharType *do_toupper(
    CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ch*<br/>
Büyük harfe dönüştürülecek karakter.

*ilk*<br/>
Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek olan durumlarda karakterler aralığının son karakter hemen izleyen karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Büyük harf formun parametresinin ilk korumalı üye işlevi döndürür *ch*. Büyük harf form var olup olmadığını döndürür *ch*. İkinci üye işlevi döndürür korumalı *son*.

### <a name="remarks"></a>Açıklamalar

Her öğe ikinci korumalı üye şablon işlevi yerine geçer `first` [ `I`], için `I` de aralık [0, `last`  -  `first`), ile `do_toupper`( `first` [ `I`]).

### <a name="example"></a>Örnek

Örneğin bakın [toupper](#toupper), çağıran `do_toupper`.

## <a name="do_widen"></a>  CType::do_widen

İçin çağrılan sanal işlev türü bir karakteri dönüştürür **char** türü karaktere karşılık gelen için ayarlanmış yerel karakter `CharType` bir yerel ayar tarafından kullanılan.

```cpp
virtual CharType do_widen(char byte) const;

virtual const char *do_widen(
    const char* first,
    const char* last,
    CharType* dest) const;
```

### <a name="parameters"></a>Parametreler

*byte*<br/>
Karakter türü **char** yerel karakter kümesindeki dönüştürülecek.

*ilk*<br/>
Dönüştürülecek karakter aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek karakter aralığındaki son karakter hemen izleyen karaktere bir işaretçi.

*Hedef*<br/>
Türünün ilk karaktere bir işaretçi `CharType` hedef aralıktaki dönüştürülmüş karakterleri depolar.

### <a name="return-value"></a>Dönüş Değeri

İlk korumalı üye işlev türü karakteri döndürür `CharType` yerel tür parametresi karaktere karşılık gelen **char**.

İkinci korumalı üye işlevi bir işaretçi türü karakterler hedef aralığına döndürür `CharType` türü yerel karakterlerinden dönüştürülen bir yerel ayar tarafından kullanılan **char**.

### <a name="remarks"></a>Açıklamalar

İkinci üye şablon işlevi depolarında korumalı `dest`[ `I`] değeri `do_widen`( `first`[ `I`]), için `I` de aralık [0, `last`  -  `first`).

### <a name="example"></a>Örnek

Örneğin bakın [genişletmek](#widen), çağıran `do_widen`.

## <a name="is"></a>  CType::is

Tek bir karakter, belirli bir özniteliği olan veya bir aralıktaki her bir karakter özniteliğini sınıflandırır ve bunları bir dizide olup olmadığını sınar.

```cpp
bool is(mask maskVal, CharType ch) const;

const CharType *is(
    const CharType* first,
    const CharType* last,
    mask* dest) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*<br/>
Karakter test edilecek olduğu maske değeri.

*ch*<br/>
Test edilecek niteliklerini olan karakter.

*ilk*<br/>
Sınıflandırılması niteliklerini olan aralıktaki ilk karaktere bir işaretçi.

*Son*<br/>
Sınıflandırılması niteliklerini olan aralıktaki son karakter takip karaktere bir işaretçi.

*Hedef*<br/>
Nerede depolanacak öznitelikleri her karakter characterizing maskesi değerleri olan bir dizi başlangıcı için bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi döndürür **true** test karakter maskesi değeri; açıklanan öznitelik varsa **false** özniteliği başarısız olursa.

İkinci üye işlevi sınıflandırılmaya niteliklerini olan aralıktaki son karakter bir işaretçi döndürür.

### <a name="remarks"></a>Açıklamalar

Öznitelikleri karakterleri sınıflandırma maskesi değerleri sınıfı tarafından sağlanan [ctype_base sınıfı](../standard-library/ctype-base-class.md), hangi ctype türetir. İlk üye işlevi bit maskeleri başvurulan ve maskesi değerleri bileşiminden mantıksal bit düzeyinde işleçler tarafından oluşturulmuş, ilk parametresinin için ifadeleri kabul edebilir (&#124; &, ^, ~).

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

## <a name="narrow"></a>  CType::Narrow

Tür karakterleri dönüştürür `CharType` türü karşılık gelen karakterler bir yerel ayar tarafından kullanılan **char** yerel karakter kümesinde.

```cpp
char narrow(CharType ch, char default = '\0') const;

const CharType* narrow(
    const CharType* first,
    const CharType* last,
    char default,
    char* dest) const;
```

### <a name="parameters"></a>Parametreler

*ch*<br/>
Karakter türü `Chartype` dönüştürülecek yerel ayar tarafından kullanılan.

*default*<br/>
Varsayılan değer türü karakterler için üye işlevi tarafından atanacak `CharType` türü karşılık gelen karakterler olmayan **char**.

*ilk*<br/>
Dönüştürülecek karakter aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek karakter aralığındaki son karakter hemen izleyen karaktere bir işaretçi.

*Hedef*<br/>
Türünün ilk karaktere bir const işaretçisi **char** hedef aralıktaki dönüştürülmüş karakterleri depolar.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi yerel karakter türü döndürür **char** parametresi karaktere karşılık gelen `CharType default` değil karşılığı tanımlı değilse.

İkinci üye işlevi, hedef aralığı türü karakterlerinden dönüştürülen yerel karakter için bir işaretçi döndürür. `CharType`.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür [do_narrow](#do_narrow)(`ch`, `default`). İkinci üye işlevi döndürür [do_narrow](#do_narrow) (`first`, `last`, `default`, `dest`). Yalnızca temel kaynak karakterler benzersiz bir ters görüntü sahip olacağı garanti edilir `CharType` altında `narrow`. Bu temel kaynak karakterler için aşağıdaki değişmez değer tutar: `narrow` ( [genişletmek](#widen) ( **c** ), 0) == **c**.

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

## <a name="scan_is"></a>  CType::scan_is

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karakteri bulur.

```cpp
const CharType *scan_is(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*<br/>
Bir karakter eşleştirilecek maske değeri.

*ilk*<br/>
Taranacak aralıktaki ilk karaktere bir işaretçi.

*Son*<br/>
Taranacak aralıktaki son karakter takip karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir maskeyle eşleşen bir aralıktaki ilk karaktere bir işaretçi. Böyle bir değer var olup olmadığını işlevi döndürür *son*.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_scan_is](#do_scan_is)(`maskVal`, `first`, `last`).

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

## <a name="scan_not"></a>  CType::scan_not

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karakteri bulur.

```cpp
const CharType *scan_not(
    mask maskVal,
    const CharType* first,
    const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*maskVal*<br/>
Bir karakter değil eşleştirilecek maske değeri.

*ilk*<br/>
Taranacak aralıktaki ilk karaktere bir işaretçi.

*Son*<br/>
Taranacak aralıktaki son karakter takip karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Belirtilen bir maskeyle eşleşmeyen bir aralıktaki ilk karaktere bir işaretçi. Böyle bir değer var olup olmadığını işlevi döndürür *son*.

### <a name="remarks"></a>Açıklamalar

Üye işlevinin döndürdüğü [do_scan_not](#do_scan_not)(`maskVal`, `first`, `last`).

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

## <a name="tolower"></a>  CType::tolower

Bir karakteri ya da karakter aralığını küçük harflere dönüştürür.

```cpp
CharType tolower(CharType ch) const;

const CharType *tolower(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ch*<br/>
Küçük harflere dönüştürülecek karakter.

*ilk*<br/>
Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek olan durumlarda karakterler aralığının son karakter hemen izleyen karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi parametre küçük biçiminde döndürür *ch*. Küçük harf form var olup olmadığını döndürür *ch*.

İkinci üye işlevi döndürür *son*.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür [do_tolower](#do_tolower)(`ch`). İkinci üye işlevi döndürür [do_tolower](#do_tolower)(`first`, `last`).

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

## <a name="toupper"></a>  CType::toupper

Bir karakteri ya da karakter aralığını büyük harflere dönüştürür.

```cpp
CharType toupper(CharType ch) const;
const CharType *toupper(CharType* first, const CharType* last) const;
```

### <a name="parameters"></a>Parametreler

*ch*<br/>
Büyük harfe dönüştürülecek karakter.

*ilk*<br/>
Dönüştürülecek olan durumlarda karakterler aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek olan durumlarda karakterler aralığının son karakter hemen izleyen karaktere bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi parametresinin büyük harf biçimini döndürür *ch*. Büyük harf form var olup olmadığını döndürür *ch*.

İkinci üye işlevi döndürür *son*.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür [do_toupper](#do_toupper)(`ch`). İkinci üye işlevi döndürür [do_toupper](#do_toupper)( `first`, `last`).

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

## <a name="widen"></a>  CType::widen

Türü bir karakteri dönüştürür **char** türü karaktere karşılık gelen için ayarlanmış yerel karakter `CharType` bir yerel ayar tarafından kullanılan.

```cpp
CharType widen(char byte) const;
const char *widen(const char* first, const char* last, CharType* dest) const;
```

### <a name="parameters"></a>Parametreler

*byte*<br/>
Dönüştürülecek karakter yerel karakter char türüne ayarlayın.

*ilk*<br/>
Dönüştürülecek karakter aralığındaki ilk karaktere bir işaretçi.

*Son*<br/>
Dönüştürülecek karakter aralığındaki son karakter hemen izleyen karaktere bir işaretçi.

*Hedef*<br/>
Türünün ilk karaktere bir işaretçi `CharType` hedef aralıktaki dönüştürülmüş karakterleri depolar.

### <a name="return-value"></a>Dönüş Değeri

İlk üye işlevi türü karakteri döndürür `CharType` yerel tür parametresi karaktere karşılık gelen **char**.

İkinci üye işlevi bir işaretçi türü karakterler hedef aralığına döndürür `CharType` türü yerel karakterlerinden dönüştürülen bir yerel ayar tarafından kullanılan **char**.

### <a name="remarks"></a>Açıklamalar

İlk üye işlevi döndürür [do_widen](#do_widen)(`byte`). İkinci üye işlevi döndürür [do_widen](#do_widen)(`first`, `last`, `dest`).

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

[\<yerel ayar >](../standard-library/locale.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
