---
description: 'Daha fazla bilgi edinin: locale sınıfı'
title: locale Sınıfı
ms.date: 07/20/2020
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
ms.openlocfilehash: e934a2e892f0b68926369c8e4a4128162345dd83
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284635"
---
# <a name="locale-class"></a>locale Sınıfı

Kültüre özgü bilgileri depolayan bir yerel ayar nesnesini belirli bir yerelleştirilmiş ortamı toplu olarak kapsülleyen bir modeller kümesi olarak tanımlayan sınıf.

## <a name="syntax"></a>Syntax

```cpp
class locale;
```

## <a name="remarks"></a>Açıklamalar

Bir model, Şu biçimdeki ortak bir nesne olan sınıf [modeli](#facet_class) 'nden türetilmiş bir sınıfın nesnesine yönelik bir işaretçidir:

```cpp
static locale::id id;
```

Bu modellerin açık uçlu bir kümesini tanımlayabilirsiniz. Ayrıca, modellerin rastgele bir sayısını gösteren bir yerel ayar nesnesi oluşturabilirsiniz.

Bu modellerle önceden tanımlanmış gruplar, standart C Kitaplığı 'nda işlev tarafından geleneksel olarak yönetilen [yerel ayar kategorilerini](#category) temsil eder `setlocale` .

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

Kategori `messages` (lc_messages) şu modelleri içerir:

```cpp
messages<char>
messages<wchar_t>
```

(Son kategori, POSIX için gereklidir, ancak C standardı değildir.)

Bu önceden tanımlı `iostream` modellerden bazıları sınıflar tarafından, sayısal değerlerin metin dizilerinden ve bunlara dönüştürülmesini denetlemek için kullanılır.

Sınıf yerel ayarı nesnesi ayrıca bir yerel ayar adını sınıf [dizesinin](../standard-library/string-typedefs.md#string)bir nesnesi olarak depolar. Yerel ayar modeli oluşturmak için geçersiz yerel ayar adı kullanmak veya bir yerel ayar nesnesi [runtime_error](../standard-library/runtime-error-class.md)sınıfından bir nesne oluşturur. Depolanan yerel ayar adı, `"*"` yerel ayar nesnesinin, C stili bir yerel ayarın nesne tarafından temsil edilen tam öğesine karşılık geldiğinden emin olamaz. Aksi takdirde, ad çağırarak, bazı yerel ayar nesneleri için standart C Kitaplığı içinde eşleşen bir yerel ayar kurabilirsiniz `locale_object` `setlocale(LC_ALL , locale_object.` [](#name) `().c_str())` .

Bu uygulamada, statik üye işlevini de çağırabilirsiniz:

```cpp
static locale empty();
```

Böylece, modeli olmayan bir yerel bir nesne oluşturabilirsiniz. Ayrıca, saydam bir yerel ayar. Şablon [has_facet](../standard-library/locale-functions.md#has_facet) ve [use_facet](../standard-library/locale-functions.md#use_facet) istenen modeli saydam bir yerel ayarda bulamazsa, önce genel yerel ayara, sonra da saydam ise klasik yerel ayara göz tırabilirler. Bu nedenle, şunu yazabilirsiniz:

```cpp
cout.imbue(locale::empty());
```

Sonraki eklemeler, [`cout`](../standard-library/iostream.md#cout) genel yerel ayarın geçerli durumu ile dağıtılır. Şunu da yazabilirsiniz:

```cpp
locale loc(locale::empty(),
    locale::classic(),
    locale::numeric);

cout.imbue(loc);
```

Sonraki eklemeler için sayısal biçimlendirme kuralları, `cout` genel yerel ayar, tarih ve parasal tutarların eklenmesi için değişen kuralları sağlar.

### <a name="constructors"></a>Oluşturucular

|Oluşturucu|Açıklama|
|-|-|
|[locale](#locale)|Bir yerel ayar veya yerel ayar kopyası ya da modelin veya kategorinin başka bir yerel ayardaki bir model veya kategori tarafından değiştirilen bir kopyasını oluşturur.|

### <a name="typedefs"></a>Tür tanımları

|Tür adı|Açıklama|
|-|-|
|[alan](#category)|Standart model aileleri belirtmek için bit maskesi değerleri sağlayan bir tamsayı türü.|

### <a name="member-functions"></a>Üye işlevleri

|Üye işlevi|Açıklama|
|-|-|
|[combine](#combine)|Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.|
|[ada](#name)|Depolanan yerel ayar adını döndürür.|

### <a name="static-functions"></a>Statik işlevler

|Ad|Açıklama|
|-|-|
|[Klasik](#classic)|Statik üye işlevini klasik C yerel ayarını temsil eden yerel bir nesneye döndürür.|
|[Genel](#global)|Varsayılan programın yerel ayarını sıfırlar.|

### <a name="operators"></a>İşleçler

|İşleç|Açıklama|
|-|-|
|[işleç =](#op_eq)|Bir yerel ayar atar.|
|[işleç! =](#op_neq)|İki yerel ayarın farklı olup olmadığını sınar.|
|[operator ()](#op_call)|İki `basic_string` nesneyi karşılaştırır.|
|[işleç = =](#op_eq_eq)|İki yerel ayarın farksız olup olmadığını sınar.|

### <a name="classes"></a>Sınıflar

|Sınıf|Açıklama|
|-|-|
|[facet](#facet_class)|Tüm yerel ayar modelleri için temel sınıf görevi gören sınıf.|
|[`id`](#id_class)|Üye sınıfı özellikleri, bir yerel ayardaki arama modelleri için bir dizin olarak kullanılan benzersiz bir kimlik sağlar.|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="localecategory"></a><a name="category"></a> locale:: category

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

Tür, bir **`int`** bit maskesi türünün bir grubunu bir grup yerel ayarında temsil eden veya Ilgili C yerel ayar kategorilerinin herhangi birini temsil etmek için kullanılabilen bir türün eş anlamlısıdır. Öğeleri şunlardır:

- `collate`, C kategorisine karşılık gelen LC_COLLATE

- `ctype`, C kategorisine karşılık gelen LC_CTYPE

- `monetary`, C kategorisine karşılık gelen LC_MONETARY

- `numeric`, C kategorisine karşılık gelen LC_NUMERIC

- `time`, C kategorisine karşılık gelen LC_TIME

- `messages`, POSIX kategorisine karşılık gelen LC_MESSAGES

Diğer iki yararlı değer şunlardır:

- `none`, C kategorilerinin hiçbirine karşılık gelen

- `all`tüm kategorilerin C birleşime karşılık gelen LC_ALL

`OR`&#124; gibi, Bu sabitler ile kullanarak rastgele bir kategori grubunu temsil edebilirsiniz `monetary` `time` .

## <a name="localeclassic"></a><a name="classic"></a> Yerel ayar:: klasik

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

## <a name="localecombine"></a><a name="combine"></a> locale:: birleştirin

Belirtilen yerel ayardaki bir modeli hedef yerel ayara ekler.

```cpp
template <class Facet>
locale combine(const locale& source_locale) const;
```

### <a name="parameters"></a>Parametreler

*source_locale*\
Hedef yerel ayara eklenecek modeli içeren yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Üye işlevi, içinde bulunan veya source_locale listelenen modeli **\* buna** ekleyen bir yerel ayar nesnesi döndürür `Facet` . 

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

## <a name="facet-class"></a><a name="facet_class"></a> model sınıfı

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

Sınıfının bir nesnesini kopyalayamaz veya atayamazsınız `facet` . `locale::facet`Temel sınıfın doğru nesnelerinden türemeyen ancak sınıftan türetilmiş nesneleri oluşturabilir ve yok edebilirsiniz. Genellikle, ' `_Myfac` `facet` `locale` de olduğu gibi, oluştururken türetilmiş bir nesne oluşturursunuz `locale loc(locale::classic(), new _Myfac);`

Bu gibi durumlarda, temel sınıf için Oluşturucu `facet` sıfır *başvuruları* bağımsız değişkenine sahip olmalıdır. Nesne artık gerekli olmadığında silinir, bu nedenle yalnızca nesne ömrü boyunca sorumluluk verdiğiniz nadir durumlarda sıfır olmayan *Başvurular* bağımsız değişkeni sağlarsınız.

## <a name="localeglobal"></a><a name="global"></a> Yerel ayar:: genel

Programın varsayılan yerel ayarını sıfırlar. Bu çağrı hem C hem de C++ için genel yerel ayarı etkiler.

```cpp
static locale global(const locale& new_default_locale);
```

### <a name="parameters"></a>Parametreler

*new_default_locale*\
Program tarafından varsayılan yerel ayar olarak kullanılacak yerel ayar.

### <a name="return-value"></a>Dönüş Değeri

Varsayılan yerel ayar sıfırlanmadan önceki yerel ayar.

### <a name="remarks"></a>Açıklamalar

Program başlangıcında, genel yerel ayar Klasik yerel ayar ile aynıdır. `global()`İşlevi, `setlocale( LC_ALL, loc.name. c_str())` Standart C kitaplığında eşleşen bir yerel ayar oluşturmak için çağırır.

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

## <a name="id-class"></a><a name="id_class"></a> ID sınıfı

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

Üye sınıfı, benzersiz bir yerel ayar modeli için gereken statik üye nesnesini açıklar. Sınıfının bir nesnesini kopyalayamaz veya atayamazsınız `id` .

## <a name="localelocale"></a><a name="locale"></a> Yerel ayar:: locale

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

*Farklı*\
Kategorinin seçilecek yerel ayar.

*new_category*\
Oluşturulan yerel ayara değiştirilecek kategori.

*new_facet*\
Oluşturulan yerel ayara değiştirilecek model.

### <a name="remarks"></a>Açıklamalar

İlk Oluşturucu, nesneyi genel yerel ayara uyacak şekilde başlatır. İkinci ve üçüncü oluşturucular, *locale_name* yerel ayar adıyla tutarlı davranış sağlamak için tüm yerel ayar kategorilerini başlatır. Kalan oluşturucular, belirtilen özel durumlarla birlikte *from_locale* kopyalar:

`locale(const locale& from_locale, const locale& Other, category new_category);`

C & *new_category* sıfır olmayan bir kategoriye karşılık gelen *diğer* modellerden değiştirir.

`locale(const locale& from_locale, const char* locale_name, category new_category);`

`locale(const locale& from_locale, const string& locale_name, category new_category);`

`locale(locale_name, all)`sıfır olmayan bir kategori *replace_category* karşılık gelen modellerden değiştirir `replace_category & new_category` .

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

## <a name="localename"></a><a name="name"></a> Yerel ayar:: ad

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

## <a name="localeoperator"></a><a name="op_eq"></a> locale:: operator =

Bir yerel ayar atar.

```cpp
const locale& operator=(const locale& other) noexcept;
```

## <a name="localeoperator"></a><a name="op_neq"></a> locale:: operator! =

İki yerel ayarın farklı olup olmadığını sınar.

```cpp
bool operator!=(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Eşitsizlik için test edilecek yerel ayarlardan biri.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yerel ayarlarda aynı yerel ayarın kopyası yoksa bir Boole değeri. Bu **`false`** , yerel ayarların aynı yerel ayarın kopyaları olması durumunda olur.

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

## <a name="localeoperator"></a><a name="op_call"></a> locale:: operator ()

`basic_string`Bu yerel ayarın modeli tarafından tanımlanan lexicographic karşılaştırma kurallarına göre iki nesneyi karşılaştırır `std::collate<charT>` .

```cpp
template <class CharType, class Traits, class Allocator>
bool operator()(
    const basic_string<CharType, Traits, Allocator>& left,
    const basic_string<CharType, Traits, Allocator>& right) const;
```

### <a name="parameters"></a>Parametreler

*tarafta*\
Karşılaştırılacak ilk dize.

*Right*\
Karşılaştırılacak ikinci dize.

### <a name="return-value"></a>Dönüş Değeri

- **`true`***sol* olarak lexıse, *yoksa, tersi* durumda **`false`** .

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
   const wchar_t *sa = L"ztesting";
   const wchar_t *sb = L"\0x00DFtesting";
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

## <a name="localeoperator"></a><a name="op_eq_eq"></a> locale:: operator = =

İki yerel ayarın farksız olup olmadığını sınar.

```cpp
bool operator==(const locale& right) const;
```

### <a name="parameters"></a>Parametreler

*Right*\
Eşitlik için test edilecek yerel ayarlardan biri.

### <a name="return-value"></a>Dönüş Değeri

**`true`** Yerel ayarların aynı yerel ayar kopyaları olması durumunda olan bir Boole değeri. **`false`** Yerel ayarların aynı yerel ayarın kopyası yoksa, bu olur.

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

[\<locale>](../standard-library/locale.md)\
[Kod sayfaları](../c-runtime-library/code-pages.md)\
[Yerel ayar adları, diller ve ülke/bölge dizeleri](../c-runtime-library/locale-names-languages-and-country-region-strings.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
