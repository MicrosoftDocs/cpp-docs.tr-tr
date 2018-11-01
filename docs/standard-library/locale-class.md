---
title: locale Sınıfı
ms.date: 11/04/2016
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
ms.openlocfilehash: 888aeff3e8661338d1a017c06325108a4240ace3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677922"
---
# <a name="locale-class"></a>locale Sınıfı

Kültüre özgü bilgileri depolayan bir yerel ayar nesnesini belirli bir yerelleştirilmiş ortamı toplu olarak kapsülleyen bir modeller kümesi olarak tanımlayan sınıf.

## <a name="syntax"></a>Sözdizimi

```cpp
class locale;
```

## <a name="remarks"></a>Açıklamalar

Bir model bir sınıftan türetilmiş bir sınıfın nesne işaretçisidir [modeli](#facet_class) formu genel bir nesnesine sahip:

```cpp
static locale::id id;
```

Bu modellerin açık uçlu bir kümesini tanımlayabilirsiniz. Ayrıca, modellerin rastgele bir sayısını gösteren bir yerel ayar nesnesi oluşturabilirsiniz.

Bu modellerin önceden tanımlı grupları temsil [yerel ayar kategorileri](#category) işlevi olarak standart C Kitaplığı'nda geleneksel olarak yönetilen `setlocale`.

Kategori collate (LC_COLLATE) şu modelleri içerir:

```cpp
collate<char>
collate<wchar_t>
```

Kategori ctype (LC_CTYPE) şu modelleri içerir:

```cpp
ctype<char>
ctype<wchar_t>
codecvt<char, char, mbstate_t>
codecvt<wchar_t, char, mbstate_t>
codecvt<char16_t, char, mbstate_t>
codecvt<char32_t, char, mbstate_t>
```

Kategori monetary (LC_MONETARY) şu modelleri içerir:

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

Kategori numeric (LC_NUMERIC) şu modelleri içerir:

```cpp
num_get<char, istreambuf_iterator<char>>
num_get<wchar_t, istreambuf_iterator<wchar_t>>
num_put<char, ostreambuf_iterator<char>>
num_put<wchar_t, ostreambuf_iterator<wchar_t>>
numpunct<char>
numpunct<wchar_t>
```

Kategori time (LC_TIME) şu modelleri içerir:

```cpp
time_get<char, istreambuf_iterator<char>>
time_get<wchar_t, istreambuf_iterator<wchar_t>>
time_put<char, ostreambuf_iterator<char>>
time_put<wchar_t, ostreambuf_iterator<wchar_t>>
```

Kategori messages (LC_MESSAGES) şu modelleri içerir:

```cpp
messages<char>
messages<wchar_t>
```

(Son kategori C standart tarafından değil ama POSIX tarafından gereklidir.)

Bu önceden tanımlanmış modellerin bazıları iostreams sınıfları tarafından sayısal değerlerin to ve from metin dizilerine dönüştürülmesini denetlemek için kullanılır.

Bir sınıf yerel ayarı nesnesi bir yerel ad ayrıca sınıfın bir nesnesi depolar. [dize](../standard-library/string-typedefs.md#string). Bir yerel ayar modeli veya bir yerel ayar nesnesi oluşturmak için bir geçersiz yerel ayar adı kullanarak sınıfının bir nesnesi atar [runtime_error](../standard-library/runtime-error-class.md). Depolanan yerel ayar adı `"*"` yerel ayar nesnesi C stili yerel ayar tam olarak karşılık geldiğinden emin olamazsa, nesne tarafından temsil edilir. Aksi takdirde, yerel ayar standart C Kitaplığı içinde eşleşen bir yerel ayar kurup `Loc`, çağırarak `setlocale`(LC_ALL `,` `Loc`. [adı](#name)`().c_str()`).

Bu uygulamada, statik üye işlevini de çağırabilirsiniz:

```cpp
static locale empty();
```

Böylece, modeli olmayan bir yerel bir nesne oluşturabilirsiniz. Bu ayrıca saydam bir yerel ayar olur; varsa şablon işlevleri [has_facet](../standard-library/locale-functions.md#has_facet) ve [use_facet](../standard-library/locale-functions.md#use_facet) istenen modeli bulamazsa saydam bir yerel ayarda bunlar ilk olarak genel yerel ayara bakın ve bu saydamsa Klasik yerel ayar. Bu nedenle, şunu yazabilirsiniz:

```cpp
cout.imbue(locale::empty());
```

Sonraki eklemeler [cout](../standard-library/iostream.md#cout) genel yerel ayarın geçerli duruma göre cout. Şunu da yazabilirsiniz:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

Sayısal biçimlendirme kuralları için sonraki eklemeler `cout` genel yerel ayar'ı tarihleri ve parasal tutarların eklenmesi için kuralların değiştirilmesini sağlasa bile gibi C yerel olduğu gibi aynı kalır.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[Yerel ayar](#locale)|Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[Kategori](#category)|Standart model aileleri belirtmek için bit maskesi değerleri sağlayan bir tamsayı türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[Birleştirme](#combine)|Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.|
|[Adı](#name)|Depolanan yerel ayar adını döndürür.|

### <a name="static-functions"></a>Statik işlevler

|||
|-|-|
|[Klasik](#classic)|Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.|
|[global](#global)|Varsayılan programın yerel ayarını sıfırlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[operator!=](#op_neq)|İki yerel ayarın farklı olup olmadığını sınar.|
|[işleç)](#op_call)|İki karşılaştırır `basic_string` nesneleri.|
|[operator==](#op_eq_eq)|İki yerel ayarın farksız olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|örneği|Açıklama|
|-|-|
|[facet](#facet_class)|Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.|
|[id](#id_class)|Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="category"></a>  Locale::category

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

Türü eşanlamlıdır bir **int** bir bit maskesi ayrı öğelerinde bir grubu temsil edebilen türü sınıf yerel ayarı için yerel yazın veya herhangi bir karşılık gelen C yerel ayar kategorileri göstermek için kullanılabilir. Öğeler şunlardır:

- `collate`, C kategorisine LC_COLLATE karşılık gelen

- `ctype`, C kategorisine LC_CTYPE karşılık gelen

- `monetary`, C kategorisine LC_MONETARY karşılık gelen

- `numeric`, C kategorisine lc_numerıc karşılık gelen

- `time`, C kategorisine lc_tıme karşılık gelen

- `messages`, POSIX LC_MESSAGES kategoriye karşılık gelen

Ayrıca, iki yararlı değerler şunlardır:

- `none`, C kategorisi hiçbiri için karşılık gelen

- `all`, tüm kategorileri LC_ALL C birleşime karşılık gelen

Kullanarak kategorileri rastgele bir grubu temsil edebilen `OR` görüldüğü Bu sabitler ile `monetary` &#124; `time`.

## <a name="classic"></a>  Locale::Classic

Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.

```cpp
static const locale& classic();
```

### <a name="return-value"></a>Dönüş Değeri

C yerel başvuru.

### <a name="remarks"></a>Açıklamalar

Klasik C yerel US değeridir Örtük olarak değil Uluslararası yapılan programlarda kullanılan standart C Kitaplığı içinde ASCII İngilizce yerel ayarı.

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

## <a name="combine"></a>  Locale::Combine

Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.

```cpp
template <class Facet>
locale combine(const locale& Loc) const;
```

### <a name="parameters"></a>Parametreler

*LOC*<br/>
Yerel ayar modeli hedef yerel ayara eklenecek içeren.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevini değiştiren veya ekleyen bir yerel ayar nesnesi döndürür  **\*bu** modeli `Facet` listelenen *Loc*.

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

## <a name="facet_class"></a>  facet sınıfı

Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.

```cpp
class facet {
protected:
    explicit facet(size_t _Refs = 0);
   virtual ~facet();
private:
   facet(const facet&)
   // not defined void operator=(const facet&)
     // not defined
};
```

### <a name="remarks"></a>Açıklamalar

Kopyalayamaz veya sınıf tarafı nesneye atamak olduğunu unutmayın. Oluşturun ve sınıfından türetilmiş nesneler yok `locale::facet` nesneleri doğru temel sınıf. Genellikle, bir nesne oluşturmak `_Myfac` gibi bir yerel ayar oluştururken, model türetilmiş **localeloc**( `locale::classic`(), **yeni**`_Myfac`);

Böyle durumlarda temel sınıf modeli için oluşturucu sıfır olmalıdır `_Refs` bağımsız değişken. Nesne artık gerekmediğinde silinir. Sıfır dışında bir _ bu nedenle, sağladığınız *Refs* bağımsız değişkeni yalnızca nesnenin ömrünü sorumluluğunu aldığınız yere nadir durumlarda.

## <a name="global"></a>  Locale::Global

Program için varsayılan yerel ayar sıfırlar. Bu, C ve C++ için genel yerel ayar etkiler.

```cpp
static locale global(const locale& Loc);
```

### <a name="parameters"></a>Parametreler

*LOC*<br/>
Program tarafından varsayılan yerel ayar olarak kullanılacak yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan yerel ayar sıfırlamadan önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Program başlangıcında, genel yerel ayar Klasik yerel ayara ile aynıdır. `global()` İşlev çağrılarında `setlocale( LC_ALL, loc.name. c_str())` standart C Kitaplığı içinde eşleşen bir yerel ayar oluşturmak için.

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

## <a name="id_class"></a>  id sınıfı

Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.

sınıf kimliği {korumalı: id(); özel: id(const id&) / / void işleç tanımlanmamış =(const id&) / / tanımlanmamış};

### <a name="remarks"></a>Açıklamalar

Üye sınıfı, her benzersiz yerel ayar modeli gerekli statik üye nesnesi tanımlar. Kopyalayamaz veya sınıfın bir nesnesi atama, Not `id`.

## <a name="locale"></a>  Locale::Locale

Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur.

```cpp
locale();

explicit locale(const char* Locname, category Cat = all);
explicit locale(const string& Locname);
locale( const locale& Loc);
locale(const locale& Loc, const locale& Other, category Cat);
locale(const locale& Loc, const char* Locname, category Cat);

template <class Facet>
locale(const locale& Loc, const Facet* Fac);
```

### <a name="parameters"></a>Parametreler

*Locname*<br/>
Bir yerel ayar adı.

*LOC*<br/>
Yeni yerel oluştururken kopyalanacak bir yerel ayar.

*Diğer*<br/>
Bir kategori seçmek için bir yerel ayar.

*Cat*<br/>
Oluşturulan yerel ayara atanması kategorisi.

*Fac*<br/>
İçinde oluşturulan yerel ayar yerine kullanılacak model.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, genel yerel ayar eşleştirilecek nesnesini başlatır. Yerel ayar adı ile tutarlı bir davranış sağlamak için tüm yerel ayar kategorileri ikinci ve üçüncü oluşturucular başlatma *Locname*. Kalan oluşturucuları kopyalama *Loc*, belirtilen özel durumlarla birlikte:

`locale(const locale& Loc, const locale& Other, category Cat);`

gelen değiştirir *diğer* bu modelleri için hangi C C kategorisine karşılık gelen & *Cat* sıfır değil.

`locale(const locale& Loc, const char* Locname, category Cat);`

`locale(const locale& Loc, const string& Locname, category Cat);`

gelen değiştirir `locale(Locname, _All)` bu modelleri için hangi C C kategorisine karşılık gelen & *Cat* sıfır değil.

`template<class Facet> locale(const locale& Loc, Facet* Fac);`

değiştirir (veya ekler) *Loc* modeli *Fac*, *Fac* null bir işaretçi değil.

Bir yerel ayar adı *Locname* null bir işaretçiyse ya da aksi takdirde geçersiz işlev oluşturursa [runtime_error](../standard-library/runtime-error-class.md).

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

## <a name="name"></a>  Locale::Name

Depolanan yerel ayar adını döndürür.

```cpp
string name() const;
```

### <a name="return-value"></a>Dönüş Değeri

Yerel ayarın adını veren bir dize.

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

## <a name="op_neq"></a>  Locale::operator! =

İki yerel ayarın farklı olup olmadığını sınar.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir eşitsizlik için test edilecek gezinin.

### <a name="return-value"></a>Dönüş Değeri

Bir Boolean değer **true** yerel kopyalarını aynı yerel ayarı kullanır; değilse, **false** yerel ayarlar aynı yerel kopyaları varsa.

### <a name="remarks"></a>Açıklamalar

Aynı yerel kopyasını, diğerini ise olmaları durumunda ya da bunların aynı adlara sahip iki yerel eşit olur.

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

## <a name="op_call"></a>  Locale:: operator()

İki karşılaştırır `basic_string` nesneleri.

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Parametreler

*Sol*<br/>
Sol dize.

*sağ*<br/>
Doğru dize.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi döndürür:

- ilk dizi ikinci sırası sayısından az karşılaştırırsa -1.

- İkinci sırası daha azını ilk dizi karşılaştırırsa + 1.

- 0 dizileri eşdeğerdir.

### <a name="remarks"></a>Açıklamalar

Üye işlevi etkin şekilde şunları yürütür:

```cpp
const collate<CharType>& fac = use_fac<collate<CharType>>(*this);

return (fac.compare(left.begin(), left.end(), right.begin(), right.end()) < 0);
```

Bu nedenle, bir işlev nesnesi bir yerel ayar nesnesini kullanabilirsiniz.

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

## <a name="op_eq_eq"></a>  Locale::operator ==

İki yerel ayarın farksız olup olmadığını sınar.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*sağ*<br/>
Bir eşitlik için test edilecek gezinin.

### <a name="return-value"></a>Dönüş Değeri

Bir Boolean değer **true** yerel ayarlar aynı; yerel kopyaları varsa **false** yerel ayarlar aynı yerel kopyasını değilse.

### <a name="remarks"></a>Açıklamalar

Aynı yerel kopyasını, diğerini ise olmaları durumunda ya da bunların aynı adlara sahip iki yerel eşit olur.

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

[\<yerel ayar >](../standard-library/locale.md)<br/>
[Kod Sayfaları](../c-runtime-library/code-pages.md)<br/>
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
