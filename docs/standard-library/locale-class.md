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
ms.openlocfilehash: 2581c5cdacc9e542f5d911860128dcf5526621ef
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367310"
---
# <a name="locale-class"></a>locale Sınıfı

Kültüre özgü bilgileri depolayan bir yerel ayar nesnesini belirli bir yerelleştirilmiş ortamı toplu olarak kapsülleyen bir modeller kümesi olarak tanımlayan sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class locale;
```

## <a name="remarks"></a>Açıklamalar

Fatür, formun ortak nesnesine sahip sınıf [falasından](#facet_class) türetilen bir sınıfın nesnesine işaretçidir:

```cpp
static locale::id id;
```

Bu modellerin açık uçlu bir kümesini tanımlayabilirsiniz. Ayrıca, modellerin rastgele bir sayısını gösteren bir yerel ayar nesnesi oluşturabilirsiniz.

Bu yönlerin önceden tanımlanmış grupları, işlev `setlocale`tarafından Standart C Kitaplığı'nda geleneksel olarak yönetilen yerel [kategorileri](#category) temsil eder.

Kategori `collate` (LC_COLLATE) yönlerini içerir:

```cpp
collate<char>
collate<wchar_t>
```

Kategori `ctype` (LC_CTYPE) yönlerini içerir:

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

Kategori `monetary` (LC_MONETARY) yönlerini içerir:

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

Kategori `numeric` (LC_NUMERIC) yönlerini içerir:

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

Kategori `time` (LC_TIME) yönlerini içerir:

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Kategori `messages` (LC_MESSAGES) yönlerini içerir:

```cpp
messages<char>
messages<wchar_t>
```

(Son kategori POSIX tarafından gereklidir, ancak C Standardı değildir.)

Bu önceden tanımlanmış faktan `iostream` bazıları, sayısal değerlerin metin dizilerine ve metin dizilerine dönüşümlerini denetlemek için sınıflar tarafından kullanılır.

Sınıf yerel bir nesnede, yerel ad da sınıf [dizesinin](../standard-library/string-typedefs.md#string)nesnesi olarak depolar. Bir yerel fason oluşturmak için geçersiz bir yerel ad kullanmak veya yerel bir nesne sınıf [nesnesi runtime_error.](../standard-library/runtime-error-class.md) Depolanan yerel ad, `"*"` yerel nesnenin C stili bir yerel aserin nesne tarafından temsil edilene tam olarak karşılık verdiğinden emin olamazsa. `locale_object`Aksi takdirde, bazı yerel nesneler için, `setlocale(LC_ALL , locale_object.` [ad](#name)`().c_str())`çağırarak Standart C Kitaplığı içinde eşleşen bir yerel oluşturabilirsiniz.

Bu uygulamada, statik üye işlevini de çağırabilirsiniz:

```cpp
static locale empty();
```

Böylece, modeli olmayan bir yerel bir nesne oluşturabilirsiniz. Aynı zamanda saydam bir yer. Şablon [has_facet](../standard-library/locale-functions.md#has_facet) işlevleri ve [use_facet](../standard-library/locale-functions.md#use_facet) saydam bir yerel alanda istenen yönü bulamıyorsa, önce genel yerel ekime ve sonra saydamsa, klasik yerel ayine başvururlar. Yani, yazabilirsiniz:

```cpp
cout.imbue(locale::empty());
```

Sonraki eklemeler, [`cout`](../standard-library/iostream.md#cout) genel yerelin geçerli durumu tarafından aracılık edilir. Şunu da yazabilirsiniz:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

Sonraki eklemeler için sayısal biçimlendirme `cout` kuralları, küresel yerel konum tarihleri ve parasal tutarlar eklemek için değişen kurallar sağlarken bile, C yerel alanıyla aynı kalır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Yerel ayar](#locale)|Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Kategori](#category)|Standart model aileleri belirtmek için bit maskesi değerleri sağlayan bir tamsayı türü.|

### <a name="member-functions"></a>Üye işlevler

|Üye fonksiyonu|Açıklama|
|-|-|
|[combine](#combine)|Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.|
|[Adı](#name)|Depolanan yerel ayar adını döndürür.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[Klasik](#classic)|Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.|
|[Küresel](#global)|Varsayılan programın yerel ayarını sıfırlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç=](#op_eq)|Bir yerel yer atar.|
|[işleç!=](#op_neq)|İki yerel ayarın farklı olup olmadığını sınar.|
|[işletici( )](#op_call)|İki `basic_string` nesneyi karşılaştırır.|
|[işleç==](#op_eq_eq)|İki yerel ayarın farksız olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[facet](#facet_class)|Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.|
|[`id`](#id_class)|Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** \<yerel>

**Ad alanı:** std

## <a name="localecategory"></a><a name="category"></a>yerel::kategori

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

Tür, bitmask türünden farklı öğelerden oluşan bir grubu sınıf yerelden sınıfa yerel olarak temsil eden veya karşılık gelen C yerel alan kategorilerinden herhangi birini temsil etmek için kullanılabilecek bir **int** türüyle eş anlamlıdır. Öğeler şunlardır:

- `collate`, C kategorisine karşılık gelen LC_COLLATE

- `ctype`, C kategorisine karşılık gelen LC_CTYPE

- `monetary`, C kategorisine karşılık gelen LC_MONETARY

- `numeric`, C kategorisine karşılık gelen LC_NUMERIC

- `time`, C kategorisine karşılık gelen LC_TIME

- `messages`, POSIX kategorisine karşılık gelen LC_MESSAGES

İki daha yararlı değerler şunlardır:

- `none`, C kategorilerinin hiçbirine karşılık gelen

- `all`, tüm kategorilerin C birliğine karşılık gelen LC_ALL

Bu sabitleri kullanarak `OR` rasgele bir kategori grubunu temsil &#124;. `time` `monetary`

## <a name="localeclassic"></a><a name="classic"></a>yerel::klasik

Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.

```cpp
static const locale& classic();
```

### <a name="return-value"></a>Dönüş Değeri

C yerel bir referans.

### <a name="remarks"></a>Açıklamalar

Klasik C yerel standart C kütüphane içinde ABD İngilizce ASCII yerel. Uluslararası olmayan programlarda dolaylı olarak kullanılan yerdir.

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

## <a name="localecombine"></a><a name="combine"></a>yerel::birleştirmek

Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.

```cpp
template <class Facet>
locale combine(const locale& source_locale) const;
```

### <a name="parameters"></a>Parametreler

*source_locale*\
Hedef yerel alana eklenecek fası içeren yerel.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev, `Facet` *source_locale'da*listelenen yönün yerine geçen veya ** \*buna** ekleyen bir yerel nesne döndürür.

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

## <a name="facet-class"></a><a name="facet_class"></a>fateks Sınıf

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

Sınıfın bir nesnesini kopyalayamaz `facet`veya atayamazsınız. Sınıftan `locale::facet` türetilen nesneleri oluşturup yok edebilirsiniz, ancak taban sınıfın nesneleri uygun değildir. Tipik olarak, `_Myfac` `facet` bir `locale`,`locale loc(locale::classic(), new _Myfac);`

Bu gibi durumlarda, taban sınıfın `facet` oluşturucusu sıfır *başvuru* argümanı olmalıdır. Nesneye artık gerek kalmadığında, silinir, bu nedenle yalnızca nesnenin ömrü için sorumluluk aldığınız nadir durumlarda sıfır olmayan bir *başvuru* bağımsız değişkeni sağlarsınız.

## <a name="localeglobal"></a><a name="global"></a>yerel::global

Programın varsayılan yerel ayarını sıfırlar. Bu çağrı hem C hem de C++'ın genel yerel abunu etkiler.

```cpp
static locale global(const locale& new_default_locale);
```

### <a name="parameters"></a>Parametreler

*new_default_locale*\
Program tarafından varsayılan yerel olarak kullanılacak yerel.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan yerel ayar sıfırlandıönce önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Program başlatmada, genel yerel konum klasik yerel olarak aynıdır. `global()` İşlev, `setlocale( LC_ALL, loc.name. c_str())` Standart C kitaplığında eşleşen bir yerel bilgisayar oluşturmayı çağırır.

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

## <a name="id-class"></a><a name="id_class"></a>id Sınıf

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

Üye sınıf, her benzersiz yerel görünüm fanının gerektirdiği statik üye nesneyi açıklar. Sınıfın bir nesnesini kopyalayamaz `id`veya atayamazsınız.

## <a name="localelocale"></a><a name="locale"></a>yerel::yerel

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
Bir yerel yerin adı.

*from_locale*\
Yeni yerel alanı oluşturmak için kopyalanacak bir yerel alan.

*Diğer*\
Bir kategori seçmek için bir yerel.

*new_category*\
Kategori, inşa edilen yerel alana değiştirilecek.

*new_facet*\
Façe inşa edilen yerel içine değiştirilecek.

### <a name="remarks"></a>Açıklamalar

İlk oluşturucu, nesneyi genel yerel eşleşecek şekilde başharfe ait hale getirmektir. İkinci ve üçüncü oluşturucular, locale_name yerel adla tutarlı bir davranış için tüm yerel kategorileri *açarlar.* Kalan yapıcılar *from_locale*kopyalayın , istisnalar hariç:

`locale(const locale& from_locale, const locale& Other, category new_category);`

C & *new_category* sıfır olmayan bir kategoriye karşılık gelen *diğer* yönlerin yerine.

`locale(const locale& from_locale, const char* locale_name, category new_category);`

`locale(const locale& from_locale, const string& locale_name, category new_category);`

sıfır olmayan `locale(locale_name, all)` bir kategori *replace_category* `replace_category & new_category` karşılık gelen bu yönleriyle değiştirir.

`template<class Facet> locale(const locale& from_locale, Facet* new_facet);`

yerine (veya ekler *from_locale)* new_facet, *new_facet* null bir işaretçi *değilse.*

Yerel ad *locale_name* null işaretçisi veya başka bir şekilde geçersizse, işlev [runtime_error.](../standard-library/runtime-error-class.md)

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

## <a name="localename"></a><a name="name"></a>yerel::ad

Depolanan yerel ayar adını döndürür.

```cpp
string name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerel in adını veren bir dize.

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

## <a name="localeoperator"></a><a name="op_eq"></a>yerel::operatör=

Bir yerel yer atar.

```cpp
const locale& operator=(const locale& other) noexcept;
```

## <a name="localeoperator"></a><a name="op_neq"></a>yerel::operatör!=

İki yerel ayarın farklı olup olmadığını sınar.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Eşitsizlik için test edilecek yerel lerden biri.

### <a name="return-value"></a>Dönüş Değeri

Yerel değerler aynı yerel in kopyası değilse **doğru** olan Boolean değeri. Yerel olarak aynı yerel in kopyaları ise **yanlış.**

### <a name="remarks"></a>Açıklamalar

İki yerel alan, aynı yerel konumsa, biri diğerinin kopyasıysa veya aynı adlara sahipse eşittir.

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

## <a name="localeoperator"></a><a name="op_call"></a>yerel::operatör()

İki `basic_string` nesneyi karşılaştırır.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Sol*\
Sol dize.

*Doğru*\
Doğru dize.

### <a name="return-value"></a>Dönüş Değeri

Üye işlev döner:

- -1 eğer ilk sekans ikinci sekanstan daha az karşılaştırırsa.

- +1 eğer ikinci sıra ilk ardandan daha az karşılaştırırsa.

- Diziler eşdeğerse 0.

### <a name="remarks"></a>Açıklamalar

Üye işlev etkili bir şekilde yürütür:

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

Bu, bir işlev nesnesi olarak bir yerel nesne kullanabilirsiniz anlamına gelir.

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

## <a name="localeoperator"></a><a name="op_eq_eq"></a>yerel::operator==

İki yerel ayarın farksız olup olmadığını sınar.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*Doğru*\
Eşitlik için test edilecek yerel lerden biri.

### <a name="return-value"></a>Dönüş Değeri

Yerel değerler aynı yerela kopyaları ise **doğru** olan boolean değeri. Yerel olarak aynı yerel in kopyası değilse **yanlış.**

### <a name="remarks"></a>Açıklamalar

İki yerel alan, aynı yerel konumsa, biri diğerinin kopyasıysa veya aynı adlara sahipse eşittir.

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

[\<yerel>](../standard-library/locale.md)\
[Kod Sayfaları](../c-runtime-library/code-pages.md)\
[Yerel Adlar, Diller ve Ülke/Bölge Dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
