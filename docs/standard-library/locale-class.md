---
title: locale Sınıfı
ms.date: 03/19/2019
f1_keywords:
- xlocale/std::locale
- xlocale/std::locale::category
- xlocale/std::locale::combine
- xlocale/std::locale::name
- xlocale/std::locale::classic
- xlocale/std::locale::global
- xlocale/std::locale::operator( )
- xlocale/std::locale::facet
- xlocale/std::locale::id
helpviewer_keywords:
- std::locale [C++]
- std::locale [C++], category
- std::locale [C++], combine
- std::locale [C++], name
- std::locale [C++], classic
- std::locale [C++], global
- std::locale [C++], facet
- std::locale [C++], id
ms.assetid: 7dd6d271-472d-4750-8fb5-ea8f55fbef62
ms.openlocfilehash: 551bca93a30bee52dc4c838864df28cb747d91df
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/06/2020
ms.locfileid: "78856559"
---
# <a name="locale-class"></a>locale Sınıfı

Kültüre özgü bilgileri depolayan bir yerel ayar nesnesini belirli bir yerelleştirilmiş ortamı toplu olarak kapsülleyen bir modeller kümesi olarak tanımlayan sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class locale;
```

## <a name="remarks"></a>Açıklamalar

Bir model, Şu biçimdeki ortak bir nesne olan sınıf [modeli](#facet_class) 'nden türetilmiş bir sınıfın nesnesine yönelik bir işaretçidir:

```cpp
static locale::id id;
```

Bu modellerin açık uçlu bir kümesini tanımlayabilirsiniz. Ayrıca, modellerin rastgele bir sayısını gösteren bir yerel ayar nesnesi oluşturabilirsiniz.

Bu modellerle önceden tanımlanmış gruplar, standart C Kitaplığı 'nda `setlocale`işlev tarafından geleneksel olarak yönetilen [yerel ayar kategorilerini](#category) temsil eder.

Kategori `collate` (LC_COLLATE) şu modelleri içerir:

```cpp
collate<char>
collate<wchar_t>
```

Kategori `ctype` (LC_CTYPE) şu modelleri içerir:

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

Kategori `monetary` (LC_MONETARY) şu modelleri içerir:

```cpp
moneypunct<char, false>
moneypunct<wchar_t, false>
moneypunct<char, true>
moneypunct<wchar_t, true>
money_get<char, istreambuf_iterator<char>>
money_get<wchar_t, istreambuf_iterator<wchar_t>>
money_put<char, ostreambuf_iterator<char>>
money_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Kategori `numeric` (LC_NUMERIC) şu modelleri içerir:

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

Kategori `time` (LC_TIME) şu modelleri içerir:

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Kategori `messages` (LC_MESSAGES) şu modelleri içerir:

```cpp
messages<char>
messages<wchar_t>
```

(Son kategori, POSIX için gereklidir, ancak C standardı değildir.)

Bu önceden tanımlı modellerden bazıları `iostream` sınıfları tarafından, sayısal değerlerin metin dizilerinden ve bunlara dönüştürülmesini denetlemek için kullanılır.

Sınıf yerel ayarı nesnesi ayrıca bir yerel ayar adını sınıf [dizesinin](../standard-library/string-typedefs.md#string)bir nesnesi olarak depolar. Yerel ayar modeli oluşturmak için geçersiz yerel ayar adı kullanmak veya bir yerel ayar nesnesi [runtime_error](../standard-library/runtime-error-class.md)sınıfından bir nesne oluşturur. Yerel ayar nesnesi, bir C stili yerel ayarın nesne tarafından temsil edilen bir yerel ayara karşılık geldiğinden emin değilse, depolanan yerel ayar adı `"*"`. Aksi takdirde, bazı yerel ayar nesne `locale_object`için standart C Kitaplığı içinde, `setlocale(LC_ALL , locale_object.`[ad](#name)`().c_str())`çağırarak, eşleşen bir yerel ayar kurabilirsiniz.

Bu uygulamada, statik üye işlevini de çağırabilirsiniz:

```cpp
static locale empty();
```

Böylece, modeli olmayan bir yerel bir nesne oluşturabilirsiniz. Ayrıca, saydam bir yerel ayar. Şablon [has_facet](../standard-library/locale-functions.md#has_facet) ve [use_facet](../standard-library/locale-functions.md#use_facet) istenen modeli saydam bir yerel ayarda bulamazsa, önce genel yerel ayara, sonra da saydam ise klasik yerel ayara göz tırabilirler. Bu nedenle, şunu yazabilirsiniz:

```cpp
cout.imbue(locale::empty());
```

[`cout`](../standard-library/iostream.md#cout) sonraki eklemeler genel yerel ayarın geçerli durumu tarafından dağıtılır. Şunu da yazabilirsiniz:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

`cout` sonraki eklemeler için sayısal biçimlendirme kuralları, genel yerel ayar, tarih ve parasal tutarların eklenmesi için değiştirme kuralları sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[ayarlar](#locale)|Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[alan](#category)|Standart model aileleri belirtmek için bit maskesi değerleri sağlayan bir tamsayı türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[bile](#combine)|Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.|
|[ada](#name)|Depolanan yerel ayar adını döndürür.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[Klasik](#classic)|Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.|
|[global](#global)|Varsayılan programın yerel ayarını sıfırlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bir yerel ayar atar.|
|[operator!=](#op_neq)|İki yerel ayarın farklı olup olmadığını sınar.|
|[operator ()](#op_call)|İki `basic_string` nesnesini karşılaştırır.|
|[işleç = =](#op_eq_eq)|İki yerel ayarın farksız olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[facet](#facet_class)|Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.|
|[`id`](#id_class)|Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="category"></a>locale:: category

Standart model aileleri belirtmek için bit maskesi değerleri sağlayan bir tamsayı türü.

```cpp
typedef int category;
static const int collate = LC_COLLATE;
static const int ctype = LC_CTYPE;
static const int monetary = LC_MONETARY;
static const int numeric = LC_NUMERIC;
static const int time = LC_TIME;
static const int messages = LC_MESSAGES;
static const int all = LC_ALL;
static const int none = 0;
```

### <a name="remarks"></a>Açıklamalar

Tür, bir bit maskesi türünün bir grubunu bir grup yerel ayarında temsil eden veya ilgili C yerel ayar kategorilerinden herhangi birini temsil etmek için kullanılabilen bir **int** türü için bir eş anlamlı. Öğeleri şunlardır:

- C kategorisine karşılık gelen `collate`LC_COLLATE

- C kategorisine karşılık gelen `ctype`LC_CTYPE

- C kategorisine karşılık gelen `monetary`LC_MONETARY

- C kategorisine karşılık gelen `numeric`LC_NUMERIC

- C kategorisine karşılık gelen `time`LC_TIME

- POSIX kategorisine karşılık gelen `messages`LC_MESSAGES

Diğer iki yararlı değer şunlardır:

- `none`, C kategorilerinin hiçbirine karşılık gelen

- tüm kategorilerin C birleşime karşılık gelen `all`LC_ALL

`monetary` &#124; `time`gibi bu sabitlerle `OR` kullanarak rastgele bir kategori grubunu temsil edebilirsiniz.

## <a name="classic"></a>Yerel ayar:: klasik

Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.

```cpp
static const locale& classic();
```

### <a name="return-value"></a>Dönüş Değeri

C yerel ayarına bir başvuru.

### <a name="remarks"></a>Açıklamalar

Klasik C yerel ayarı, standart C kitaplığı içindeki ABD Ingilizcesi ASCII yerel ayarıdır. Uluslararası olmayan programlarda örtülü olarak kullanılan yerel ayar.

### <a name="example"></a>Örnek

```cpp
// locale_classic.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: " << loc2.name( )
        << "." << endl;
   cout << "The name of the current locale is: " << loc1.name( )
        << "." << endl;

   if (loc2 == locale::classic( ) )
      cout << "The previous locale was classic." << endl;
   else
      cout << "The previous locale was not classic." << endl;

   if (loc1 == locale::classic( ) )
      cout << "The current locale is classic." << endl;
   else
      cout << "The current locale is not classic." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
The previous locale was classic.
The current locale is not classic.
```

## <a name="combine"></a>locale:: birleştirin

Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.

```cpp
template <class Facet>
locale combine(const locale& source_locale) const;
```

### <a name="parameters"></a>Parametreler

*source_locale*\
Hedef yerel ayara eklenecek modeli içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi, ' de bulunan veya *source_locale*listelenen modeli `Facet` **\*** için bir yerel ayar nesnesi döndürür.

### <a name="example"></a>Örnek

```cpp
// locale_combine.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main() {
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s; it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   locale loc2 ( "C" );
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   locale loc3 = loc2.combine<collate<_TCHAR> > (loc);
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;
}
```

## <a name="facet_class"></a>model sınıfı

Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.

```cpp
class facet {
protected:
    explicit facet(size_t references = 0);
    virtual ~facet();
private:
    facet(const facet&) // not defined
    void operator=(const facet&) // not defined
};
```

### <a name="remarks"></a>Açıklamalar

`facet`sınıfından bir nesne kopyalayamaz veya atayamazsınız. `locale::facet` sınıfından türetilmiş nesneleri oluşturabilir ve yok edebilir, taban sınıfının nesneleri doğru değildir. Genellikle, bir `locale`oluşturduğunuzda `facet` türetilmiş bir nesne `_Myfac` oluşturursunuz `locale loc(locale::classic(), new _Myfac);`

Bu gibi durumlarda, `facet` temel sınıf için Oluşturucu sıfır *başvuruları* bağımsız değişkenine sahip olmalıdır. Nesne artık gerekli olmadığında silinir, bu nedenle yalnızca nesne ömrü boyunca sorumluluk verdiğiniz nadir durumlarda sıfır olmayan *Başvurular* bağımsız değişkeni sağlarsınız.

## <a name="global"></a>Yerel ayar:: genel

Programın varsayılan yerel ayarını sıfırlar. Bu çağrı hem C hem C++de genel yerel ayarı etkiler.

```cpp
static locale global(const locale& new_default_locale);
```

### <a name="parameters"></a>Parametreler

*new_default_locale*\
Program tarafından varsayılan yerel ayar olarak kullanılacak yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan yerel ayar sıfırlanmadan önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Program başlangıcında, genel yerel ayar Klasik yerel ayar ile aynıdır. `global()` işlevi, standart C kitaplığında eşleşen bir yerel ayar oluşturmak için `setlocale( LC_ALL, loc.name. c_str())` çağırır.

### <a name="example"></a>Örnek

```cpp
// locale_global.cpp
// compile by using: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( )
{
   locale loc ( "German_germany" );
   locale loc1;
   cout << "The initial locale is: " << loc1.name( ) << endl;
   locale loc2 = locale::global ( loc );
   locale loc3;
   cout << "The current locale is: " << loc3.name( ) << endl;
   cout << "The previous locale was: " << loc2.name( ) << endl;
}
```

```Output
The initial locale is: C
The current locale is: German_Germany.1252
The previous locale was: C
```

## <a name="id_class"></a>ID sınıfı

Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.

```cpp
class id
{
   protected:    id();
   private:      id(const id&)
   void operator=(const id&)  // not defined
};
```

### <a name="remarks"></a>Açıklamalar

Üye sınıfı, benzersiz bir yerel ayar modeli için gereken statik üye nesnesini açıklar. `id`sınıfından bir nesne kopyalayamaz veya atayamazsınız.

## <a name="locale"></a>Yerel ayar:: locale

Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur. Ayrıca bir yıkıcı içerir.

```cpp
locale();

explicit locale(const char* locale_name, category new_category = all);
explicit locale(const string& locale_name);
locale(const locale& from_locale);
locale(const locale& from_locale, const locale& Other, category new_category);
locale(const locale& from_locale, const char* locale_name, category new_category);

template <class Facet>
locale(const locale& from_locale, const Facet* new_facet);

~locale();
```

### <a name="parameters"></a>Parametreler

*locale_name*\
Yerel ayarın adı.

*from_locale*\
Yeni yerel ayarı oluştururken kopyalanacak yerel ayar.

*Diğer*\
Kategorinin seçilecek yerel ayar.

*new_category*\
Oluşturulan yerel ayara değiştirilecek kategori.

*new_facet*\
Oluşturulan yerel ayara değiştirilecek model.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, nesneyi genel yerel ayara uyacak şekilde başlatır. İkinci ve üçüncü oluşturucular, *locale_name*yerel ayar adıyla tutarlı davranış sağlamak için tüm yerel ayar kategorilerini başlatır. Kalan oluşturucular, belirtilen özel durumlarla birlikte *from_locale*kopyalar:

`locale(const locale& from_locale, const locale& Other, category new_category);`

C & *new_category* sıfır olmayan bir kategoriye karşılık gelen *diğer* modellerden değiştirir.

`locale(const locale& from_locale, const char* locale_name, category new_category);`

`locale(const locale& from_locale, const string& locale_name, category new_category);`

`replace_category & new_category` sıfır olmayan bir kategori *replace_category* karşılık gelen bu modellerden `locale(locale_name, all)` değiştirir.

`template<class Facet> locale(const locale& from_locale, Facet* new_facet);`

*new_facet* null bir işaretçi değilse, modeli *new_facet* *from_locale* (veya öğesine ekler) değiştirir.

*Locale_name* yerel ayar adı null işaretçisiyse veya geçersiz değilse, işlev [runtime_error](../standard-library/runtime-error-class.md)atar.

### <a name="example"></a>Örnek

```cpp
// locale_locale.cpp
// compile with: /EHsc
#include <locale>
#include <iostream>
#include <tchar.h>
using namespace std;

int main( ) {

   // Second constructor
   locale loc ( "German_germany" );
   _TCHAR * s1 = _T("Das ist wei\x00dfzz."); // \x00df is the German sharp-s, it comes before z in the German alphabet
   _TCHAR * s2 = _T("Das ist weizzz.");
   int result1 = use_facet<collate<_TCHAR> > ( loc ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc ) << result1 << endl;

   // The first (default) constructor
   locale loc2;
   int result2 = use_facet<collate<_TCHAR> > ( loc2 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc2 )  << result2 << endl;

   // Third constructor
   locale loc3 (loc2,loc, _M_COLLATE );
   int result3 = use_facet<collate<_TCHAR> > ( loc3 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc3 ) << result3 << endl;

   // Fourth constructor
   locale loc4 (loc2, "German_Germany", _M_COLLATE );
   int result4 = use_facet<collate<_TCHAR> > ( loc4 ).
      compare (s1, &s1[_tcslen( s1 )-1 ],  s2, &s2[_tcslen( s2 )-1 ] );
   cout << isalpha (_T ( '\x00df' ), loc4 ) << result4 << endl;
}
```

## <a name="name"></a>Yerel ayar:: ad

Depolanan yerel ayar adını döndürür.

```cpp
string name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerel ayarın adını sağlayan bir dize.

### <a name="example"></a>Örnek

```cpp
// locale_name.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "german" );
   locale loc2 = locale::global( loc1 );
   cout << "The name of the previous locale is: "
        << loc2.name( ) << "." << endl;
   cout << "The name of the current locale is: "
        << loc1.name( ) << "." << endl;
}
```

```Output
The name of the previous locale is: C.
The name of the current locale is: German_Germany.1252.
```

## <a name="op_eq"></a>locale:: operator =

Bir yerel ayar atar.

```cpp
const locale& operator=(const locale& other) noexcept;
```

## <a name="op_neq"></a>locale:: operator! =

İki yerel ayarın farklı olup olmadığını sınar.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*\
Eşitsizlik için test edilecek yerel ayarlardan biri.

### <a name="return-value"></a>Dönüş Değeri

Yerel ayar aynı yerel ayarın kopyası değilse, **true** olan bir Boolean değeri. Yerel ayarların aynı yerel ayar kopyaları olması durumunda bu **yanlış** olur.

### <a name="remarks"></a>Açıklamalar

İki yerel ayar aynı yerel ayarlarsa, biri diğerinin kopyası ise veya özdeş adlara sahip ise eşittir.

### <a name="example"></a>Örnek

```cpp
// locale_op_ne.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 != loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc2 (" << loc2.name( ) << ") are equal." << endl;

   if ( loc1 != loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are not equal." << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ") and\n loc3 (" << loc3.name( ) << ") are equal." << endl;
}
```

```Output
locales loc1 (German_Germany.1252) and
loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252) and
loc3 (English_United States.1252) are not equal.
```

## <a name="op_call"></a>locale:: operator ()

İki `basic_string` nesnesini karşılaştırır.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Parametreler

*sol*\
Sol dize.

*sağ*\
Doğru dize.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi şunu döndürür:

- -1 ilk sıra ikinci diziden daha az karşılaştırırsa.

- İkinci sıra ilk diziden daha az karşılaştırırsa + 1.

- diziler eşdeğer ise 0.

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkin bir şekilde yürütülür:

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

Bu, bir yerel ayar nesnesini işlev nesnesi olarak kullanabileceğiniz anlamına gelir.

### <a name="example"></a>Örnek

```cpp
// locale_op_compare.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

int main( )
{
   using namespace std;
   wchar_t *sa = L"ztesting";
   wchar_t *sb = L"\0x00DFtesting";
   basic_string<wchar_t> a( sa );
   basic_string<wchar_t> b( sb );

   locale loc( "German_Germany" );
   cout << loc( a,b ) << endl;

   const collate<wchar_t>& fac = use_facet<collate<wchar_t> >( loc );
   cout << ( fac.compare( sa, sa + a.length( ),
       sb, sb + b.length( ) ) < 0) << endl;
}
```

```Output
0
0
```

## <a name="op_eq_eq"></a>locale:: operator = =

İki yerel ayarın farksız olup olmadığını sınar.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*\
Eşitlik için test edilecek yerel ayarlardan biri.

### <a name="return-value"></a>Dönüş Değeri

Yerel ayarların aynı yerel ayar kopyaları olması durumunda **doğru** olan bir Boole değeri. Yerel ayarlar aynı yerel ayarın kopyası değilse, bu **false 'tur** .

### <a name="remarks"></a>Açıklamalar

İki yerel ayar aynı yerel ayarlarsa, biri diğerinin kopyası ise veya özdeş adlara sahip ise eşittir.

### <a name="example"></a>Örnek

```cpp
// locale_op_eq.cpp
// compile with: /EHsc
#include <iostream>
#include <string>
#include <locale>

using namespace std;

int main( )
{
   locale loc1( "German_Germany" );
   locale loc2( "German_Germany" );
   locale loc3( "English" );

   if ( loc1 == loc2 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc2 (" << loc2.name( ) << ") are not equal."
      << endl;

   if ( loc1 == loc3 )
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are equal."
      << endl;
   else
      cout << "locales loc1 (" << loc1.name( )
      << ")\n and loc3 (" << loc3.name( ) << ") are not equal."
      << endl;
}
```

```Output
locales loc1 (German_Germany.1252)
and loc2 (German_Germany.1252) are equal.
locales loc1 (German_Germany.1252)
and loc3 (English_United States.1252) are not equal.
```

## <a name="see-also"></a>Ayrıca bkz.

[\<yerel ayar >](../standard-library/locale.md)\
[Kod sayfaları](../c-runtime-library/code-pages.md)\
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
